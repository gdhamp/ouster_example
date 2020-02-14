# Files Changed
ouster_client/include/ouster/os1_util.h
ouster_client/src/os1_util.cpp
ouster_ros/CMakeLists.txt
ouster_ros/include/ouster_ros/os1_ros.h
ouster_ros/include/ouster_ros/point_os1.h
ouster_ros/os1.launch
ouster_ros/src/os1_ros.cpp

#Files Added
ouster_ros/src/os1_laserscan_node.cpp


Added a new file for the laserscan node and added some vars in the OS1 namespace
for laserscan and got it to build and run. Added method make_closest_xyz_lut to gather
the closest points based on the calculated z for each point in each column. 
I took this approach to avoid creating a vector bigger than neccesary for the xyz data since
we are only interested in the closest point in each column. It also made sance to calculate
z first since if it isn't the closest point, the data point is ignored so why bother calculating
x and y.  I'm not completely sure that the z value really represensts distance but it
seemed from the OS1 Software User Guide page 23 that this is the calcualtion that they suggest.
I still need to pour this into the laserscan variable and look at visualization.

