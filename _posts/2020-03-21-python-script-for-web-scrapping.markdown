---
layout: post
title: A SUPER EASY PYTHON SCRIPT FOR WEB SCRAPPING THAT ANYBODY CAN USE
date: 2020-03-21 
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: githubjekyll.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [python, web_scrapping, beautiful_soup]
---
** You don't need to know Python or even need to have Python installed in your computer to use this script.

Once I needed to scrap some simple data from a webpage. I thought there would be plenty of free tools available in the internet to do that. Unfortunately, I was wrong or was unable to find any of them. At that time, I knew a little bit of Python, however, I was aware that there was a Python package called Beautiful Soup used for parsing HTML and XML documents. So, I thought I could find a simple Python script somewhere in the web and just do the copy-pasting to get my job done. That time I was half-right. Yes, I had found a lot of free Python scripts but none of them were easy enough for me that I could use with a little modification. At the end, I had to make my own script taking bits and pieces from here and there. Now it's here for you.

You need to do there three things (or two things if you already have a Python compiler) to use this script --

- Identify the html elements of the data you want to scrap (in our example below, we used Chrome Developer tools to do that)

- Go to the online IDE called repl.it and open a new repl (really simple, just go to the website, you can figure it out by yourself)

- Copy the Python script provided below and paste into repl.it and put your URL and html elements in the script

**Step 1: Finding html elements**

In our example, we want to extract book titles and author names from below webpage. If we use Chrome browser, we can go to Developers tool (F12), click that "Arrow inside a square" symbol which *selects an element in the page to inspect it* and then hover over the book title and author name.

You can see that book title is a <h3> element with class = 'css-5pe77f'. The author name is a <p> element with class = 'css-hjukut'. You need to take a note of this and put that into the Python script coming later in this post.

**Step 2: repl.it**

Follow this step if you do not have a Python compiler in your computer. Go to repl.it, click "new repl" and then select "Python" as your language. Copy the Python script (from Step 3) and paste it in main.py

**Step 3: Python script**

You need to make only two changes in the script.

1. In "url = " provide URL of the webpage that you want to extract data from.

2. In "text1" and "text2" provide respective element names and class names. If you have more data columns to extract, you can add "text3, text4...".

Click "Run" in your repl.  You should see a csv file named "index.csv" in the left side of the screen. You can find the list of book titles and author names in this index.csv file. Mission accomplished!

And here is your script --