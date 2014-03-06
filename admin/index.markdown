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