.. load-style:: gradient



.. layout::
   :vgradient:white;gray

Linux Based Personal Robots

.. page-style::
   :font_size: 20

Tully Foote

.. image:: images/wg_logo.jpg
   :width: 200

----

What is a personal robot?


.. note::
   Seek audiance input/suggestions. 

   From movies and TV: R2D2, iRobot

   In the real world.  iRobot Create, 

   End with Rosie

Sci Fi Personal Robots
----------------------


=================================== ==============================
.. image:: images/rosie_singing.gif .. image:: images/r2d2_200.jpg
=================================== ==============================

.. note:: We'd all love to have these robots
   But what robots do we have in the home. 

Personal Robots In Homes
------------------------
.. page-style:: 
   :list.expose: expose
   :align: center
   :list.bullet: none

- .. image:: images/roomba_220.jpg
    :height: 200

.. note:: We have simple cleaning robots.  They sometimes can work on
   their own, sometimes they're more entertainment.  

- .. image:: images/paro.jpg
    :height: 200

.. note:: And we have many robots companions, but the extent of their 
   abilities is to make noises and wiggle a little.

- .. image:: images/800px-Pleo_robot.jpg
     :height: 200

.. note:: And we have many robots companions, but the extent of their 
   abilities is to make noises and wiggle a little.

----

Motivation

What we're doing

Future


My Background
-------------

.. image:: images/grandchallenge.jpg
   :width: 800

.. note:: 

   Connect with audience!!! Ask how many know of Grand Challenge? HOw many particpiated? 
   What is the grand challenge?


My Background
-------------

.. page-style:: 
   :list.expose: expose
   :align: center
   :list.bullet: none

- .. image:: images/bob.jpg
     :height: 220

- .. image:: images/alice.jpg
     :height: 220
     
- .. image:: images/little_ben.jpg
     :height: 220


---------------------


.. note:: DARPA Urban Grand Challenge

.. image:: images/urban_challenge.jpg

.. note::
   Why did DARPA choose the challenge format? -- because paying military contractors to do this is much less efficient than crowd sourcing.  

.. note:: Note the similarities between these two cars.  The code
   which defined the difference between the winning car and the other
   finalists was maybe 10 percent of the effort.  The other 90% of the
   efforts could have been shared and not given up their competitive
   advantage.  And think if the 100+ teams in the overall competition
   had all contributed just a little bit to a shared pool.  
   Of course I'm preaching to the choir.


.. note:: This is indicative of the state of academic robotics in general.  
   TRANSITION TO PHD COMIC


----

.. PHD COMIC
.. image:: images/phd_comic.jpg

TODO change to progressive reveal of one word + image simplified


----

.. page-style::
   :align: center
   :layout.valign: center
   :font_size: 40


============================== =========
 .. image:: images/recycle.png  - Reduce 
                                - Reuse
                                - Recycle
============================== =========

 TODO fixme get this table working well 

.. note:: You can take the 3 tenants of recycling and directly apply them here. 
   The goal is to reduce wasted effort and make people more productive.  
   Reduce the amount of code written. 
   Reuse existing code, don't reimplement it if someone's already done it
   Recycle -- take parts of existing code and reuse them


.. note:: Values -- less volume + more eyes -> higher code quality, no duplicated effort.


----

.. Tux + Research

.. style::
   :align: center
   :layout.valign: center

========================= ========================== ==================================
.. image:: images/tux.png .. image:: images/plus.png .. image:: images/books_open.jpg
                             :height: 314               :height: 314
========================= ========================== ==================================

.. note:: 
   
   Computer industry is booming, and alot of it is due to the
   availability of open source software in particular linux.  We're
   looking to kick start the robotics industry in the same way.


----

What is the solution?

.. note:
   
   WG MIssion Open source lead to ROS

----

.. image:: images/ros.png
   :width: 700


----

=============================== ===================================
.. image:: images/direction.jpg .. image:: images/osi_symbol.jpg
=============================== ===================================
.. image:: images/balance.jpg   .. image:: images/documentation.jpg
=============================== ===================================


.. note:: 
  A goal and direction -- to get others to follow
  Open source platform
  Good software engineering practices
  Stable APIs
  Good documentation!!

----

  Transition to summary of some of the existing tools in ROS.


Tools for Developers
--------------------

.. image:: images/rosmake.png
   :width: 800

Tools for Developers
--------------------

.. video:: videos/rviz_30_second.mpeg


Tools for the Community
-----------------------

aafa.. image:: images/rosdocs.png

Tools for the Community
-----------------------

.. image:: images/jenkins.png
   :width: 600

.. image:: images/success.gif
   :width: 400

ADD IMAGE of dashboard

.. note:

   We've seen significant improvements in our code quality and
   usability.  And extending this to the entire community helps
   everyone.

.. note::

   We have implemented continuous integration and release testing for
   all stacks publicly release in the ROS community.  And the
   infrastructure is also being used externally to index and test
   private repositories.

MORE DETAILS 5 minute quick builds on commit, overnight builds to test full releases, release tarball generation

Worldwide community
-------------------
.. image:: images/ros_map.png
   :width: 1024

.. note:: 

   This represents the locations of most of the public repositories
   which are releaseing open source code and we are indexing.

.. note::

   To be able to write state of the art software we needed a state of
   the art robot.  I give you the PR2.


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

   Design goal was to be software developers dream platform.  Emphasis
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

.. video:: videos/milestone2_and_replugged.mpeg

PR2
--- 

.. video:: videos/pool_reduced.mpeg

PR2
---

.. video:: videos/beer_short.mpeg

PR2
---

What can others do with the PR2?

PR2
---

.. video:: videos/towel_speedup.mpeg

.. note:: 

   Done 2 years ago with an alpha robot.  

.. note::
   
   Done this spring with a stock PR2.  X times faster.  The speedup
   demonstrats the improvements in the tools.

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

The TurtleBot
-------------

.. image:: images/turtlebot.jpg
   :height: 650

----

.. video:: videos/turtlebot.mp4
   :width: 800

----

================================ ========================== ===============================
.. image:: images/droid.jpg      .. image:: images/l--r.jpg      .. image:: images/turtlebot.jpg
                                                                    :height: 325
================================ ========================== ===============================

.. note:: Introduce Turtlebot, getting from research into the home
   Small platform, give people access to the ROS community in a
   package they can take home.
   
.. note:: Show off teleo interactive markers, 2dnavigation + prebuilt
   slam from before hand.  Then stop it and switch to teleop android.



.. note:: ADD NOTES FOR SMARTPHONE analigy, give people the capability to implement their passion


----

Live Demo!


----


Thank You


Questions?


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

Notes from Karen
----------------



add transition slides between videos and sections.  like:
- "What can we do to prove ROS works?"
- "What's a good challenge for the PR2?
- Hackathon Results
- ...
- Where linux based robots have been, before my background.  

need summary of what I"m going to say
Where it was
Where it is
Where it's going

Find 3 images, use them as transition slides and themes

Setup my background with summary of the Grand Challenge
Ask who knows about it?  Who was involved with it.  ->>> This is what I did.  

Connect East Palo Alto to West Philly


Tools need more transitions, showing ROS log in the corner, --- Use ROS logo for where we are today. Connect with Willow Garage and our current mission.  
Use Scott's history of open source -> WG Mission for robotics.  



Transitions - wrap up previous and lead into the next point
Finding ways to enguage with the audience - ask more questions, even retorical

More direct conneciton to linux lost from last draft.



ENERGY!!!!!!!
Fun!!
Contact w/ audience
