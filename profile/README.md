# Project updates

## February 19, 2023: What's in a name?

In the Spring of 2022 I had an unrequested job change situation dropped in my lap.
In the Fall of 2022 we moved from a wonderful neighborhood near Rice Creek in the
Twin Cities (Minnesota, USA) up to the North Woods of Minnesota.  The original 
inspiration for this project was named Avior (a star used for navigation.)  Then 
when I spun off the pure open-source parts I called them AuraUAS, but a small 
company came along and built an RC flight controller and called it Aura so I let
them have it because they are good guys.  I then changed the name to Rice Creek UAS.
But because no one much cares about this project or uses anything from it, the name
really doesn't matter, so I have changed it again to reflect this new chapter of my life!
North Star UAS circles back around to the astronomy theme of the original effort
and reflects the direction my life moves have taken me, starting in Peru, then AZ,
then Twin Cities, MN, now Duluth MN.  (So further and further north!)
Over time and as I go through various sections of code, I may do arbitrary variable and file
name changes to reflect the new project name a bit better.  And there may be things
I don't touch that still have the old name.  It will be a work in progress.

## January 7, 2023: Status Update.

I just wanted to post a quick public note on the development
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

For now, I hope this body of code can serve as an example of an alternative
structure for a UAV flight controller. The design goal is simplicity.  I don't
know if that shows through, but that is the underlying intent ... easier to
understand code, structures, and algorithms.  I will do my best to support and
answer questions and will truly feel bad if I am slow or unable to respond.

For the future, I do truly intend to pick this work back up and continue pushing
it forward.  I thoroughly enjoy the process of writing and testing my own flight
controller code, and I believe there is room in the world for a simpler approach
that doesn't attempt to support every vehicle, every sensor, every use case,
every hardware board, and every idea.

If someone spends 15 seconds looking at this and thinks, oh, that's a little
cool, then I guess I'm happy enough. :-)  If some of these ideas and design
patterns seem interesting and make it into your own future work, then that would
be a big success.
