# NorthStar UAS

## Summary

This is a collection of all the UAS, flight control, EKF, ground station, data analysis, and mapping related work I've done since the middle 2000's.

## January 2025: House cleaning

Less activity this month.  I have been doing some house keeping to make field names more consistently include their units and have been slowly pushing those changes through the ecosystem.  I also separated the Simluator and SysId work into two separate repositories in anticipation of more cleanly packaging the Simulator tools for reuse.

## December 2024: Pushing forward (and another flight test?)

I would love to find at least one more day in 2024 with light winds, moderate temps, and time in my schedule to go out and test all the fixes and updates since mid-november.  There is also plenty more work to do porting the remaining tasks (parametric path following, glide and excitation tasks, and survey route generation.)  If I get bored with that, I really hope to get back working on my ideas of generating control laws directly from flight test data (just fly around a bit ...) along with generating a functional flight simulator for HIL testing also directly from flight test data.

## November 2024: First Test Flight!

On November 15 I went out and actually test flew all the work so far.  Yes I had missed a few things in testing so the day started out rough as I worked through debugging a couple things, and then after that I got about an hour and 45 minutes of fully autonomous flight, including a successful autoland.  Much of the remainder of November was spent working through the squaks I discovered and working through logfile and post-process scripts to catch up with all the message changes.

## October 2024: Working towards Aircraft Integration

Continuing tweaks and polishing of code as I work through the next aircraft integration.  For example: I ran into a not-fully-understood issue with parsing sbus input, so I updated to the latest BFS sbus library code and made the corresponding API updates to the calling layers. Hoping for full integration by the end of October with a first flight soon after.

## September 2024: Logging, Real Hardware and Sensors, Aircraft Integration

This summer's efforts to port the entire FMU system from a hybrid beaglebone(linux/python) + teensy(real-time/c++) to all running entirely on a single teensy in c++ has been going well.  The Launch and Land tasks are ported and tested.  Onboard logging is also up and running now.  Logging had been another function that resided on the beaglebone.  Flight data is pushed into a protected ring buffer from the main 100hz interrupt handler and then written [as able] to the SD card in the slack time.  I had been testing on a teensy-4.x but as of today I have the code up and running on a teensy-3.6 (Bolder Flight Systems Marmot board.)  My plan is to integrate this board into my Skywalker for first real test flights of all the software updates.

## August 2024: Porting Route Management, Mission, and Tasks

I successfully spun up a HIL simulation system that is built on top of JSBSim and communicates with the hardware via nsLink (and Messages.)  This enables testing the firmware code on the teensy hardware in simulated flight and allows testing of all the flight control law components as well as the higher level mission and task elements.  Circle holds are working.  The GCS web pages (panel and map) were updated with all the latest property name updates.  Some GCS (map) commands are enabled and working.  More will be added as the backend mission/task code to respond to those commands is ported.  Finally I am working on updating the route manager code to be a lot more embedded system friendly.  Previously it was running on a beaglebone (linux, pi-like) and I didn't worry too much about memory usage or memory fragmentation.
