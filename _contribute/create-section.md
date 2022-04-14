---
layout: wiki
title: Create Section
description: "Create a new section on Laptop Wiki"
contributors: [nonkerdoob]
---

# Create New Section

Sections can be seen as equivalent to categories. Each section aims to fulfill a different purpose. The section you are currently on is called ``Contribute`` and serves as a guide on how to add content to the wiki.

## Creating the directory

Sections are served from a directory where markdown files are stored. They are created in the root of the site. 

### Name the section key

The section key will be referred to as ``sectionkey`` for the purpose of this guide. Your key should closely match the section name.

To get started, fork the ``main`` branch of the wiki's repository on Github. Click on add new file.

You will be greeted with a text editor. Name the file ``_sectionkey/sectionkey.md``. 

This will create a directory called ``_sectionkey`` and file called ``sectionkey.md``.

The directory name and the file name should match and should contain no spaces. Preceeding ``_`` underscore and the file extension ``.md`` are important.

### Add Front Matter

Copy and Paste this onto the top of the file. Replace ``sectionkey`` with the key of your section. If you want, add a description too between the double quotes ``""``.

```yaml
---
layout: collection
title: section Name
description: "section Description"
nav_exclude: true
permalink: /sectionkey
---

# section Name (Can be different from the title and permalink)

---
```

### Save Changes

Scroll Down and click on ``Commit new file`` to save your changes.

## Configuring the section

After creating the directory and index, you have to tell Jekyll that the folder is a section. Navigate to the root of the branch and look for the file named ``_config.yml``.

> &#9888; Do not use tab for indendation in the config file, use space instead.

### Locate the collection array

In Jekyll, sections are defined as a sequence / array called collections. We need to add a new entry that defines the collection and it's metadata. 

Press ``Ctrl+F`` or ``Command+F`` if you are on a Mac to bring up the search function. Type in ``collections:``. It should bring up a search result that looks like this.

```yaml
collections:
  # Define a collection named "guides", its documents reside in the "_guides" directory
  guides:
    permalink: "/:collection/:path/"
    output: true
  # Define a collection named "contributes", its documents reside in the "_contribute" directory
  contribute:
    permalink: "/:collection/:path/"
    output: true
```

### Add the new section

To add your new section, replace the ``sectionkey`` with the name of your key and place it according to the order it should appear on the Laptop Wiki side bar.

```yaml
  # Define a collection named "sectionkey", its documents reside in the "_sectionkey" directory
  sectionkey:
    permalink: "/:collection/:path/"
    output: true
```

For the purpose of this guide I will be creating the section with the key ``laptops`` and place it between ``guides`` and ``contribute``. The final output will look like this.

#### Example
```yaml
collections:
  # Define a collection named "guides", its documents reside in the "_guides" directory
  guides:
    permalink: "/:collection/:path/"
    output: true
  # Define a collection named "laptops", its documents reside in the "_laptops" directory
  laptops:
    permalink: "/:collection/:path/"
    output: true
  # Define a collection named "contributes", its documents reside in the "_contribute" directory
  contribute:
    permalink: "/:collection/:path/"
    output: true
```

### Configure the theme to use the section

Next look for the sequence named ``just-the-docs``. It should have a sub sequence called ``collections``.

```yaml
just_the_docs:
  # Define which collections are used in just-the-docs
  collections:
    # Reference the "guides" collection
    guides:
      # Give the collection a name
      name: Guides
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
    # Reference the "contribute" collection
    contribute:
      # Give the collection a name
      name: Contribute
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
```

We need to add our section here, replace ``sectionkey`` with the key and add it matching the order it should appear on the side bar.

```yaml
    # Reference the "sectionkey" collection
    sectionkey:
      # Give the collection a name
      name: section Name
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
```

Using our previous example of ``laptops`` it should look like this -

#### Example
```yaml
just_the_docs:
  # Define which collections are used in just-the-docs
  collections:
    # Reference the "guides" collection
    guides:
      # Give the collection a name
      name: Guides
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
    # Reference the "laptops" collection
    laptops:
      # Give the collection a name
      name: Laptops
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
    # Reference the "contribute" collection
    contribute:
      # Give the collection a name
      name: Contribute
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
```
### Save Changes

Scroll Down and click on ``Commit changes`` to save your changes.


## Fin
The new section should now be added. Open a pull request detailing why you think the section is important.
