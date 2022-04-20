---
layout: wiki
title: Create New Post
description: "Create new post in Laptop Wiki"
contributors: ['nonkerdoob','horizon3902']
---

# Creating a new post

Content on laptop wiki are written using Markdown and it's properties defined using YAML front matter. This guide covers how to create a new post, set it's properties and how to submit it. 

To create a new submission, you have to fork the ``main`` branch of the Github repo this wiki is served from. Add the post and create a pull request.

Creating a fork is fairly simple, just look for the fork button and click, Github will guide you through the rest. You need to fork it since the wiki repo is not directly editable. You will essentially be making a copy of the repo where you will be making the edits.

A pull request submits your edits for a review before it is merged with the main repo.

## Taxonomy

This wiki is categorized by sections, pages and sub pages. Sections are top level classification grouping similar posts together. 

Pages display the posts submitted to this wiki. Sub-pages are children of a page.

You can see how it behaves in the side bar and breadcrumbs.

![image](https://user-images.githubusercontent.com/100846697/164338263-df268967-5e38-401a-900c-b642cc84b4e6.png)

Red is a section, teal is a page, and if it is dashed, it is a sub-page. Pages can be nested within pages.

With this in mind, you will have to decide where you are going to place your post.

## Creating the file

We need to navigate to ``_section/page/sub-page/../`` to add your entry. If it doesn't exist read [Creating A Sub Page Directory]() and [Creating a Section](). 

In the above sample, we know the post belongs in ``Laptops`` section, and that is a sub - page of ``Zephyrus G14`` which in turn is a sub - page of ``Asus``. We navigate to ``_section/Asus/Zephyrus-G14/`` to add our new entry.

Once in the correct directoy, click on ``Create New File``. An empty text editor courtesy of Gihub will be opened. Name the file a shorter version of the post title.



