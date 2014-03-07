---
layout: page
title: Forms
permalink: /
readers: [publishers, admin]
---

## Overview

There are two components to forms on our site:

- Forms created with the Freeform Pro module
- Pages in the Form channel that "display" the form

This set up allows you to have custom text around the form itself.

## Removing form entries

Periodically form entries should be cleaned up and removed:

1. Login to the CMS as a publisher or editor plus.
2. Go to Forms.
3. Click on the Submissions button.
4. Check the ones you want to remove and delete them.

## Editing a form

1. Log in to the CMS as a publisher
2. Click on Forms in the toolbar (don't see it, got to Modules >> Freeform Pro)
3. To edit the layout of the form, click on the pencil under Composer. To edit the form preferences, click on the gear under edit.

## Adding a form

Adding a new form is a little more complicated.

1. Login to the site and go to Forms.
2. Click New Form.
3. Make sure the Form Type is Composer.
4. Fill in the rest of the details.
5. Set the Default Status to "Open"
6. Add email addresses to the Admin Notification Email Address field.

From here, you either need to create form fields, or start editing the form in Composer.

>**Best practice:** Try to resuse form fields as much as possible. More fields means a more bloated database.

At this point, you probably want to create a notification template locally then:

1. From Forms click on "Notifications."
2. Click on New Notificiation
3. Paste in the form you created.
4. Go back to the form settings.
5. Select the notification template.

Consult Solspace's Freeform Pro documentation for more help: [http://www.solspace.com/docs/freeform/](http://www.solspace.com/docs/freeform/).

Now, you need to create a new page for the form:

1. From Structure, add a child page, add it to the Form channel.
2. Open the page, put in the title (I like for it to match the form title more or less).
3. Find the form section, choose the form you created above. Enter a "thank you" destintion.
4. Create the Thank you page.
5. Click on the Structure tab and set "Hide from nav" to Yes.

>**Tip:** For thank yous, I like them to be child pages of the form. Also you have to enter the full path to page (ie include the parent page, the current page, then the child thank you page).

## Form notifications

I crreated custom notification templates for the forms. They are all located in the site's Git repository under `assets/templates/form_notifications`. Sure sure to edit these templates locally through Git and then copy/paste into the site.

Also, good too keep in mind that HTML email is pretty basic, and it's better to use tables, sadly.