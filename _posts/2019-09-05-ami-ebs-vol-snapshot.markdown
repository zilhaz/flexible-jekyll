---
layout: post
title: CLARIFYING THE RELATIONSHIP AMONG AMI, EBS VOLUME AND SNAPSHOT IN AWS EC2
date: 2019-09-05 
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: aws.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [AWS] # add tag
---
For AWS beginners, the relationship among an EC2 Instance, AMI (Amazon Machine Image), EBS Volume and Snapshot might get quite confusing. Here, I am not going to explain these relationships with definitions and theories. Rather, I will try to explain it with example and hands-on demonstration. If required, perhaps you can Google and check out the definitions of these AWS terminologies from other sources and then come back here to clarify further.

Let's say your "EC2 Instance I1" has two EBS volumes attached to it -- EBS Volume V1a and EBS Volume V1b

Now, if you create an AMI image from EC2 Instance I1, you will get --

-   An AMI image of EC2 Instance I1, let's call it AMI1
-   A snapshot of EBS Volume V1a, let's call it S1
-   A snapshot of EBS Volume V1b, let's call it S2

Then, if you launch a new instance from AMI1 image, you will get --

-   A new EC2 instance, let's call it I2
-   A new EBS Volume generated from Snapshot S1, let's call it V2a
-   A new EBS Volume generated from Snapshot S2, let's call it V2b
-   (And a network interface)

![AMI]({{site.baseurl}}/assets/img/AMI.png)

To sum it up --

1.  An AMI image creates snapshot(s) of the volume(s) that are attached to the original instance (from which the AMI is created)
2.  A new instance launched from an AMI image creates volume(s) from the snapshots attached to that AMI.

Now here is a step by step demo to show those relationships.

While creating a new EC2 instance, along with Root volume, I added an additional EBS Volume of 2 GiB.

Step 1: Create a new instance with the default Root volume and an additional EBS volume

From Instances screen, create a new instance with the default Root volume and an additional EBS volume.

![AMI]({{site.baseurl}}/assets/img/1a.png)

In "Instances" page, we can see a new instance named EBSVolDemo has been created.

![AMI]({{site.baseurl}}/assets/img/1b.png)

Step 2: Go to Volumes screen and you will see two volumes there as defined in Step 1

If we go to "ELASTIC BLOSK STORE à Volumes", we will see two Volumes have been created automatically and attached to the EC2 instance because while creating a new EC2 instance, along with Root volume, I added an additional EBS Volume of 2 GiB.

We can confirm the attachment between the instance and volumes by looking at Attachment information in Volume's description, as shown in the below image.

![AMI]({{site.baseurl}}/assets/img/2.png)

Step 3. Create an AMI image from the instance created in Step 1

Now let's go back to Instances page and crate an AMI Image from our EBSVolDemo instance.

![AMI]({{site.baseurl}}/assets/img/3a.png)

While creating the image, we can see the console already populates two volumes in "Instance Volumes" section, that we attached to the original EBSVolDemo instance. We named the AMI "ImageFromEBSVolDemo"

![AMI]({{site.baseurl}}/assets/img/3b.png)

Once the image is created, if we go to AMIs screen and check the Details section of the image, we will see that two snapshots of above two volumes have been attached to ImageFromEBSVolDemo image.

![AMI]({{site.baseurl}}/assets/img/3c.png)

Step 4: Confirm two snapshots of the two volumes (in Step 1) have been created automatically.

If we go to "ELASTIC BLOCK STORE à Snapshots", we can see more details of the snapshots that got generated with the AMI. In Snapshot's Description, we can see the Volume ID of the snapshot volume.

![AMI]({{site.baseurl}}/assets/img/4.png)

Step 5: Launch a new instance from the AMI created in Step 3

Now, let's go to "IMAGES --> AMIs" and launch an instance from ImageFromEBSVolDemo image.

![AMI]({{site.baseurl}}/assets/img/5a.png)

While launching the new instance, in "Add Storage" section we can see that the same volumes (as the original EBSVolDemo instance and ImageFromEBSVolDemo image) have been automatically populated in the screen.

![AMI]({{site.baseurl}}/assets/img/5b.png)

Step 6: Confirm the same Volumes (as Step 1 and Step 3) have been created automatically (unless we changed them manually while launching the new instance in Step 5)

After launching the new instance from the image, in Instance description section we can see the AMI ID and Name from which the instance has been launched.

![AMI]({{site.baseurl}}/assets/img/6a.png)

Once the new instance (Name: CreatedFromEBSVolDemoAMI) from ImageFromEBSVolDemo image is up and running, if we go to "ELASTIC BLOCK STORE --> Volumes" screen, we can see that two new volumes as same as our two initial volumes have been created.

![AMI]({{site.baseurl}}/assets/img/6b.png)

Hope it helps!