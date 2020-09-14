**************
Implementation
**************

Here you can find an overview over all the current screens to get an idea
how the Anounz app works.

First, for a better understanding, the terminology of the app.

Terminology
===========

============  ======================================================================
Term          Description
============  ======================================================================
Announcement  The parent object, contains the configuration data of the announcement
Document      Child object, contains the HTML for an announcement.
Recipient     A user of your website/-application that receives the announcement
============  ======================================================================

The Announcement has a zero to many relationship to the Document, as you could have no HTML stored in the Anounz App
(you only need the Announcement for administrating) or you could have multiple HTML files to display for example
a wizard.

How it works
============
At first you create a new Announcement in the Anounz App (via the Announcements Screen).
There you can define the name,the date range and if the announcement is optional or mandatory via the
blocking attribute (the logic needs to be implemented in your own website/-application).

Now it's time to add some content to the announcement. Therefore you switch to the Documents Screen
and add a new Document, where you can insert some magnificent HTML/CSS/JS code.

The announcement is now ready for you to grab via the public API, but you need to create an
API Key first to connect your website/-application to the Anounz App.
You can create such a key in the Settings.

Please be aware, that you have to store the generated key somewhere safe outside the Anounz app
as it disappears from the app on leaving the page and can not be retrieved.

Now you can access the following three public API Endpoints [https://api.anounz.io] with the API Key in the
request header ("X-API-KEY"):

=======  =================================  =============================================
Method   Endpoint                           Description
=======  =================================  =============================================
GET      /api/v1/currentAnnouncements       Get all the current announcements
GET      /api/v1/seen                       Check if recipient has seen an announcement.
POST     /api/v1/seen                       Adds a recipient to an announcement
=======  =================================  =============================================

Screens
=======

Dashboard
---------
The Dashboard Screen (Home Screen) gives you an overview over all the current announcements.
For each announcement it shows some interesting stats about the recipients and a time graph of
when the recipients have seen the announcement.

Announcements
-------------
The Announcements Screen shows an overview over all your announcements, where you can
manage (create, update, delete) them

Documents
---------
The Documents Screen lets you manage the documents of an announcement

Recipients
----------
The Recipients Screen displays all the recipients of an announcement.
You can also add a recipient manually or remove him from an announcement.

Settings
--------
The API Settings are the only settings implemented yet.
There you can generate an API Key to connect your website/-application with the Anounz App.

Test (Dev only)
---------------
This screen is for testing purposes only.
It allows you to communicate with the public API without a website.