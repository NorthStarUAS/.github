# NorthStar UAS

## Summary

This is a collection of all the UAS, flight control, EKF, ground station, data analysis, and mapping related work I've done since the middle 2000's.

## June 2025: Flight Testing

I managed a day of flight testing.  There aren't major changes just little tweaks and fixes I have been making along the way in response to the previous test flight (last November, yikes, time flies!) I validated the fully autonomous hand launch task continues to work correctly after porting from the old python system to C++ on the teensy.  In the background I have been exploring NiceGUI as a replacement technology for the operator station.  So far this has been really nice!

## March, April, and May 2025: Also not a lot to report

Life and work has been busy.  I need to do better at not letting myself get distracted by all the cruelty and attrocities and disasters in the world.  Those are important, but somehow learning about these things on social media and commenting on social media and fretting about them in my head doesn't seem to help any of these situations.  I don't know any answers, I am starting to wonder if no one else does either.  The people who are most certain they know all the answers most certainly do not!

## February 2025: Not a lot to report

I have been doing some background cleanup of the simulation and out-the-window view code.  I did a big round of cleanup of the FCS modules and archived all the components I currently have no use-case for ... these can all be brought back when/if needed.  These changes are prep work so I can do prep work to experiment with some model-based controller ideas.  No flight testing yet in 2025 due to lack of decent weather.

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
