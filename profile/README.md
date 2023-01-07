# Project update(s)

January 7, 2023: I just wanted to post a quick public note on the development
status of this project.  In the spring of 2022 I lost the funding for my job at
the University of Minnesota.  This was stressful!  Thankfully I was able to find
a new position at a great company called Cirrus Aircraft.  However, getting up
to speed with the rhythm of the new job and simultaneously moving to a new city
has consumed all my brain cells and spare time.  The result is that this project
has gone dormant for the past year.

As it was left last spring, I was in process of a major overhaul of the flight
controller code to run natively on pixhawk hardware leveraging the ardupilot
driver libraries and build system.  This new system has been successfully test
flown, and I was in the process of rolling more of the flight controller
functionality from the beaglebone rc-flight code directly to run on the pixhawk
fmu. The other major functionality I hope to move over to the flight controller
is data logging.  This would enable the entire base system to run on the pixhawk
hardware without needing a beaglebone host computer.

The good: a much less expensive and much easier hardware integration. The bad:
losing all the python code/support for any functionality that is moved to the
pixhawk (which is C/C++ only.)