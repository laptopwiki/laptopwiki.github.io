# Create New Section

---

Sections can be seen as equivalent to categories. Each section aims to fulfill a different purpose. The section you are currently on is called ``Contribute`` and serves as a guide on how to make the wiki a better place. 

## Creating the directory

Sections are served from a folder where markdown files are stored. They are created in the root of the site. 

### Name the category

To get started, navigate to the ``main`` branch of the wiki repository on Github. Click on add new file.

You will be greeted with a text editor. Name the file ``_categoryname/categoryname.md``. The directory name and the file name should match and should contain no spaces. Preceeding ``_`` underscore and the file extension ``.md`` are important.

### Add Front Matter

Copy and Paste this onto the top of the file. Replace ``categoryname`` with the name of your category. If you want, add a description too between the double quotes ``""``.

```
---
layout: collection
title: Category Name
description: "Category Description"
nav_exclude: true
permalink: /categoryname
---

# Category Name (Can be different from the title and 
---
```

### Save Changes

Scroll Down and click on ``Commit new file`` to save your changes.

## Configuring the category

After creating the directory and index, you have to tell Jekyll that the folder is a section. Navigate to the root of the branch and look for the file named ``config.yml``.

### Locate the collection array

In Jekyll, sections are defined as a sequence / array called as collections. 
