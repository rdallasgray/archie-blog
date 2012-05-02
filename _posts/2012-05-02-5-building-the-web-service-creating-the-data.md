---
layout: post
title: "5. Building the Web Service: Creating the data"
description: "SQLAlchemy, models, templates"
category: archie
tags: []
date: 2012-05-02 10:17:23
---
{% include JB/setup %}
All the Archie webservice needs to do is provide a feed of ARML data to Wikitude's servers; the feed is used to define and place points of interest within a 'World' which will be available in the Wikitude phone app.

To make things simple and maintainable, it makes sense to define data models for the points of interest (and their media attachments, eventually). These can be used within a view template to complete the ARML feed.

Flask has bindings to [SQLAlchemy](http://packages.python.org/Flask-SQLAlchemy/) to provide simple and usable ORM functionality. Here's how the point-of-interest model was created:

{% highlight python %}
from archie import db

class Poi(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(255))
    description = db.Column(db.String(255))
    type = db.Column(db.String(255))
    waypoint_number = db.Column(db.String(255))
    co_ordinates = db.Column(db.String(255))
    thumbnail = db.Column(db.String(255))
    hi_res_image_url = db.Column(db.String(255))
    marker_icon_url = db.Column(db.String(255))
    
    def __repr__(self):
        return '<Poi %s>' % (self.name)
{% endhighlight %}

It can then be incorporated into an ARML template using the [Jinja2](http://jinja.pocoo.org/docs/) template engine. Settings for the World itself can be hardcoded in the template or (as I've done) set up in a the config file for the app.

The points of interest were derived from the points that had previously been added to the Wikitude.me service.

<img src="{{ BASE_PATH }}/assets/images/IMG_0227.PNG" width="49%"/>
<img src="{{ BASE_PATH }}/assets/images/IMG_0228.PNG" width="49%"/>

As well as co-ordinates, points were given names and descriptions which appear when clicked on in either the map or cam interfaces. Further formative evaluation followed, confirming some issues and raising new ones. It was still difficult to actually follow a path through the POIs in the map. Labels were too short to be useful, and the lack of distinguishing features made them difficult to tell apart.

####Next: Adding thumbnails