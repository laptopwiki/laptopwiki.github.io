---
layout: wiki
title: Create New Post
description: "Create new post in Laptop Wiki"
contributors: ['nonkerdoob','horizon3902']
---

# Creating a new post

Content on laptop wiki are written using Markdown and it's properties defined using YAML front matter. This guide covers how to create a new post, set it's properties and how to submit it. 

To create a new submission, you have to fork the ``main`` branch of the Github repo this wiki is served from. Add the post and create a pull request.

Creating a fork is fairly simple, just look for the fork button and click on it, Github will guide you through the rest. You need to fork it since the wiki repo is not directly editable. You will essentially be making a copy of the repo where you will be making the edits.

A pull request submits your edits for review before it is merged with the main repo.

## Navigation Structure

This wiki is categorized by sections, pages and its children. Sections are top level classification grouping similar posts together. Pages display the posts submitted to this wiki, they can have child pages.

```
+-- ..
|-- (Site root)
|
|-- _sectionname
|   |-- page-name.md
|   |-- page-name
|   |   |-- (child-pages.md) 
|   |   |-- child-page-name.md
|   |   |-- child-page-name
|   |   |   +-- (child-pages.md)
|   |   +--
|   +-- (pages.md)
|-- (Site root)
+--
```

You can see how it behaves in the side bar and breadcrumbs.

![image](https://user-images.githubusercontent.com/100846697/164708701-61192303-8fd4-45c7-ab92-2f1312c7a4a0.png)

Red is a section, teal is a page, and if it is dashed, it is a child. Pages can be nested within pages.

#### Example
```
+-- ..
|-- (Site root)
|
|-- _laptops
|   |-- Asus.md
|   |-- Asus
|   |   |-- Zephyrus-G14.md
|   |   |-- Zephyrus-G14
|   |   |   +-- 2020
|   |   +--
|   +-- 
|-- (Site root)
+--
```

You need to navigate to the appropriate directory in the repo. If it is a child page, there should be a corresponding directory with the name same name as the parent page. If the parent page is not yet made, create it with this guide.

In the above sample, we know the post belongs in ``Laptops`` section, and that it is a child of ``Zephyrus G14`` which in turn is a child of ``Asus``. We navigate to ``_laptops/Asus/Zephyrus-G14/`` to add our new entry.

To make a directory for the child pages, preceed the name of your post with the parent page's file name. If the directory ``Zephyrus-G14`` doesn't exist we can create it by naming the file ``Zephyrus-G14/2020.md``.

## Creating the file

While in the directory click on ``Create New File``. An empty text editor courtesy of Gihub will open. Name the file a shorter version of the post title. Keep in mind, this act as the permalink too.

## Writing the post

Copy this template to the editor.

#### Template
```markdown
---
layout: wiki
title: Post Title
description: "Description"
parent: Parent post
grand-parent: grand-parent post
ancestor: ancestor post
contributors: ['github username'] 
---

# Post Title

Your content goes here

# Refereneces

Footnotes

```

Start writing or paste your pre - edited content between ``# Post Title`` and ``# Reference``. Link your references under the References heading with the syntax ``[Example](https://example.com){:target="_blank"}``. You can use [Markdown Cheat Sheet]() for help in formatting your content.


## Cleanup

The top part of the template consists of front matter that informs Jekyll how to process the file appropriately. Things you need to change are 

### ``title``

This is what will appear in the side bar and bread crumbs. You are not required to use full title here rather a short one thats appropriate for navigation.

### ``description`` 
#### Optional

You can give your post a description. This helps with SEO.

### ``parent``

If the post is a child, use the parent pages title here. Remove the line if not applicable.

### ``grand-parent``

If the parent page is a child too, use the title of the grand - parents page. Remove the line if not applicable.

### ``ancestor``

If the grand parent page is a child too, use the ``ancestors`` to mention a title of the page that is unique. It doesn't have to be the direct parent of the grand - parent page.

### ``contributors``

It is an array, enter your github username inside the brackets with single quotes. If there are multiple contributors use `,` to separate them. This post has multiple contributors which looks like ``['nonkerdoob','horizon3902']`` in the front matter.

### References and Footnotes

Below the references heading, link your references using the markdown format ``[example](https://example.com){:target="_blank"}``. Square brackets contain the text that will be hyperlinked, paranthesis for the url and ``target="_blank"`` so that the link opens in a new window when a user clicks it.

Footnotes can be made using ``[^1]`` near the text, and then referencing ``[^1]: Reference`` below the Footnoes sub - heading under the Reference heading.

# Pull Request

Once you are done editing, commit the changes and make a pull request with the ``main`` branch.

