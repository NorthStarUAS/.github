# NorthStar UAS

## Summary

This is a collection of all the UAS, flight control, EKF, ground station, data analysis, and mapping related work I've done since the middle 2000's.

## July 2024: Continued efforts towards freshening many aspects of the project.

The main porting effort to the teensy (from the stalled pixhawk hardware port) is finished.  Next up is beginning to move the higher level guidance and flight control system over to the teensy.  This was previously written in python and intended to run on a beaglebone/raspberry-pi type of host computer.  However I would like to run as much of this system on the teensy as possible.  The short term goal is to get the core flight control laws running along with basic circle holds and route following.  Higher level tasks (such as survey route planning, launch, and land will hopefully follow time permitting.)  Life is always busy, but I am hoping to have the core flight control laws ported, tested (HIL), and then flight tested in an actual model aircraft by the end of 2024 ... fingers crossed!

## April 2024: Working on an approach to developing flight control laws that are fit directly to flight test data.

Advantage: there is almost no need for tuning.  Disadvantage: there is almost no knobs to tune if you don't like the performance.  There is some really cool stuff to be explored here, but I've set this stuff aside for the short term in favor of driving towards getting a plane back in the air with all the core functionality running directly on the teensy.
