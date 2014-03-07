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