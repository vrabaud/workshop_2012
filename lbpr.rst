.. page-load-style:: styles/title

ROS: 

.. page-style:: 
   :font_size: 40

The Robot Operating System

.. page-style::
   :font_size: 20

Vincent Rabaud

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


.. include:: motivation.rst

----

.. include:: state_of_ros.rst

----

.. include:: PR2.rst

----

.. include:: ros_technical_overview.rst

----

.. layout::
   :vgradient:white;white

.. image:: images/future.jpg

.. note::
   Transition to where we want to go.  Keep expanding user base.  Make it easier to use ROS as a development platform. 

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


Current Efforts
---------------

.. load-style:: styles/future

.. page-style:: 
   :font_size: 36
   :align: left

ROS:

- Gazebo revamp

- more drivers (Motoman ...)

- rpm packages. Mac/Windows support

- auto-discovery of masters, of devices

- client library redesign (ZeroMQ, no msg type)

ROS environment:

- ROS Industrial

- ROS Enterprise

- ROS Education


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


Tutorials
---------

.. page-style:: 
   :font_size: 40
   :bold: yes


.. image:: images/tutorials.png
   :width: 800


http://ros.org/wiki/ROS/Tutorials

----


Thank You

Questions?

.. style::
   :font_size: 20

More inforomation at: www.ros.org


Email: vrabaud@willowgarage.com
