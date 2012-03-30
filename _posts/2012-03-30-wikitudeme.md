---
layout: post
title: "wikitude.me"
description: "First steps, using the wikitude.me service."
category: archie
tags: []
---
{% include JB/setup %}

The first step I took was to use the wikitude.me community platform (http://wikitude.me) to place some points in the wikitude.me World. That put me in a position to do some very basic evaluation as regards broad user experience issues. The whole process took less than a day, and the results were useful:

- It was immediately apparent that there was potential for confusion if icons in the map and camera views were to be used as waypoints (they tended to cluster together and overlap each other), so icon types would have to be easily distinguishable and ordered so that following waypoints didn't overlay preceding ones.

- The app changed the size of icons slightly to indicate relative distance, but it wasn't that effective. Transparency would probably be more useful.

- An indicator showing the next waypoint on the walk would be useful, and/or a list of nearby points of interest.

- The accuracy of the placemarking could be inferred (appearing to be about 5--10m), and a certainly squirreliness was noted (icons tended to jump around in the cam display -- this has since been improved by updates to the Wikitude app).

- Icon labels in the cam display are very short (only a few letters). There needs to be a way to maximise the amount of information the icons convey between the icon itself and the label.

The next post deals with the creation of the web service to serve ARML to Wikitude.