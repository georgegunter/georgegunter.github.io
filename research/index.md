---
layout: page
title: Primary Research Projects
image:
  feature: Arizona_line_experiments_trimmed.jpg
comments: false
modified: 2018-01-27
---
## Cyber attacks on traffic with automated vehicles.

Vehicles with automated features are becoming increasingly present in traffic, such as adaptive cruise control (ACC) which manages a vehicle's speed in relation to vehicles ahead of it, effectively taking over a significant portion of the driving task. These technologies are expected to make traffic flows safer and more efficient, but they also introduce expanding attack vectors for cyber-security attacks. 

This project explores the extent to which broader traffic flows can be attacked by cyber-comrpomised AVs. In our initial work we proposed a simple congestion inducing attack, which we call a randomized deceleration attack (RDA). We test the attack in a mixed-autonomy simulation environment which involves both automated vehicles and human drivers interacting in complex traffic dynamics, and find that the attack is able to degrade commuter metrics such as travel time, as well as system throughput. Additionally, the attacks escape detection via anomaly detection using an autoencoder neural network which attempts detection from GPS measurements on vehicles.

<figure>
  <a href="{{ site.url }}/images/Cyber_Attack_ACC_intro_fig.png"><img src="{{ site.url }}/images/Cyber_Attack_ACC_intro_fig.png" alt=""></a>
</figure>


## Traffic control from sparsely adopted automated vehicles.

FILL IN

## Analyzing commercially available ACC vehicles for string-stability.

This work investigated answering whether or not commerically available ACC vehicles operate under string-stable control. This was a property that had been asserted in a number of works, but had previously not been verified. 

We tested 8 commercially available 2018 vehicles across three manufacturers, with over 1000 miles of total driving data collected. We found across all vehicles that they did not engage in car-following behavior that was string-stable. As a result, this means that just as humans contribute to phantom traffic jams, so do commerically available ACCs.

In following work we also developed techniques for performing online system-identification of ACC car-following dynamics. We developed both a technique that utilized a recursive least-squares filter as well as a particle filter to do identification and found both techniques to be both accurate and operational in real time.


G. Gunter et al., "Are Commercially Implemented Adaptive Cruise Control Systems String Stable?," in IEEE Transactions on Intelligent Transportation Systems, doi: 10.1109/TITS.2020.3000682. [Journal Publication](https://ieeexplore.ieee.org/abstract/document/9123538) [Arxiv Publication](https://arxiv.org/pdf/1905.02108.pdf)

G. Gunter, C. Janssen, W. Barbour, R. E. Stern and D. B. Work, "Model-Based String Stability of Adaptive Cruise Control Systems Using Field Data," in IEEE Transactions on Intelligent Vehicles, vol. 5, no. 1, pp. 90-99, March 2020, doi: 10.1109/TIV.2019.2955368. [Journal Publication](https://ieeexplore.ieee.org/abstract/document/8910461) [Arxiv Publication](https://arxiv.org/pdf/1902.04983.pdf)

Y. Wang, G. Gunter, M. Nice, M. L. D. Monache and D. B. Work, "Online Parameter Estimation Methods for Adaptive Cruise Control Systems," in IEEE Transactions on Intelligent Vehicles, vol. 6, no. 2, pp. 288-298, June 2021, doi: 10.1109/TIV.2020.3023674. [Journal Publication](https://ieeexplore.ieee.org/abstract/document/9195163) [Preprint](https://par.nsf.gov/servlets/purl/10206297)

[Datasets](https://acc-dataset.github.io/datasets/)



