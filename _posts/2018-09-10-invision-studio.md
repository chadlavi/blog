---
layout: post
title: Prototyping with InVision Studio
date: 2018-09-10
tags:
- prototyping
- invision
---

_Note: InVision Studio prototypes currently are not supported on macs with Intel HD 4000 GPUs ([most 2012-2013 models](https://support.apple.com/en-us/HT204349#intelhd)). This is a [known issue with InVision](https://support.invisionapp.com/hc/en-us/community/posts/360014933931/comments/360001806692). If you attempt to view the following prototypes on an affected mac, you'll likely get a garbled, unintelligible screen._

...

I've been a big fan of InVision since I first started using their web app in 2014; so when I caught wind of a beta desktop design app they were planning to release back in 2017, I immediately jumped onboard. I got access to InVision Studio in January 2018.

Most of the work I've done in 2018 has been experimental/direct building, so I've only had a few opportunities to use InVision Studio to prototype.

## Document Explorer

My team started work on a document exploration app for architectural drawing sets in May of this year. The app would allow architects and designers to upload individual drawing files and tag them, then allow the consumers of their drawing sets (contractors, subcontractors, engineers, clients) to interactively make sets of _just the drawings they needed_. This was an attempt to solve a longstanding problem with physical drawing sets produced in architecture today: the designs relevant to one person's work are scattered throughout the document set, which is often hundreds of pages long. Finding all the drawings you need, and comparing/contrasting drawings that are far away from each other, is a constant struggle. 

This product unforunately ended up getting shelved; there was a rights disagreement between the idea's originator and our company ownership, and they parted ways. 

But my initial MVP prototype still exists. In this prototype, you can create a project, simulate uploading images in bulk and tagging them, then filter your new project on those tags. 

[![Architectural Document Explorer MVP](http://chadlavimoniere.com/images/2018/09/prototyping/planit-mvp.jpg)]( https://projects.invisionapp.com/prototype/mvp-flow-cjhkmosiq00coo201mzehj69x/play/39763228)

## Tile Resizing Demo

In our initial version of [prsnt.app](https://prsnt.app), we had a fixed layout of three tiles per page, which flowed onto as many pages as needed. In part, this was because the users we initially talked to about presentation were highly technical. For them, the image was secondary, or perhaps even tertiary; it was included more as a visual reference to anchor the technical information than as a piece of presentation/decision making per se. We quickly realized that this wasn't a majority use case; interior designers and decorators generally give presentations that are more akin to collages than specifications, and for them the ability to add more images to the page and lay them out beautifully was a must-have. 

My colleague Peter and I had a long discussion one day about how to solve this. How could we let users add a varying number of items to the page while still making sure the page flow was controlled, and the user could accurately predict how many items would be on the page? 

It occured to me that we could take the length of the list of items added to a given page, then change the layout of the page based on that length; basically, we would bootstrap ourselves some responsive layouts based on item count. 

This is the quick demonstration I made to illustrate that concept to Peter and our developers. In this demo, you can click the "Add Tile" button to simulate dragging and dropping a new image onto the page; the tiles on the page will adjust to accommodate the new tile. For layouts of 3+ tiles, you can also click the +/- button on the first tile to make it fullheight. This yields a total of 14 different layouts for 8 tiles.

[![Tile Resizing Demo](http://chadlavimoniere.com/images/2018/09/prototyping/prsnt-tile-exploration.jpg)]( https://projects.invisionapp.com/prototype/11x17-layout-cjj1rnjl5003mem01w34vnx28/play/3aadbc7e)

The basic mechanics of this demonstration are still at the heart of our layout engine in prsnt.app, though we've extended and refined it since its inception.