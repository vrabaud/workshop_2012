.. page-load-style:: styles/title

ROS: 

.. page-style:: 
   :font_size: 40

The Robot Operating System

.. page-style::
   :font_size: 20

Tully Foote

.. image:: images/wg_logo.jpg
   :width: 200

.. image:: images/osrf-horiz.png
   :width: 400


.. note::
   Connect:  Who's use robots before? 
   Who's been entirely satisfied with what the robot did? 
   Who's developed for a robot?


Presentation Outline
--------------------
.. load-style:: styles/main


.. page-style:: 
   :font_size: 40



.. image:: images/pie_in_sky.jpg
   :height: 200

.. image:: images/wg_logo.jpg
   :height: 200

.. image:: images/future.jpg
   :height: 200

.. note:: 
   Outline of my talk, I'll start with the vision for open source personal robots, The current implementation. And where we're going.  

.. include:: motivation.rst

----

.. include:: state_of_ros.rst



----

How do you prove your software works?

.. note::

   We have this vision for ROS but to get others to buy in that it's actually good we need to have great demos.  To have great demos we need a great robot.  

PR2
---

.. image:: images/pr2.jpg
   :height: 700

.. note::
   
   2 dual quad core Intel i7 servers with 32 Gb ram each pulling 500Watts each (motors are only 200W at full power)
   2 wifi routers + gigabit ethernet port with automatic network rerouting
   5 ethernet cameras
   2 laser range finders
   32 motorized joints
   16 Lithium-Ion laptop batteries

.. note::

   Design goal was to be robot software developers dream platform.  Emphasis
   on uptime, reliability and robustness.  Also easy user switching
   for time sharing.  Usually research robots run a few days a month,
   PR2s sometimes do 3 shifts of students.

   Talk about safe arms, with spring counter balance.  I"m willing to
   work right in front of the robot w/o looking due to only 4 poinds
   force.  I know of other common robot arms which have punched
   through the middle of the table in front of them the first time
   they were turned on.


PR2
---

What's a good challenge for the PR2?

.. note::
   Ask the audience their suggestions

PR2
---

How about a marathon?

PR2
---

.. note:: 
   Video silent, talk over it.  

.. video:: videos/milestone2_and_replugged.mpeg

.. note:: 

   Our first milestone was 3.14 km autonomous.  

   Our 2nd milestone was 26 miles autonomous
   Needed to teach it to plug in and open doors.  
   Some hacks needed to pull this off on our timeline.  

   Revisited plugs with production hardware and you can see it now plugging in cleanly.  

   Option: We got coverage in a running magazine for this.  

PR2
--- 

Can we make it play pool?

In one week?

.. note:: 
   Now that we've got a platform what can we do in a week to test our development?
   We gave ourselves this challenge as a hackathon.  Starting monday, demo on friday of what we can do.  

PR2
--- 

.. video:: videos/pool_reduced.mpeg

.. note::

   We had some more free time and wanted to get the PR2 doing something cool, in a week to identify weaknesses in the platform.  So we spent a week teaching it to play pool.  

PR2
--- 

How about fetch beer?

.. note::
   
   With the success of the pool playing robot, we though we might do it again for fetching beer from the fridge.  


.. note:: 
   Another 1 week long hackathon.  

   Let this one speak for itself. 

PR2
---

.. video:: videos/beer_short.mpeg


PR2
---

What can others do with the PR2?

.. note:: 
   We've shown that we who built the robot can use it, but what about external users?  

PR2
---

.. note::
   
   Background for video.  UCBerkeley student visited us and got the prototype PR2 folding towels at 25 min/ towel.  A year later UC Berkeley was able to demonstrate it in 5 minutes.  


.. video:: videos/towel_speedup.mpeg


----

.. layout::
   :vgradient:white;white

.. image:: images/future.jpg

.. note::
   Transition to where we want to go.  Keep expanding user base.  Make it easier to use ROS as a development platform. 

ROS Fuerte RC1
--------------

.. load-style:: styles/future

.. image:: images/fuerte_beta.png
   :width: 640


----


.. page-style:: 
   :list.expose: expose
   :align: center
   :list.bullet: none

- .. image:: images/osrf-horiz.png
     :width: 1024

- .. image:: images/roboticschallenge.jpg
     :width: 512

.. note::
   Just yesterday we announced the Open Source Robotics Foundation
   Designated to be a facilitator of OSR
   First project will be DARPA Simulator


Future Plans
------------


.. image:: images/ubuntu.png
   :width: 600

.. image:: images/fedora.png
   :width: 600

.. image:: images/android.jpg
   :width: 600

.. note:: 

   We're growing the community and now we're planning to start pushing
   our more mature code upstream to ubuntu and fedora repos.  Toward
   growing the community we are also now reaching out to more people
   by pushing our software onto smaller platforms.  We have many
   people starting to use ROS on Android and Arm based computer.  We
   just launched the TurtleBot running on Atom based laptops.

----

.. load-style:: styles/main


Try it out!

Tutorials
---------

.. page-style:: 
   :font_size: 40
   :bold: yes


.. image:: images/tutorials.png
   :width: 800


http://ros.org/wiki/ROS/Tutorials


The TurtleBot
-------------

.. image:: images/turtlebot.jpg
   :height: 650

.. note:: Introduce Turtlebot, getting from research into the home
   Small platform, give people access to the ROS community in a
   package they can take home.

.. note::
   Don't spend too long, talk more after video.  

----

.. video:: videos/turtlebot.mp4

----

.. note:: ADD NOTES FOR SMARTPHONE analigy, give people the capability to implement their passion

================================ ========================== ===============================
.. image:: images/droid.jpg      .. image:: images/l--r.jpg      .. image:: images/turtlebot.jpg
                                                                    :height: 325
================================ ========================== ===============================

.. note:: 
   Computer are great, they can display things, but what would you want them to do if they could move?   

   Who thinks they have the hardware to user robot code?
   Who has a computer and a webcam?  Who has a Kinect?  
   Simulator?  
   Rovio, roomba.  

Simulator
---------

.. image:: images/turtlebot_sim.png
   :width: 640

----


Thank You

Questions?

.. style::
   :font_size: 20

Check it out: www.ros.org


Email: tfoote@willowgarage.com


Image Sources
-------------

.. style::
   :font_size: 20


- Roomba Public Domain on Wikipedia
- Paro http://www.parorobots.com/pdf/pressreleases/PARO to be marketed 2004-9.pdf
- Pleo http://en.wikipedia.org/wiki/File:Pleo_robot.jpg
- Debian Package Management http://murugaprabu.me/wordpress/2011/01/16/hello-world/
- Urban Challenge kwc.org
- Success Chart https://cs.byu.edu/image/302-success_clipart
- Jenkins Logo https://wiki.jenkins-ci.org/display/JENKINS/Logo
- Droid Photo http://www.motorola.com/staticfiles/Consumers/Products/Mobile%20Phones/DROID-3-By-Motorola/_Images/Droid-X3_Production_Specs.jpg
- Android Logo http://farm4.staticflickr.com/3034/3754407004_33e592d075.jpg


