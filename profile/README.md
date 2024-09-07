# NorthStar UAS

## Summary

This is a collection of all the UAS, flight control, EKF, ground station, data analysis, and mapping related work I've done since the middle 2000's.

## September 2024: Logging, Real Hardware and Sensors, Aircraft Integration

This summer's efforts to port the entire FMU system from a hybrid beaglebone(linux/python) + teensy(real-time/c++) to all running entirely on a single teensy in c++ has been going well.  The Launch and Land tasks are ported and tested.  Onboard logging is also up and running now.  Logging had been another function that resided on the beaglebone.  Flight data is pushed into a protected ring buffer from the main 100hz interrupt handler and then written [as able] to the SD card in the slack time.  I had been testing on a teensy-4.x but as of today I have the code up and running on a teensy-3.6 (Bolder Flight Systems Marmot board.)  My plan is to integrate this board into my Skywalker for first real test flights of all the software updates.

## August 2024: Porting Route Management, Mission, and Tasks

I successfully spun up a HIL simulation system that is built on top of JSBSim and communicates with the hardware via nsLink (and Messages.)  This enables testing the firmware code on the teensy hardware in simulated flight and allows testing of all the flight control law components as well as the higher level mission and task elements.  Circle holds are working.  The GCS web pages (panel and map) were updated with all the latest property name updates.  Some GCS (map) commands are enabled and working.  More will be added as the backend mission/task code to respond to those commands is ported.  Finally I am working on updating the route manager code to be a lot more embedded system friendly.  Previously it was running on a beaglebone (linux, pi-like) and I didn't worry too much about memory usage or memory fragmentation.

## July 2024: Continued efforts towards freshening many aspects of the project.

The main porting effort to the teensy (from the stalled pixhawk hardware port) is finished.  Next up is beginning to move the higher level guidance and flight control system over to the teensy.  This was previously written in python and intended to run on a beaglebone/raspberry-pi type of host computer.  However I would like to run as much of this system on the teensy as possible.  The short term goal is to get the core flight control laws running along with basic circle holds and route following.  Higher level tasks (such as survey route planning, launch, and land) will hopefully follow time permitting.  Life is always busy, but I am hoping to have the core flight control laws ported, tested (HIL), and then flight tested in an actual model aircraft by the end of 2024 ... fingers crossed!
