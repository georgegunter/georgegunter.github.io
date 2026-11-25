---
layout: page
title: Primary Research Projects
image:
  feature: Arizona_line_experiments_trimmed.jpg
comments: false
modified: 2018-01-27
---
# Current research

My current work is focused on building formal methods for real-time control and operation of transportation systems. 


### Traffic signal control for transit arrival time management through gradient based formal methods

Traffic signal control (TSC) focuses on using the timing of traffic lights to optimize overall traffic flow metrics. A vairent of the TSP problem is transit signal priority (TSP), in which lights are timed with considerations for transit signals as well. For instance, a light might turn green when a bus is within a certain distance, allowing the bus to proceed un-interrupted. Simple TSP approaches have two potential drawbacks however: 1) Negative impact on traffic flows if overly aggressive, and 2) ineffectiveness at facilitating bus arrivals in congested traffic conditions. 

In this project we look at framing the TSP problem as a formal supervision problem. First, we model transit vehicle arrival times as a function of surrounding traffic using the LWR traffic flow PDE, and the vehicle as a particle within a broader flow. This traffic flow is impacted by light timing. We then take an underlying TSC controller (or nominal controller) and look to alter phase durations so that transit vehicle arrive at desired intervals, but without too aggressively changing underlying control. We do this by framing the magnitude of change to the nominal control input as a constraint that we look to satisfy at all times. Within this constrained set we then look to optimize transit vehicle arrival times. In other words, we time lights so that transit vehicles arrive as on time as possible, within a certain amount of disturbance to surrounding traffic flow.


We develop a novel numerical framework to solve this problem. By making a few small relaxations to the typical LWR model we can create a fully differentiable traffic flow model. This allows to us to explicitly calculate gradients of objective functions on the traffiuc flow as a function of traffic signal control durations. We implement this model in the Jax python framework, which can do automatic differentiation. With an ability to calculate gradients, we then optimize an objective function which includes barrier/penalty methods on changes to underlying traffic flow metrics and a squared-error term on transit vehicle arrival time. This approach is able to run extremely quickly, making it suitable for real-time supervisory control.




### Headway based transit operation with formal control of automed buses


In headway based operations of transit vehicles we want vehicles to arrive at stops at even intervals (e.g. every 10 minutes), rather than at set times. Variations in passenger demand and variability in travel times can make this challenging, causing buses to draw too close or too far apart from one another. To mitigate this, we must respond in real-time to re-allign bus timing. This has 




# Prior research

### Control barrier functions for safe supervision of automated vehicles.

In this work we looked at using control barrier functions (CBFs) to supervise safe driving of automated vehicles (AVs). While CBFs have been shown in a wide set of theoretical works to effectively supervise AVs, this was some of the first work to experimentally test this in real world deployments. We put CBFs onto our experimental vehicle and drove hundreds of miles on real roadways letting the CBF supervise. We found that a simple CBF form was able to effectively supervise a variety of underlying controllers, but there were violations to the specified formal safety property of two kinds: 1) forward-invariance and 2) recovery. When beginning in satisfaction of the safety property, we saw some, relatively small, violations to the safety property. This means that forward-invariance was not strictly satisfied, but rather it was mostly (and practically) satisfied. Additionally, when other vehicles cut-in front of the AV at close distances, the property is immediately violated. From there, a desirable robustness property of good supervisory algorithms is recovery: that the system is always moving back towards safety. Again, we found this to not be strictly true. 


<figure>
  <a href="{{ site.url }}/images/CBF_testing_distribution.png"><img src="{{ site.url }}/images/CBF_testing_distribution.png" alt=""></a>
</figure>

After the initial work on deployment of CBFs we expanded our work to higher-order CBFs (HO-CBFs). When adopting a higher-order dynamical model of an AV, one that includes control lag, original formulations of CBFs were no longer correct. An HO-CBF formulation fixes this. However, the HO-CBF aslo induces a need to do higher-order derivative estimation, something that is known to induce measurement error. We deployed a formulation of the HO-CBF that does lvie derivative estimation and measured it's performance. Interestingly, despite a more accurate dynamical model forumlation, the HO-CBF performed similarly to the original CBF. We beleive this was due to the presence of estimation error. This raises interesting questions about the tradeoff between increased model accuracy and induced measurement error in designing formal methods approaches.




