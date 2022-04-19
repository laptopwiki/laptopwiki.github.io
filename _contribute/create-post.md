---
layout: wiki
title: Create New Post
description: "Create new post in Laptop Wiki"
contributors: ['nonkerdoob','horizon3902']
---

# Creating a new post

Content on laptop wiki are written using Markdown and it's properties defined using YAML front matter. This guide covers how to create a new post, set it's properties and how to submit it. 

To create a new submission, you have to fork the ``main`` branch of the Github repo this wiki is served from. Add the post and create a pull request. 

## Taxonomy

This wiki is categorized by sections, pages and sub pages. Sections are top level classification grouping similar posts together. 

Pages display the posts submitted to this wiki. It can be or have a sub page. Sub-pages are children of a page.

You can see this in action on top of post tiles in the form of breadcrumbs.

![image](https://user-images.githubusercontent.com/100846697/164103343-11858683-5730-4786-bc4b-36c610b5b809.png)

In the above image, the red underline is a section. The teal underline is a page, and if it is dashed, it is a sub-page.

Looking at it in conjunction with the side bar makes it clearer.

![image](https://user-images.githubusercontent.com/100846697/164109319-d8ddd7b7-4aff-456e-9e37-1f0d186c1725.png)


You have to decided which section the post will go to and if it is going to be a sub - page.

## Creating the file

This guide will be using above entry as an example. It needs to be stored in ``_laptops/asus/zephyrus-g14/`` with the file named ``2020.md``. Directories containing markdown file that start with an underscore are sections. ``Laptop`` section's directory will be ``_laptops``. The rest of the directory matches the name of the parent pages. If the directories don't exist yet, read [Creating A Sub Page Directory]() and [Creating a Section]().

Click on ``Create New File``, and name the 

