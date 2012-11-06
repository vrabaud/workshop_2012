How does it work?
-----------------

.. load-style:: styles/current

.. page-style::
   :align: left
   :font_size: 40


- Build System

- Communications Middleware

- Community of developers and libraries

Build System Features
---------------------

.. page-style::
   :align: left
   :font_size: 40

- Declared dependencies

- FHS compliant (example)

- Automated workspace path updating

- Binary build automation

Example Manifest
----------------

.. page-style:: 
   :align: left
   :literal.font_size: 24

.. code:: xml

  <package>
    <description brief="Shows the features of ROS">
      This package attempts to show the features of ROS step-by-step.
    </description>
    <author>Morgan Quigley</author>
    <license>BSD</license>
    <review status="unreviewed" notes=""/>
    <url>http://ros.org/wiki/roscpp_tutorials</url>
    <depend package="roscpp"/>
    <depend package="std_srvs"/>
    <depend package="std_msgs"/>
    <export>
      <cpp cflags="-I${prefix}/srv/cpp"/>
    </export>
  </package>


Dependency Traversal
--------------------

.. page-style:: 
   :font_size: 24

rospack depends roscpp_tutorials vs rospack depends1 roscpp_tutorials

.. page-style:: 
   :align: left
   :literal.font_size: 24

.. code:: bash


  
  depends              depends1
  -------------------- ----------
  roscpp               roscpp			    
  std_srvs             std_srvs			    
  std_msgs             std_msgs			    
  rosbuild			       		    
  roslang			       		    
  cpp_common			       			    
  roscpp_traits			       			    
  rostime			       		    
  roscpp_serialization		       
  rospack			       		    
  roslib			       		    
  xmlrpcpp			       		    
  rosconsole			       			    
  rosgraph_msgs			       			    

Environment
-----------

.. page-style:: 
   :font_size: 30
   :align: left
   :literal.font_size: 32

The ROS Packaging system uses Environment Variables to find the packages

.. code:: bash

  $ env | grep ROS

  ROS_ROOT=/opt/ros/groovy/share/ros
  ROS_PACKAGE_PATH=/opt/ros/groovy/share:/opt/ros/groovy/stacks
  ROS_MASTER_URI=http://localhost:11311
  ROS_DISTRO=groovy
  ROS_ETC_DIR=/opt/ros/groovy/etc/ros


ros_comm
--------

.. page-style:: 
   :font_size: 40
   :align: left

ROS communication libraries. 

- Native implementations in each language

- Communication Types:

 - Anonymous Publish Subscribe

 - Remote Procedure Calls

 - Shared Parameters

- Messages defined by an IDL

Example Message
---------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 12


.. code:: bash

  $ rosmsg show LaserScan -r

  [sensor_msgs/LaserScan]:
  # Single scan from a planar laser range-finder
  #
  # If you have another ranging device with different behavior (e.g. a sonar
  # array), please find or create a different message, since applications
  # will make fairly laser-specific assumptions about this data

  Header header            # timestamp in the header is the acquisition time of 
                           # the first ray in the scan.
                           #
                           # in frame frame_id, angles are measured around 
                           # the positive Z axis (counterclockwise, if Z is up)
                           # with zero angle being forward along the x axis
                         
  float32 angle_min        # start angle of the scan [rad]
  float32 angle_max        # end angle of the scan [rad]
  float32 angle_increment  # angular distance between measurements [rad]

  float32 time_increment   # time between measurements [seconds] - if your scanner
                           # is moving, this will be used in interpolating position
                           # of 3d points
  float32 scan_time        # time between scans [seconds]

  float32 range_min        # minimum range value [m]
  float32 range_max        # maximum range value [m]

  float32[] ranges         # range data [m] (Note: values < range_min or > range_max should be discarded)
  float32[] intensities    # intensity data [device-specific units].  If your
                           # device does not provide intensities, please leave
                           # the array empty.


Example Message
---------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 24


.. code:: bash

  $ rosmsg show LaserScan

  [sensor_msgs/LaserScan]:
  Header header
    uint32 seq
    time stamp
    string frame_id
  float32 angle_min
  float32 angle_max
  float32 angle_increment
  float32 time_increment
  float32 scan_time
  float32 range_min
  float32 range_max
  float32[] ranges
  float32[] intensities


Using Messages
--------------

.. page-style:: 
   :font_size: 32
   :align: left


- Talker Listener demo
- show rostopic list
- show rostopic info 
- show rxgraph
- show rostopic echo
- show rostopic pub
- show rosbag record
- show rosbag play
- show rxconsole
- show logger levels



Inside Talker (Python)
----------------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 24


.. code:: python

  import rospy
  from std_msgs.msg import String

  pub = rospy.Publisher('chatter', String)
  rospy.init_node('talker', anonymous=True)
  r = rospy.Rate(10) # 10hz
  while not rospy.is_shutdown():
      str = "hello world %s"%rospy.get_time()
      rospy.loginfo(str)
      pub.publish(str)
      r.sleep()



Inside Talker (C++)
-------------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 24

.. code:: c++

  #include "ros/ros.h"
  #include "std_msgs/String.h"
  #include <sstream>
  int main(int argc, char **argv) {
    ros::init(argc, argv, "talker");
    ros::NodeHandle n;
    ros::Publisher chatter_pub = n.advertise<std_msgs::String>("chatter", 1000);
    ros::Rate loop_rate(10); int count = 0;
    while (ros::ok()){
      std::stringstream ss; 
      ss << "hello world " << count;
      std_msgs::String msg; msg.data = ss.str();
      ROS_INFO("%s", msg.data.c_str());
      chatter_pub.publish(msg);
      ros::spinOnce();
      loop_rate.sleep(); ++count; }
    return 0;  }



Inside Listener (Python)
------------------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 24

.. code:: python

  import rospy
  from std_msgs.msg import String

  def callback(data):
      rospy.loginfo(rospy.get_caller_id()+"I heard %s",data.data)
    
  rospy.init_node('listener', anonymous=True)
  rospy.Subscriber("chatter", String, callback)
  rospy.spin()


Libraries Available In ROS
--------------------------

.. page-style:: 
   :font_size: 40
   :align: left

- tf

- navigation

- arm navigation

- sensor drivers

- actuator drivers

- OpenCV

- PCL 

- object recognition

Where to find these resources
-----------------------------

.. page-style:: 
   :font_size: 64

ROS Wiki: www.ros.org

.. page-style:: 
   :font_size: 40

There are indexes on the home page. 

Click "Browse Software" to browse or search the meta data fields

Where to get help
-----------------
.. page-style:: 
   :font_size: 60

Q&A site: answers.ros.org

.. page-style:: 
   :font_size: 40
   :align: left

- Search first, then ask. 

- Make sure to tag well. 

- Follow www.ros.org/wiki/Support guidelines



