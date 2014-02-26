---
layout: page
title: Images
permalink: /
readers: [publishers, editors, bloggers]
---

## Overview

Here you'll learn about some general principles about using images on the site, getting good cover images, and dhow to find good images for blog posts.

## Some general thoughts about images

- No image is better than a bad image
- Fewer images are better than more images
- Use images fairly and provide attribution when possible.

> **Note:** We have generally agreed that catalog images don't need to be credited.

## Cover images
Here's how to get a good image from the catalog. Bibliocommons currently uses images from a service called Syndetics. So, to get this image, do the following:

1. Go to the catalog.
2. Find an item and view it.
3. Right click over the image and view it in a new tab.

At this point you should see a long url and the cover image. A book typically looks like:

    http://www.syndetics.com/index.aspx?isbn=9780545265355/MC.GIF&client=###-###-####&type=xw12&oclc=

A video might looks like:

    http://www.syndetics.com/index.aspx?isbn=/MC.GIF&client=###-###-####&type=xw12&oclc=&upc=899975002962

The two main components are the isbn number (or the upc number) and the size switch (the `MC` bit of the url). In both of these examples you see a medium sized image. If you change `MC` to `LC` you get an image that is about 300px wide.

### Open Library Book cover api

If you don't find a cover in the catalog, you could also try the [Open Library Book Cover api](https://openlibrary.org/dev/docs/api/covers
). Here is a basic example:

    http://covers.openlibrary.org/b/isbn/9780545265355-L.jpg

The `L` at the end of the URL is a size parameter. If you change is to `S`, you would get a smaller image.

## Finding good images

I think it is important that when we use images on our blog that we give credit and attribution for them. It is also important that we do our best not to steal the intellectual property of others. There are two main ways to find images for you blog posts that we'll look at below.

### Creative Commons licensed images
I recommend that you look for and use Creative Commons licensed images in your blog posts. What is Creative Commons? CC is a license that creators can attach to their works that allows for varying degrees of reuse. There are a few different types of CC licenses you’ll find online. The main thing is that any CC image requires attribution.

### Find CC images on Flickr:

1. Go to http://www.flickr.com/search/advanced/
2. In the Creative Commons section, check off:
3. “Only search within Creative Commons-licensed content “
4. If you want to find things to photoshop, etc, check off “Find content to modify, adapt, or build upon”
5. Go back up and enter your search terms

> **Try this:** http://www.flickr.com/search/?q=computers&l=cc&ct=0&mt=all&adv=1
Notice the “l=cc” bit in the URL? That tells Flickr to search CC images. Yes, you can start doing URL hacking and just modify your URLS to do searches. #geeklife

When you find an image you like, click on it and then:

1. Click on the overflow button (looks like three horizontal dots) and select “Download / All Sizes”
2. You’ll see license information first, followed by a series of download options. Download the highest quality / largest image available. This will ensure that the image looks good on the site. Unless you know if will be a right aligned image, then choose at least 1024 x 768 if available.
3. Click your back button to go back to the image. Now click the Share button (a box with an arrow launching out of it).
4. Click on the chain icon to get a link to the photo. 
5. Add the following to the bottom of your blog post: Photo: URL you just copied.

### Find CC images on Google image search:

1. Do a google search for a term.
2. Click on “Images”
3. Click on “Search Tools”
4. Under “Size” select: Large for full width images, Medium for right aligned images
5. Under “Usage Rights” select the license that suits your needs.
6. Click on the image.
7. Click on “View image”
8. Right click over the image and save the image to your computer.
9. Click the back button
10. Click on “Visit page” and copy the URL.
11. Don’t copy the URL to the image itself. Copy the URL to the page where the image resides.
12. Add the following to the bottom of your post: Photo: URL you just copied.

### Giving attribution

It's mentioned above, but don't forget to give attribution for the CC image you're using.

## Editing images

If you need to edit an image, crop it or resize it, I highly recommend Paint.net. Ask IT to have it installed on your computer.