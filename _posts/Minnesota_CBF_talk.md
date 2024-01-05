---
layout: post
title: "Graduate student seminar at U Minn: How have we been using control barrier functions in the field?"
date: 2024-01-07
tags: [research, safe control]
comments: false
share: false
---

# Safety critical control

In the fall semester I was grateful to be invited to give a seminar talk at the University of Minnesota transportation seminar where I talked about the use of "safety critical control" methods in intelligent transportation systems. These are a class of control algorithm designed to make sure systems do *not* enter certain states. Contrast this with the more common control objective of *livenes*, which is a property describing that a system will move to a certain state. Here's a good [contrast description](https://en.wikipedia.org/wiki/Safety_and_liveness_properties).

My talk focused on how our lab has been using Control Barrier Functions (CBFs) to monitor the driving behavior of our labs automated vehicle. Generally, CBFs are model based *active safety filters* (ASFs), which will filter control inputs to an autonomous/controlled system in order to maintain the safety of the system. 

A high level technical overview of how a CBF can induce an ASF given a dynamical system model is shown below:

<figure>
	<a href="{{ site.url }}/images/research_images/CBF_overview_minnesota_talk.png"><img src="{{ site.url }}/images/research_images/CBF_overview_minnesota_talk.png" alt=""></a>
</figure>