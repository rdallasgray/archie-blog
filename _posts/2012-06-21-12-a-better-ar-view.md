---
layout: post
title: "12. A better AR view"
description: "Scraping the Canmore photo archive"
category: archie
tags: []
date: 2012-06-21 15:35:39
---
{% include JB/setup %}
In the previous posts I'd acknowledged that using the AR camera view in tandem with a map view didn't add much use value to the prototype app. I'd also considered the two test subjects' interest in historical images of nearby locations, and wondered if it might be possible to use the [Canmore](http://canmore.rcahms.gov.uk) photo archive as a source of material.

Well, I've now implemented the idea, and it works quite well.

![Canmore via ARchitect]({{ BASE_PATH }}/assets/images/Canmore_01.jpg)

The core of the app is a back-end using [Sinatra](http://www.sinatrarb.com), running on [Heroku](http://heroku.com), which accepts a request in the form /latitude/longitude/radius. The app then searches Canmore on the Ordnance Survey grid reference for the given co-ordinates, and returns a list of index numbers. The front-end of the app can then asynchronously request images and other details for each index number (including the precise location of the site photographed), and place them in the AR display.

Several problems had to be solved for this to work; firstly, it is not trivial to convert longitude/latitude to OS grid references and vice-versa. Most modern location services (including GPS) use the [WGS84 datum](http://en.wikiedia.org/wiki/World_Geodetic_System) standard for geodetic projections; the OS uses the OSGB36 datum, which it considers a better fit for Britain. Within that datum, the OS locates points by [eastings and northings](http://en.wikiedia.org/wiki/Easting_and_northing) rather than latitude and longitude, and creates a two-letter prefix which locates squares of side 100km.

So the task is to: convert WGS84 co-ordinates to the OSGB36 datum; convert the resulting co-ordinates to eastings and northings; and convert the eastings and northings to a final grid reference. The OS provides good [guidelines](http://www.ordnancesurvey.co.uk/oswebsite/gps/docs/A_Guide_to_Coordinate_Systems_in_Great_Britain.pdf) for carrying this out, but the maths is frankly hairy. 

####Silva
I found a [Ruby library](http://harrywood.co.uk/maps/osgbconvert.rb) by Harry Wood (from an original in JavaScript by [Chris Veness](http://www.movable-type.co.uk/scripts/latlong-gridref.html)) which almost did what I needed (it didn't back-convert grid references to WGS84 co-ordinates), and from there I was able to build a new Ruby Gem, [Silva](http://github.com/rdallasgray/silva), in nice, clear, properly object-oriented Ruby, with maths checked against the OS guidelines, and fully unit-tested.

Using Silva, I was able quite quickly to build a Sinatra application to scrape the Canmore site and return information and images to a client app. The application was tested using [MiniTest](https://github.com/seattlerb/minitest), the new default testing framework in Ruby 1.9.

####ARchitect
Next, I had to engage with [ARchitect](http://www.wikitude.com/developer/architect), Wikitude's new AR engine. This provides a JavaScript API to place arbitrary objects in an AR view -- the developer can point Wikitude's phone-based [World Browser](http://www.wikitude.com/tour/wikitude-world-browser) at an html file online, and the browser will process the linked JavaScript.

####CoffeeScript (and Jasmine)
This seemed like a good opportunity to get to grips with some more tools, so I opted to write the ARchitect application in [CoffeeScript](http://coffeescript.org), which turns out to be considerably more convivial than JavaScript. The application was tested using [Jasmine](http://pivotal.github.com/jasmine), and incorporated into the Sinatra app. When it detects that the user has moved more than a given distance, it makes a request to the Sinatra app based on the user's location; the Sinatra app responds, and the ARchitect app places photographs in the scene, scaled and with opacity adjusted according to the distance of the site.

The whole thing is [on GitHub](http://github.com/rdallasgray/archie-canmore), and has been an education on all sorts of levels.

####Where to next?
Now I have to begin working with the Wikitude SDK, and dive into Objective-C and CocoaTouch. I'm looking forward to it.
