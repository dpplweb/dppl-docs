---
layout: page
title: Members
permalink: /
readers: [admin, publishers]
---

## Overview

Whether you're a blogger, an editor, or an admin, you're a Member as far as the CMS is concerned. This document looks at the member groups we have and how to add or remove a member.

## Member groups

Member groups define the different roles for members on the site. Currently, we have 5 groups:

- Blogger
- Editor
- Editor Plus
- Publisher
- Super admin

Let's look at what the groups can and cannot do. They are arranged from most restrictive to least restrictive permissions. Each group inherits the permissions of the group before it.

Before we start, one quirk of Expression Engine is that all member groups need access to Modules so that they can use Structure. It's annoying, but it's just the way it is.

### Blogger

- Add/edit their own blog posts
- Upload files to following directories:
    - Blog posts
    - Calendar uploads
- View/edit content from the “Blog” channel only

### Editor

- Can do everything the Blogger does
- Can edit their own pages
- Upload to the following additional directories:
    - General
    - Uploaded documents
- Can view / edit the content in the following channels:
    - Basic
    - Blog post
    - Resource
    - Rows
    - Subject
    - School
    - Tax forms

### Editor Plus

- Can do everything the Blogger and Editor does
- Does not need publication approval
- Upload to the following (additional) directories:
    - Board documents
    - Job descriptions
    - User uploads
- Can view/edit content in the these additional channels:
    - Form
    - Job

### Publisher

- Can do everything the Blogger and Editor does
- Add/edit any page
- Add/edit any channel
- Upload to all directories including:
    - Staff photos
- Can approve pages for publication

### Super admin

- Everything the Blogger, Editor, and Publisher does
- Add/edit members, member groups
- Access to site configuration and management

## Using these groups

In general, you don't want to give someone more permissions than they need to do their job. Most staff on the site should be fine with being a "blogger." Editor and Editor Plus should be reserved for people who are part of the content team on the site.

Be careful with the Editor Plus. This group has access to the user submitted form information, including job application info. So this needs to be reserved for a very limited number of people.

> **Best practice:** In general, it is best to not log in to the site as the super admin. Only login as super admin if you have to do a super admin thing.

## Editing a current member

1. Log in as the super admin
2. Go to Members >> View all
3. Click on a username to edit the member.

Staff profiles, photos, etc that appear on the website and on the blog have **nothing** to do with members on the site. See the docs about the Staff channel for editing that content.

## Removing a current member

1. Login as the super admin
2. Go to Members >> View all
3. Use the checkboxes on the right to select the member and delete.

> **Remember:** You will need to update the person's profile in the Staff channel too.

## Adding a member

1. Add the username and password to the user accounts spreadsheet.
2. Log in as the super admin.
3. Go to Members >> Register
4. Fill in the required fields, including a **strong** password.
5. Select the appropriate group.
6. Contact the person with their information.