---
layout: page
title: Events
permalink: /
readers: [publishers, editors]
---

## Overview

The Events channel in the site get populated by an import from the Evanced Calendar (see the section below called Calendar Import for a more technical discussion). Every night, the site pulls the 300 events from Evanced through it's XML feed.

Events that already exist on the site are updated, new ones are created. **Deleted events are not removed automatically.** So, see the section below on deleting events.

## Editing events

Only publishers have the ability the edit (and delete) events manually on the website. Here's how to edit an event.

1. From Structure, click on Edit next to Calendar in the sitemap.
2. Search for the event(s) you want to edit.
3. Click on the name of the Event.

From here, you can edit any of the information that has been pulled from Evanced, including categories. Of course, any changes you make here, do not get sent back to Evanced.

## Editing categories

Only the admin account has the ability to edit categories. If there is a need to remove or edit categories, you do the following:

1. Log in as the admin account.
2. Click on Categories from the toolbar.
3. Choose "Add/Edit Categories" next to "Event audience" or "Event type"

> Note: For an event type or audience to appear on the calendar, it **has to be listed under Public**. Private categories and those not listed under Public will not display on the website calendar.

Once you have chosen which type of category to edit, you can do a number of things like:

- Reorder entries with the blue arrows
- Edit a category title
- Delete a category

Just remember that anything that is listed under public (at least with the event types) will be visible on the website.

## Deleting events
If you need to delete an event from Evanced, there are few steps that you need to take to make sure that everything works the way it should.

1. Write down the Evanced ID number for the event that you are deleting. (Look at the URL in Evanced, it’s whatever comes after ID=#####)
2. If you are creating a new event, go ahead and create that one. Write down the Evanced ID number for the new event.
3. Delete the event from Evanced.
4. Send an email to Brodie or Heather, send the following info:
    - Event title
    - Date
    - Evanced ID number(s)

### For Publishers

Deleted events need to be either removed or updated on the website too.

1. Go to Structure, click on “Edit” next to the calendar.
2. Search for the event.
3. Double check the date.
4. Select the item with the checkbox on the right.

For duplicate events, do the following:

1. Open the event.
2. Double check the ID number. Make sure it matches the one that needs to be deleted.
3. Close the event form.
4. Select the event and delete it.

> **Tip**: The site’s internal ID number is different from the Evanced ID number mentioned above.

## Calendar import

No events are created in Expression Engine — instead, they’re imported from Evanced, nightly, via a cronjob, which executes a DataGrab command.

DataGrab reads the a custom version of the Evanced XML feed of the next 300 events (nb: this isn’t proper RSS, it’s just XML), and for every new `<item>`, it’ll create a new entry in the Event channel. For extant entries, it’ll update the entry with any data that’s been changed in the XML feed. 

The DataGrab configuration — how the XML fields get mapped to the fields in the EE system — are specified in the DataGrab admin panel. And you can change them. However, you can’t change the feed URL in the interface. To do that, you have to hack a field in the database. Be careful, though, because it’s not as easy as changing the entry in a text field. It’s stored in a JSON object that includes a field for the length of that string. So you’ll need to change that as well.

### Custom XML

> **Warning!** It is SUPER DUPER important that the customxml files are NEVER removed from Evanced. If they are missing, the calendar import will not work.

There are two Evanced files that generate the custom xml file for DataGrab:

- `lib/customxml.asp`
- `lib/common/customxml.inc`

The main change is to the `customxml.inc` file. The `date2` field was converted to show the event date and time using the ISO-8601 date/time format:

    YYYY-MM-DDTHH:MM-6:00

That last bit is an offset for UTC time (ie this tells the import that this is Central time zone time).

This hack allows us to sort calendar entries using ExpressionEngine's built-in calendar channel and entry tags.

The import url currently looks like: 

    http://calendar.dppl.org/evanced/lib/customxml.asp?nd=300&dm=exml

This grabs the next 300 events and display an "extended xml" format with the modification mentioned above.

### Categories

DataGrab reads the data in the agegroup field and maps it to categories in the Event Audience group. If it finds a string in that field that doesn’t match a category, it’ll create one with that name. 

It does the same thing with the eventtype field and the Event Type category group.

### Featured entries

The only hack around this import is that DataGrab doesn’t support the mapping of a boolean field into a particular status. (It does support setting the status dyanmically on import, but the import field needs to match the status name exactly.) To get around this, I’ve set up this hack:

Each entry has a Featured? field, which is 1 or 0 depending on the value of the import field
There’s a stored procedure (aka “routine” in phpMyAdmin parlance) that updates the status of each record if the Featured? field is 1

But that stored procedure doesn’t run automatically yet. I’m sure this is possible via cronjob, I just haven’t figured it out yet. For now, you’ll need to run it manually once in a while (once a week should be fine).

### How Calendar data gets rendered with JS

Because the default Calendar module in Expression Engine doesn’t support the inclusion of custom fields (probably because the query necessary to do so would be heinous) I had to get creative with how the data got shown on the page. 

There are three kinds of calendar views:

- By month
- By date
- Default (next three weeks)

And for each of those, the view can be unfiltered, i.e. showing events of all categories, or it can be filtered down to show only events of a certain age group, or type. (Or both, by chaining URL segments, but the interface doesn’t indicate this is possible.)

When a month page loads, here’s what happens:

1. The {exp:calendar:entries} tag outputs the days in the month, along with a list in each day of all the events that day.
2. The jQuery makes an AJAX call to /calendar/events/ (with the relevant dates indicated in the query string), which returns a large JSON object full of all the metadata associated with all events shown on the page.
3. It iterates through all those events and slots in the data accordingly.
4. It does a bunch of other stuff, like set the h1, the navigation buttons, etc.

When a day view loads, same thing, except just for one day.

When the default view loads, a lot of extra things happen:

1. First off, the page outputs {exp:calendar:entries} twice — once for the current month, once for the next month. 
2. Then the JS removes all weeks before today.
3. It collapses the week at the end of the current month and the week that starts the next month into one line. (If necessary.)
4. It removes all weeks beyond the 3 we want.
5. It sets a gray background color for all days in the past.
6. It alters the h1 and navigation buttons.

The JSON object that returns the data makes use of a very straightforward plugin that just returns data as structured JSON instead of text.

It’s worth noting that there’s a Solspace module out there for improving Calendar functionality, but I have no idea how much of the stuff I wrote is covered by it. Worth looking into in the future.
