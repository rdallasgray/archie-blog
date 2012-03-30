---
layout: post
title: "1. Background"
description: "A bit of background on the project."
category: archie
tags: []
date: 2012-03-30 11:00:00
---
{% include JB/setup %}

#### The Project

I'm using this blog to document the development of my MSc project, in the hope that I can note down enough here to a) have a reasonable head-start on writing up the dissertation when the time comes, b) remember the various hoops I've had to jump through to get things done and c) perhaps have some utility to anyone else who chances on it.

The project itself is to develop a prototype augmented reality smartphone app to encourage walking visits to the Antonine Wall. The Antonine Wall is the northernmost fortification of the Roman Empire, and stretches from the Firth of Clyde to the Firth of Forth in central Scotland. It's mostly not very interesting to the layperson -- not much remains of the wall or fortlets along it -- hence the suggested use of augmented reality techniques to try to give some sense of why it *is* interesting to archaeologists, historians etc.

I didn't create the project myself; I chose it from a list, based partly on my keenness to get to grips with smartphone programming, and partly on the fact that the project offered the opportunity to go on long walks out of the city.

#### Proposal

I completed the proposal for the project almost exactly a year ago today (I'm a part-time student, so my workload is split over two academic years). The proposal looked at other similar projects and at the general rise in use of technology in cultural heritage contexts. Following research I opted to use Wikitude as the base platform for the application, as it offered a nicely graded path from a very simple but evaluable interface to a standalone application.

#### Approach

My project advisor, learning that I liked long-distance walking, assigned me a route out of Glasgow city centre to Cadder and back -- around 16 miles. About the mid-point of the walk, the remains of two Antonine Wall fortlets would be encountered, with various other sites of interest along the way.

The Wikitude platform would be used as the backbone of a short-cycle iterative process, the overall structure being:

1. Use the [wikitude.me service](http://wikitude.me) to place points of interest in the wikutde.me World. These would then be visible on both the map and camera views of the Wikitude iPhone app, enabling simple evaluation.

2. Building on the results of the previous step's evaluation, carry over the points of interest into a web service providing an [ARML feed](http://openarml.org) to Wikitude. This would allow points to be given custom icons, and have media attached to them. Further and more detailed evaluation could then be undertaken.

3. Using [Wikitude's SDK](http://www.wikitude.com/developer/documentation/wikitude-sdk), and working from the previous evaluations, begin building a standalone iPhone app.

The next post discusses step 1, and the lessons learned from it.