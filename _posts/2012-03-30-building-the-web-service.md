---
layout: post
title: "3. Building the web service"
description: "Generating ARML"
category: archie
tags: []
date: 2012-03-30 17:00:00
---
{% include JB/setup %}

The next rung on the Wikitude ladder is Wikitude Worlds, which offers two broad publishing options:

1. Use their [ARchitect Engine](http://www.wikitude.com/developer/architect) to create a simple interface using HTML and CSS, or

2. Provide [ARML](http://openarml.org), either by uploading a static file or dynamically by means of a web service.

Option 1 would offer more flexibility, but would be quite time consuming, and the end result would still have to run inside Wikitude's World Browser app; option 2 offered much shorter development turnaround, and allowed for custom icons for points of interest, as well as links to attached media. This would enable me to get to a next round of useful evaluation much more quickly.

####Platform

The next decisions to make were more interesting: where to host the webservice, and what platform to develop it on. For a while I entertained the idea of writing it in Java, just for the sake of the experience, but came to my senses reasonably quickly. Having little experience with Python, I decided to use the opportunity to learn some, and chose the [Flask framework](http://flask.pocoo.org). Flask is a microframework in the vein of web.py and Sinatra, and seemed apt to the task.

For hosting, I looked at Google Apps, EC2 and Heroku. I already have an EC2 account, so I wouldn't be eligible for the free level of service; Google Apps looked needlessly complex. So Heroku it was.

####Getting it running
Heroku had some [helpful documentation](https://devcenter.heroku.com/articles/python) on getting a simple Flask app running, and I had things working reasonably quickly. An initial stumbling block was the database: I'd intended to use SQLite, but Heroku doesn't seem to properly persist file-based data (there is effectively no file system).

####The database
Heroku's native RDBMS is PostgreSQL. It's supposed to be simple enough to transfer the contents of a local SQLite db upstream to their PostgreS, but I had trouble doing it in the Python environment -- it seemed set up to cater to Rails. So I decided the path of least resistance was to set up PostgreS on my local machine (a Mac running OS X 10.7). This wasn't simple, but luckily I'd done it not long before in order to get access to [PostGIS](http://postgis.refractions.net), which I needed to get OpenStreetmap data into [TileMill](http://mapbox.com/tilemill).

Once I had a local PostgreS, things went a bit more smoothly, although it took me a while to figure out how to access Heroku's db (the url to the database is only available through an environment variable, which is actually quite smart -- no storing usernames, passwords and hostnames in config files).

All in, it took about three hours to get the service from scratch to running and serving ARML.

####Next
More details.