---
layout: post
title: "2. wikitude.me"
description: "First steps, using the wikitude.me service."
category: archie
tags: []
date: 2012-03-30 12:00:00
---
{% include JB/setup %}



The first step I took was to use the [wikitude.me](http://wikitude.me) community platform to place some points in the wikitude.me World. The whole process took less than a day, and the results were useful. Initially about 30 points of interest were added, charting the path of the walk.

![The walk on Wikitude.me](/assets/images/Screenshot_1.png)

This put me in a position to do some very basic evaluation as regards broad user experience issues:

- It was immediately apparent that there was potential for confusion if icons in the map and camera views were to be used as waypoints (they tended to cluster together and overlap each other), so icon types would have to be easily distinguishable and ordered so that following waypoints didn't overlay preceding ones.

- The app changed the size of icons slightly to indicate relative distance, but it wasn't that effective. Transparency would probably be more useful.

- An indicator showing the next waypoint on the walk would be useful, and/or a list of nearby points of interest.

- The accuracy of the placemarking could be inferred (appearing to be about 5--10m), and a certainly squirreliness was noted (icons tended to jump around in the cam display -- this has since been improved by updates to the Wikitude app).

- Icon labels in the cam display are very short (only a few letters). There needs to be a way to maximise the amount of information the icons convey between the icon itself and the label.

<img src="{{ BASE_PATH }}/assets/images/IMG_0209.PNG"/>

####Next
Creating the web service to serve ARML to Wikitude.