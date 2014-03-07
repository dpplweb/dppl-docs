---
layout: page
title: Admin
permalink: /
readers: [admin]
---

## Caching

The site uses a module called [CE Cache](http://www.causingeffect.com/software/expressionengine/ce-cache) to cache (ie save) certain pages. Currently the site caches copies of:

- Homepage
- All Resources page
- Sidenav

There is a spreadsheet on Google drive that lists these out too.

### How it works

CE Cache uses a special tag in the template to indicate that the info should be saved. The tag looks like:

    {exp:ce_cache:it id="whatever" tags="whatever" seconds="amount of seconds"}

You can also escape parts of the template with:

    {exp:ce_cache:escape}

### Breaking the cache

If something isn't updating on a page after a change, it's usually because of the cache. There are a few triggers set up to automatically break the cache, but you can also do it manually:

1. Log in to CMS as admin.
2. Click on the CE Cache button in the toolbar.
3. Click on "View items" in the File row.
4. Click on "local".
5. From here browse for the item you want to break. You can either Delete item or Delete Children (ie everything in that section).

### Caching gotchas

Be careful with caching! It wreaks havoc with forms on the site, for instance. So, **never use caching on forms!** I also experienced a problem with trying to cache the `embed/head.html` template. For some reason blog posts wouldn't preview anymore with Better Workflow.

## Removing ghost drafts

Ever so often, the BetterWorkflow module doesn't clean up after itself as well as it should. If you have entries that have two Draft statuses and you cannot delete them, follow these steps:

1. Go the site and write down the ID number for the entry with the phantom statuses. 
2. Log in to the host account.
3. Go to Databases.
4. Open up the phpMyAdmin for the site's database.
5. Enter the database password.
6. Click on the database for the site.
7. Find the `exp_ep_entry_drafts` table and click on it.
8. Find the row with where `entry_id` equals the number you wrote down above.
9. Click on Delete for the row.

This will clear the status. Now you need to go back to the site and remove the post (or do whatever you planned to do with it).

## Backups

The site is automatically backup up using three methods:

- An export of the entire SQL database, via cronjob, stored on the Webfaction server
- An export of the enitre database, along with a copy of all the files, in a tarball file, executed by SafeHarbor, stored on the Webfaction server.
- A copy of the same SafeHarbor tarball, stored on S3.

### Cleaning up backups

If left to their own devices, the backups would pile up, which isn't a good idea. There are two things that clean up backups:

I have created a cronjob that runs every Sunday that removes the any backup that is 21 days or older from the site. The cronjob runs a simple shell script called cleanbackups.sh.

I have also created an Amazon s3 Lifecycle rule that removes backups older than 21 days.

## Removing a staff person

1. If they manage pages on the site, update each page with a new page manager.
2. Update the staff channel (see the Staff channel page for info)
3. Remove the user account

A quick note on removing the user account. It might be a good idea to wait until a replacement comes on board to remove the member account. It will be much easier to transfer ownership if the old account still exists.
