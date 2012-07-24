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

- Automatic linking and compile flags

- Automated PYTHONPATH updating

- System dependency resolution

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

$rospack depends roscpp_tutorials vs $rospack depends1 roscpp_tutorials

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

Dependency Exports
------------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 14

.. code:: bash

  $ rospack export --lang=cpp --attrib=cflags roscpp_tutorials

  -I/opt/ros/electric/stacks/ros_tutorials/roscpp_tutorials/srv/cpp -I/opt/ros/electric/stacks/ros_tutorials/roscpp_tutorials/srv_gen/cpp/include  -I/opt/ros/electric/stacks/ros_comm/clients/cpp/roscpp/include -I/opt/ros/electric/stacks/ros_comm/clients/cpp/roscpp/msg_gen/cpp/include -I/opt/ros/electric/stacks/ros_comm/clients/cpp/roscpp/srv_gen/cpp/include      -I/opt/ros/electric/stacks/ros_comm/clients/cpp/roscpp_serialization/include  -I/opt/ros/electric/stacks/ros_comm/clients/cpp/roscpp_traits/include  -I/opt/ros/electric/stacks/ros_comm/utilities/xmlrpcpp/src  -I/opt/ros/electric/stacks/ros_comm/tools/rosconsole/include  -I/opt/ros/electric/stacks/ros_comm/utilities/rostime/include  -I/opt/ros/electric/stacks/ros_comm/utilities/cpp_common/include   -I/opt/ros/electric/stacks/ros_comm/messages/rosgraph_msgs/msg_gen/cpp/include  -I/opt/ros/electric/stacks/ros_comm/messages/std_msgs/include -I/opt/ros/electric/stacks/ros_comm/messages/std_msgs/msg_gen/cpp/include   -I/opt/ros/electric/stacks/ros_comm/messages/std_srvs/srv_gen/cpp/include  -I/opt/ros/electric/stacks/ros_comm/messages/std_msgs/include -I/opt/ros/electric/stacks/ros_comm/messages/std_msgs/msg_gen/cpp/include  -I/opt/ros/electric/ros/core/roslib/msg_gen/cpp/include -I/opt/ros/electric/ros/core/roslib/include  -I/opt/ros/electric/ros/tools/rospack -I/opt/ros/electric/ros/tools/rospack/include  

.. note:: Many more features we don't have time to cover.  

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
- show rxconsole
- show logger levels



Inside Talker (Python)
----------------------

.. page-style:: 
   :font_size: 24
   :align: left
   :literal.font_size: 24


.. code:: python

  import roslib; roslib.load_manifest('rospy_tutorials')
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

  import roslib; roslib.load_manifest('rospy_tutorials')

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

ROS Wiki: www.ros.org

There are indexes on the home page. 

Click "Browse Software" to browse or search the meta data fields

Where to get help
-----------------

answers.ros.org

Search first, then ask. 

Make sure to tag well. 

Follow www.ros.org/wiki/Support guidelines



