cmake_minimum_required(VERSION 2.8.3)
project(goal_monitor)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  geometry_msgs
  sem_nav_msgs
  tf
)



catkin_package(
  INCLUDE_DIRS include
  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS roscpp rospy std_msgs geometry_msgs tf
#  DEPENDS system_lib
)

include_directories(include)
include_directories(
  ${catkin_INCLUDE_DIRS}
  ${roscpp_INCLUDE_DIRS}
)

add_library(goal_monitor
  src/goal_monitor.cpp
)
target_link_libraries(goal_monitor
  ${catkin_LIBRARIES}
  ${roscpp_INCLUDE_DIRS}
)

#add_executable(goal_monitor_node
#  src/goal_monitor_node.cpp
#)
#target_link_libraries(goal_monitor_node goal_monitor)


