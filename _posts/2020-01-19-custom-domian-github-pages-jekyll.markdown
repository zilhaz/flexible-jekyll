---
layout: post
title: SETTING UP CUSTOM DOMAIN FOR A ‘GITHUB PAGES WITH JEKYLL’ SITE IN THE RIGHT WAY
date: 2020-01-19 
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: githubjekyll.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [GitHub, Jekyll]
---
Recently I ditched WordPress CMS and moved two of my websites to [GitHub Pages](https://pages.github.com/){:target="_blank"}. I used [Jekyll](https://jekyllrb.com/){:target="_blank"} a simple, blog-aware, static site generator for both of my websites. Setting up the sites was quite easy, however figuring out the right way to configure the custom domain (with https enabled) on GitHub Pages took me some time. So, here I am to save your time and show you how to get it right --

**1. ****Setting up custom domain on GitHub Pages setting**

Set up custom domain on GitHub Pages as shown below. Make sure you are not typing www before your site name. And check "Enforce HTTPS".

![Image]({{site.baseurl}}/assets/img/customdomain.png)

**2. ****Setting DNS Host records on your domain name provider's portal**

Go to your domain name provider's website and set the records as shown below. Setting up CNAME with username.github.io is particularly important. Otherwise if someone types www before your website name, the browser will not be able to show the website. At the time of writing this post, GitHub Pages is using the below IP Addresses for A records. But it will be a good idea to check if there has been any change in these IP addresses. You can check it in this [GitHub Help page](https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site#configuring-a-records-with-your-dns-provider){:target="_blank"}.

![Image]({{site.baseurl}}/assets/img/dnsrecords.png)

**3. ****Edit YAML file**

Add/update baseurl and url keys of your config.yml file as below.
```
baseurl: # the subpath of your site, e.g. /blog. If it's not relevant for your site, keep it blank.
url: "https://www.example.com" # the base hostname & protocol for your site.
```

If you follow above steps correctly, your site should be up and running shortly. Good luck!

-----------
*Image credit: https://guides.github.com/features/pages/*