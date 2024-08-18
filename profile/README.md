# NorthStar UAS

## Summary

This is a collection of all the UAS, flight control, EKF, ground station, data analysis, and mapping related work I've done since the middle 2000's.

## August 2024: Porting Route Management, Mission, and Tasks

I successfully spun up a HIL simulation system that is built on top of JSBSim and communicates with the hardware via nsLink (and Messages.)  This enables testing the firmware code on the teensy hardware in simulated flight and allows testing of all the flight control law components as well as the higher level mission and task elements.  Circle holds are working.  The GCS web pages (panel and map) were updated with all the latest property name updates.  Some GCS (map) commands are enabled and working.  More will be added as the backend mission/task code to respond to those commands is ported.  Finally I am working on updating the route manager code to be a lot more embedded system friendly.  Previously it was running on a beaglebone (linux, pi-like) and I didn't worry too much about memory usage or memory fragmentation.

## July 2024: Continued efforts towards freshening many aspects of the project.

The main porting effort to the teensy (from the stalled pixhawk hardware port) is finished.  Next up is beginning to move the higher level guidance and flight control system over to the teensy.  This was previously written in python and intended to run on a beaglebone/raspberry-pi type of host computer.  However I would like to run as much of this system on the teensy as possible.  The short term goal is to get the core flight control laws running along with basic circle holds and route following.  Higher level tasks (such as survey route planning, launch, and land) will hopefully follow time permitting.  Life is always busy, but I am hoping to have the core flight control laws ported, tested (HIL), and then flight tested in an actual model aircraft by the end of 2024 ... fingers crossed!
