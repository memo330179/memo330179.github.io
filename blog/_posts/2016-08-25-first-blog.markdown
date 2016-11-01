---
layout: post
title:  "Hacking the Jeep"
date:   2016-08-25 15:53:04 -0400
categories: CSC_386 Blog New
---
I saw the video [Hackers Remotely Kill a Jeep on the Highway—With Me in It](https://www.youtube.com/watch?v=MK0SrxBC1xs). In this video, A jeep is hacked, and the Jeep is controlled through a laptop miles aways. The attackers made the jeep do some benign things such as: turn the stereo volume up, turn the fans on, etc. The scary part of this video is that they turned off the engine and made the brakes stop working.

This brings up an interesting point. We live in a world filled with the Internet of things items everywhere from [Wifi enabled coffee makers](https://www.amazon.com/Mr-Coffee-Wifi-Enabled-Coffeemaker-BVMC-PSTX91WE/dp/B00LUFSSWG) to [home security systems](http://www.kwikset.com/wireless-technology/homeowners/index.aspx), and all of these items can be hacked.

This is a major concern when it comes to liability. f a Jeep were hacked, and the passengers killed, what liability would Fiat Chrysler have? It is an ethical questions, and one that can become more relevant in the future as autonomous cars progress. As a developer, security is always a concern, and something much more important especially when it concerns human lives. I am inclined to believe that if something like this scenario were to happen then Fiat Chrysler would have to be held responsible as it is a manufacturer defect. A software bug for something as important as a 2000+ steel bullet can be catastrophic is the wrong hands. I have learned that even in small projects bugs can go unnoticed, and this must be true in a codebase as large as making a jeep run. Something of this importance must be checked and double checked for bugs that could cause this, and if something is found then it should be patched up quickly.

As a student developer I have to be constantly learning the practices that will help with these kinds of situations. I am not sure that I am ready to work on something that could result in being life of death, but I think that I can get closer everyday. This semester I am taking the courses which I think could help me become a better developer. Embedded systems in which we will be designing a sensor will let me think about these challenges, and it will help me develop the skills that I will perhaps use in the future. Computer Security will help me think of ways to prevent things like the hacking of the Jeep from happening. The pair programming from my introduction classes have helped me to communicate. Communication is one of the skills which will be necessary to prevent things like this from happening.

Some of the things that safety-critical embedded systems use are:

1. Identify the Hazards - Knowing what could happen is crucial in correcting it.
2. Determine the Risks - What is the worst that could happen?
3. Define the Safety Measures - What needs to be done when the worst happens
4. Create Safe Requirements - Don't ask the system to do too much
5. Create Safe Designs - isolate safety systems so they are not affected by other processes
6. Implement Safety - Make sure safety systems work
7. Assure the Safety Process - test, test, test
8. Test, Test, Test
