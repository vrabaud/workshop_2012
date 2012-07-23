.. page-load-style:: styles/main


How does it work?

- Build System

- Communications Middleware

- Community of developers and libraries

Build System Features
---------------------

.. load-style:: styles/current

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

'''$rospack depends roscpp_tutorials''' vs $rospack depends1 roscpp_tutorials

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

