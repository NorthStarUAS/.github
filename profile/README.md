# NorthStar UAS

## Summary

This is a collection of all the UAS, flight control, EKF, ground station, data analysis, and mapping related work I've done since the middle 2000's.

## February 2025: Not a lot to report

I have been doing some background cleanup of the simulation and out-the-window view code.  I did a big round of cleanup of the FCS modules and archived all the components I currently have no use-case for ... these can all be brought back when/if needed.  These changes are prep work so I can do prep work to experiment with some model-based controller ideas.

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
