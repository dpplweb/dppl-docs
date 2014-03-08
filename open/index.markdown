---
layout: page
title: Open pages
permalink: /
readers: [admin]
---

## Overview

There are a number of pages that are in the Open channel. This means that the page is just a blank box for putting custom html, css, etc. These pages have to be created, edited, and maintained by hand.

These pages include:

- Notifications
- Card eligbility map
- Library card app for businesses and schools
- Brick order form
- Donation form
- Volunteer form

## Tracked with Git

The open pages are all kept in the same Git repository with the rest of the site's code. This ensures that the files are easily maintained and tracked. The main thing to keep in mind is that any of the open pages should edited **locally** first, not directly through the site.

## Dynamically loading javascript

One thing that you might notice on some of the open pages is that there is special javascripts that need to be loaded. Because of the way these pages are set up, though, you can't just drop a jQuery script onto the page. jQuery won't be loaded yet! So, you'll often see something that looks like:

    <script>
        window.onload = function(){
            var brick_script = document.createElement('script');
            brick_script.src = '/assets/bricks/js/bricks.js';
            document.getElementsByTagName('body')[0].appendChild(brick_script);
        }
    </script>

This script at the bottom of the page dynamically loads the external script.

## Editing an open page

Here are the steps to edit an open page.

1. Go to your local environment
2. Find the `open_pages` directory
3. Open the page.
4. Commit the changes, push to Github.
5. Log in to the CMS.
6. Find the open page.
7. Copy and paste the code.

## Print forms

There are a number of "forms" on the site that I call "print" forms. These forms are not created or maintained through the CMS. Instead, they are hand coded and are only meant to be printed out.

There are special CSS rules in the Sass files to format these pages.

## Bricks

The plaza brick order form and "find a brick" pages are also open pages. The "find a brick" page has a few other components located in `assets/bricks`:

- `css/style.css`
- `data/bricks.json`
- `js/bricks.js`

If there are new bricks added to the plaza, they'll need to be added to the `bricks.json` file. JSON is a file format that looks like:

    {"key" : "value"}

A typical entry in the `bricks.json` file looks like:

    {"id":"1","inscription":"1998 David and Laura Corba","location":"P6"}
