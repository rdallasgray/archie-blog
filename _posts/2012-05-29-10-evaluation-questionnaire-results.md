---
layout: post
title: "10. Evaluation Questionnaire Results"
description: ""
category: archie
tags: []
date: 2012-05-29 16:49:01
---
{% include JB/setup %}

The intention behind conducting the formative evaluation we undertook at the weekend was to try to clarify the *purpose* of the application, and to determine whether it could achieve the aims set out in my Project Proposal. 

Informally, through conversations and observations during the walk, several things came into focus, as covered in the previous entry. The questionnaire provided a tool to further structure (and, to some extent, quantify) our thinking about the evaluation (my thinking and the subjects').

The stated aims of the application were to:

1. **Facilitate access to the site**, by some means of guiding the user to the site and within it;

2. **Present interpretative material** so that the material does not obscure, overwhelm or invalidate direct experience of the site itself; the interpretative material should augment the experience of visiting and interacting with the site;

3. Foster **continued interest** in and **repeat visits** to the site;

4. **Be portable**, both in terms of the hardware the solution should use, and in terms of the data available to the application.

####Here's a broad précis of the questionnaire results:

1. Both subjects are **interested in local history, enjoy visiting museums, and enjoy walking or rambling**.

2. Neither has previously found phone applications particularly useful while walking or rambling, or when visiting cultural heritage sites.

3. **Both would use an application like the one under test when planning a walk**, and would be at least as likely to use the app as to use a walking book or website. Both say that the availability of walks in the app would influence a decision on which walk to take.

4. **Images** of sites of interest on the walk would be important in a decision on which walk to take.

5. Both found **wayfinding** at least as easy using the app as using a paper map, and easier than using a non-dedicated mapping application.

6. Both **noticed sites of interest** they would not have noticed if not using the app, on both familiar and unfamiliar parts of the walk, and stopped for longer than they had before to explore sites of interest on the familiar part of the walk.

7. Both **learned new things** about their local area and the broader area as a result of using the app, and indirectly through conversations sparked by using the app.

8. Both felt they would be **more likely to undertake similar walks** in future after the walk with the app, and to revisit the areas we visited.

9. Both **did further research** on what they had seen following the walk.

10. One subject **felt more interested in cultural heritage**, and more likely to visit a cultural heritage site, following the walk; the other response was neutral, although this could be because the other subject was more likely to visit cultural heritage sites in the first place.

11. Neither felt they would use the app if there was **only a camera view**; both would use it if there were only a map view.

12. Both **clicked on points of interest** in the display, clicked through to read longer descriptions, and viewed images. Clicks were more likely if the icon was distinct (not one of the standard icons). Instrumentation would have been helpful here, to gather solid quantitative data, but unfortunately the ARML feature intended to allow such instrumentation doesn't seem to work (a bug report has been raised with Wikitude).

13. Subjects disagreed about how easy it was to **find the next waypoint** in the display; one subject found the number of icons in the display confusing, particularly when they were clustered.

14. Both agreed the **camera view was not helpful** in wayfinding; one subject noted that he found it largely redundant, although he suggested an interesting use case: naming hills or islands in a broad vista.

15. Most of the **suggested features** were welcomed:
    - A choice of walks
    - Indications of length and difficulty, and the ability to filter on these criteria
    - Walks within a given area
    - The ability to access longer descriptions of sites of interest as well as more images and video (although not audio)
    - Some indication of the next waypoint, whether a highlighted icon or a list
    - Notifications when reaching waypoints
    - An indication of distance travelled (and remaining)
    - Overlays on the map and camera displays showing hidden or disappeared structures
    - The ability to 'favourite' POIs for later review
    - The ability to add notes to POIS
    - Some form of social sharing of notes or photos taken along the route
    

One subject also suggested some simple **indication of historical period** of given POIs (Ancient, Georgian, etc.), and that an indication of **nearby amenities** would be useful in planning walks.

####Effects
So, there are two sides to sides to this result: 1) it seems to vindicate the broad use case for the app; it does seem to encourage visits, and repeat visits, and to generally foster the 'virtuous circle' of visit-research-revisit, but 2) the camera view just wasn't helpful or interesting in its present state.

This leaves me with two major problems to address:

1. What to do with the camera view. As discussed in the previous post, I think the best approach would be to limit it to particular areas of a walk, perhaps notifying the user that a view is available. I can think of three possible uses for the view at present:
   - Overlaying historical photos on scenes (which would necessitate the user standing in a particular position)
   - Marking, e.g. the path of the Antonine Wall or a disused railway
   - Per one subject's suggestion, annotating distant land features
   
2. What to do about the inaccessible Antonine Wall sites. My inclination is that further development would be simpler, and the result more valuable, if the Wall is deemphasised. 
