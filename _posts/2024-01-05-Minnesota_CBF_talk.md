---
layout: post
title: "Graduate student seminar at U Minn: How have we been using control barrier functions in the field?"
date: 2024-01-05
tags: [research, safe, control]
comments: false
share: false
---

## Safety critical control

In the fall semester I was grateful to be invited to give a seminar talk at the University of Minnesota transportation seminar where I talked about the use of "safety critical control" methods in intelligent transportation systems. These are a class of control algorithm designed to make sure systems do *not* enter certain states. Contrast this with the more common control objective of *livenes*, which is a property describing that a system will move to a certain state. Here's a good [contrast between safety and liveness](https://en.wikipedia.org/wiki/Safety_and_liveness_properties).

My talk focused on how our lab has been using Control Barrier Functions (CBFs) to monitor the driving behavior of our labs automated vehicle. Generally, CBFs are model based *active safety filters* (ASFs), which will filter control inputs to an autonomous/controlled system in order to maintain the safety of the system. 

A high level technical overview of how a CBF can induce an ASF given a dynamical system model is shown below:

<figure>
	<a href="{{ site.url }}/images/research_images/CBF_overview_minnesota_talk.png"><img src="{{ site.url }}/images/research_images/CBF_overview_minnesota_talk.png" alt=""></a>
</figure>

In portions of the systems state, represented here in 2 dimension by x, where the CBF based ASF does not "consider" safety to be an issue other controllers that are interested in a liveness property can decide control inputs. However, as the 



## Supervising variable speed limit following

One of the most interesting applications of the development of our CBF based ASF is that it's opened up new opportunities to test out Vehicle-to-Infrastructure algorithms, which otherwise might not be safe. For instance, on Interstate 24 in Nashville our team also works on improving safety along the instertate through the deployment of vairable speed limit (VSL) gantries which adjust the speed limit along the roadway.



Here's a video of our deployment:

<figure>
	<a href="{{ site.url }}/images/research_images/V2I_on_I24"><img src="{{ site.url }}/images/research_images/V2I_on_I24" alt=""></a>
</figure>








