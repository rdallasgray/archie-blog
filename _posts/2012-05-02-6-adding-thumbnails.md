---
layout: post
title: "6. Adding thumbnails"
description: "Beginning to distinguish the POIs"
category: archie
tags: []
date: 2012-05-02 14:03:44
---
{% include JB/setup %}

The first advantage of using an ARML-fed webservice over the Wikitude.me community service is the facility to assign thumbnails individually to POIs. This would be the first step in addressing the issue of pathfinding using the map and cam interfaces.

The first issue was to somehow inform the user about the *order* of the waypoints on the walk. Numbering the POIs seemed the sensible way to do this; numbering the POI names had worked very basically, but the names were not immediately visible in the map interface.

It also seemed apparent that not all POIs were in fact waypoints, so fields were added to the POI model to indicate the *type* of the POI and its *waypoint number* (which could be null).

The icons were designed to give simple indications of these two pieces of information.

![Icons in the Wikitude interface](/assets/images/IMG_0252.PNG)

Labels on the icons were still not terribly useful. They tended to get cut off before they had really said anything, so they were shortened to absolute bare-bones, giving the user an indication of the object they should be looking for, but relying on the longer POI description for fuller information.

![Shorter icon names in use](/assets/images/IMG_0268.PNG)

There were still issues with the placement of POIs in the display -- the map display seemed accurate, but in the cam display there was a distinct bias to the north, and apparent issues with altitude (POIs appearing in the sky, for instance ...).