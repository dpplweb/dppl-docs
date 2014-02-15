---
layout: page
title: Homepage
permalink: /
readers: [publishers]
---

## Overview

There are a few different components to the homepage:

- Feature
- Sub-features
- Blog post
- Upcoming events
- Resources
- Guides section

Let's look at the Feature, Sub-features, and Guides first since these are can be edited directly through the CMS.

## Feature

The Feature area takes up the full-width of the homepage. It is an opportunity to to highlight a theme, a resource, or some other large scale event. The feature shouldn't change that much, maybe every other week.

There are two components to the feature:

1. Blurb
2. Hero image

### Blurb

The Feature blurb is positioned to be in the lower left of the feature area. It has three parts to it:

- Headline
- Blurb
- Link

The link can go to an internal page or an external one. If you are linking to a blog post or calendar listing on the site, be sure to remove `http://dppl.org` from the link. The link should start with "/". See the Links page for more details.

### Hero image

There are a few requirements for the hero image:

- Dimensions: 1400 x 634
- Highest quality available (ie no JPEG compression)

For the best results, it is a good idea to start with an image that is actually 2x the size (2800 x ). From that, the website create three versions of the image for desktop, tablet, and smartphone sizes. 

When you are naming hero images, please observe these naming conventions:

- Lower case 
- Space or hyphens in between the parts (I think hyphens are best for images)
- More descriptive file names are better than less descriptive
- Pin "hero" to the end of the file name too

Here's an example of shiny file name:

    adult-winter-reading-club-hero.jpg

### Updating the feature

1. Log in with a publisher account.
2. From Structure, click on "Home".

The features exist in a Matrix field. Whichever entry is listed as #1 appers on the homepage.

> **Tip:** You can stack up multiple features and resort them to change up the homepage feature easily.

From here, you can:

- Edit the first entry with the new text and image you have.
- Click on the plus sign button to add a new row, then click and drag the rows in a new order.

> **Remember**: To make the arrow appear after the link, type `&rarr;`

## Sub-features

Sub-features are edited a little differently. You don't go the Homepage to edit them. Instead, they are available under Assets. 

### Edit or add a sub-feature

1. Log in as a publisher.
2. From Structure, click on Assets.
3. Click on Edit or Add to the right of Homepage Sub-Feature

From here, you need to add the following things:

- Title: This is a required field, but only affects how the sub-feature is listed in the CMS
- Superhead: This appears above the text. There should be some consistency about how these are used.

    > **Note:** You should *not* type out the Superhead in Capitals. Type it like a regular title. The site makes it appear in small caps automatically.

- Blurb: The actual text of the entry. Try to be as economical as possible. I would suggest:

    - Abbreviate days of the week (Mon., Tues.)
    - Only say what is essential, let your link be the call to action

- Link text: By default this will be more. But this is your change to put in a strong call to action like

    > **Best Practice:** A strong call to action should indicate what the user is doing and why they should do it. Examples: Learn more, Sign up, Start exploring etc. Here's a [good blog post](http://blog.crazyegg.com/2013/07/24/call-to-action-examples/) to review.

### Ordering sub-features

Ordering the sub-features works a little differently. It uses a EE Plugin called Low Reorder. 

> **Tip:** Create a shortcut to Homepage subfeatures in your toolbar.

1. Click on Homepage subfeatures in your toolbar
2. Click and drag the entries to change the order.

Only two sub-features appear at a time. So whichever one is listed third *won't* appear on the home page. Much the homepage feature, you could swap sub-features in and out just by reordering them.

## Guides

The links under each Guide on the homepage can be edited on the homepage.

1. Log in as a publisher. 
2. From Structure, click on on Home.
3. Scroll down until you see Guides.
4. From here, you can edit the text in the Text field. Use a bulleted list to create the lists of links. 

Be careful not to reorder the entries here. The order here should reflect the navigation and the order of the pages in Structure. So, one change in any of those places, means changing things in the other. Capiche?

## Blog posts, events, resources

These three items on the homepage are all pulled dynamically from the CMS. A few quick notes thought:

- Blogs posts can be hidden from the homepage with the "Suppress from homepage" category for blogs.
- There is a SQL procedure that updates the featured status of events and needs to be run periodically.
- Resources just kind of happen.