### Cyber attacks on traffic with automated vehicles.

Vehicles with automated features are becoming increasingly present in traffic, such as adaptive cruise control (ACC) which manages a vehicle's speed in relation to vehicles ahead of it, effectively taking over a significant portion of the driving task. These technologies are expected to make traffic flows safer and more efficient, but they also introduce expanding attack vectors for cyber-security attacks. 

<figure>
  <a href="{{ site.url }}/images/Cyber_Attack_ACC_intro_fig.png"><img src="{{ site.url }}/images/Cyber_Attack_ACC_intro_fig.png" alt=""></a>
</figure>

This project explores the extent to which broader traffic flows can be attacked by cyber-comrpomised AVs. In our initial work we proposed a simple congestion inducing attack, which we call a randomized deceleration attack (RDA). We test the attack in a mixed-autonomy simulation environment which involves both automated vehicles and human drivers interacting in complex traffic dynamics, and find that the attack is able to degrade commuter metrics such as travel time, as well as system throughput. Additionally, the attacks escape detection via anomaly detection using an autoencoder neural network which attempts detection from GPS measurements on vehicles. This work is currently under review. The feasibility of the attack was ealso experimentally validated on a live commercially available ACC vehicle.

All code developed for this project can be found at [Anti-Flow](https://github.com/georgegunter/Anti-Flow). Further work will investigate developing both more advanced attack methods, as well as different approaches to adversary detection.


### Traffic control from sparsely adopted automated vehicles.

As part of the [CIRCLES DOE project](https://circles-consortium.github.io/) I work on developing automatic control techniques for automated vehicles which can improve energy consumption in broader traffic flows.

### Analyzing commercially available ACC vehicles for string-stability.

This work investigated answering whether or not commerically available ACC vehicles operate under string-stable control. This was a property that had been asserted in a number of works, but had previously not been verified. 

We tested 8 commercially available 2018 vehicles across three manufacturers, with over 1000 miles of total driving data collected. We found across all vehicles that they did not engage in car-following behavior that was string-stable. As a result, this means that just as humans contribute to phantom traffic jams, so do commerically available ACCs.

In following work we also developed techniques for performing online system-identification of ACC car-following dynamics. We developed both a technique that utilized a recursive least-squares filter as well as a particle filter to do identification and found both techniques to be both accurate and operational in real time.


G. Gunter et al., "Are Commercially Implemented Adaptive Cruise Control Systems String Stable?," in IEEE Transactions on Intelligent Transportation Systems, doi: 10.1109/TITS.2020.3000682. [Journal Publication](https://ieeexplore.ieee.org/abstract/document/9123538) [Arxiv Publication](https://arxiv.org/pdf/1905.02108.pdf)

G. Gunter, C. Janssen, W. Barbour, R. E. Stern and D. B. Work, "Model-Based String Stability of Adaptive Cruise Control Systems Using Field Data," in IEEE Transactions on Intelligent Vehicles, vol. 5, no. 1, pp. 90-99, March 2020, doi: 10.1109/TIV.2019.2955368. [Journal Publication](https://ieeexplore.ieee.org/abstract/document/8910461) [Arxiv Publication](https://arxiv.org/pdf/1902.04983.pdf)

Y. Wang, G. Gunter, M. Nice, M. L. D. Monache and D. B. Work, "Online Parameter Estimation Methods for Adaptive Cruise Control Systems," in IEEE Transactions on Intelligent Vehicles, vol. 6, no. 2, pp. 288-298, June 2021, doi: 10.1109/TIV.2020.3023674. [Journal Publication](https://ieeexplore.ieee.org/abstract/document/9195163) [Preprint](https://par.nsf.gov/servlets/purl/10206297)

[Datasets](https://acc-dataset.github.io/datasets/)



