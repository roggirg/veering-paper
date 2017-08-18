# To Veer or Not to Veer: Learning from Experts How to Stay Within the Crosswalk
Accepted at the __5th International Workshop on Assistive Computer Vision and Robotics (ACVR), ICCV 2017__ [[link]](http://iplab.dmi.unict.it/acvr2017/index.php). For any inquiries please contact [Roger Girgis](mailto:rogerg@cim.mcgill.ca) or [Manfred Diaz](mailto:mdiaz@cim.mcgill.ca).

## Motivation

One of the many challenges faced by visually impaired individuals is crossing an intersection while remaining within the crosswalk. Mobility training focuses on techniques to keep the individual walking as straight as possible while maintaining a safe distance from parallel traffic, i.e., remaining within the marked lines designating pedestrian crossings. Unfortunately, as previous studies found, even after training, detection of veering remains difficult. It has been noted that regardless of visual impairment, in the absence of environmental visual cues, humans tend to walk in circles, with diameters less than 20 meters. 

This has obvious implications in crossing intersections, which can be of similar length. Many systems have been proposed to tackle this problem, but due to sensor stability problems, the need to constantly recalibrate the devices, or their reliance on special features present in crosswalks (e.g., Zebra crossings), their deployment remains under-adopted by the visually impaired community. Perhaps the most successful deployed system is the Accessible Pedestrian Signal (APS), which provides indications of when it is safe to cross and offers auditory cues that help users determine their orientation relative to the far side of the curb. Unfortunately, one of the major problems of this system is auditory cue masking, due to the level of background noise. Another major constraint is their cost of deployment, estimated at approximately $25k per new installation and $8k at intersections with existing poles. 

In Montreal, Canada, there are currently only 133 installed APS systems out of a total of 1875 intersections. 

## Overview
n this work, we present a Learning from Demonstration (LfD) approach to tackle the veering problem at intersections. Contrary to previous methods, our solution does not presume the existence of particular features in crosswalks. Instead, the LfD framework allows us to transfer the abilities of sighted individuals to an intelligent assistive agent. 

We started by recollecting  215 demonstrative videos of intersection crossings executed by sighted individuals ("the experts"). We sampled these videos at two frames per second and labeled each frame to gather the experts' recommended actions. Next, we applied a policy derivation technique to extract the optimal behaviour using Convolutional Neural Networks (CNNs). We use the concepts of transfer learning to re-train four CNN models, pre-trained on the Imagenet dataset, to predict the optimal action as chosen by an expert. 

Finally, to assess the feasibility of such a solution, we evaluated the performance of the trained agent in predicting expert actions on a collected test dataset comprised of 51 additional videos from intersections not present at the training set. We construct confusion matrices which allow for the analysis of the severity of an error, as opposed to the accuracy metric. 

Next, one must evaluate the resulting trained agents in a real-world application.Since the model is only useful if it responds quickly enough to guide the user in real-time, we packaged a model that provides a balance between fast inference time and best performance into an Android application. The system provides users with a virtual audio beaconing signal that makes it sound like there is an actual APS system at intersections where no such system is installed. The idea is to provide users with a mobile solution that is both cost efficient (effectively free) and overcomes the problem of auditory-cue masking. 

## Project Status

We are currently working on conducting experiments with blindfolded sighted individuals as well as visually impaired individuals to characterize the effectiveness of the system.

## Supporting Material

As a demonstration of the capabilties of the proposed solution, we have created real-time videos from different intersection configurations which proposes various challenges for our system. The videos are available at the project [Youtube channel](https://www.youtube.com/channel/UCh9GARW98Z41SezH-4fh7zg/videos).

## Contributors

* Roger Girgis [[mail](mailto:rogerg@cim.mcgill.ca), [github](https://github.com/roggirg/)]
* Manfred Diaz [[mail](mailto:mdiaz@cim.mcgill.ca), [github](https://github.com/takeitallsource)]
* Thomas Fevens [[mail]()]
* Jeremy Cooperstock [[mail]()]


