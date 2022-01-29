cmake_minimum_required(VERSION 2.8.3)
project(sparse_stereo_msgs)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  message_generation
  std_msgs
  geometry_msgs
 # tf2
 # tf2_eigen
)

add_message_files(
  FILES
  TrackedPoint.msg
  TrackedPointList.msg
  TrackedLine.msg
  TrackedLineList.msg
)
generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
  INCLUDE_DIRS #${tf2_INCLUDE_DIRS} ${tf2_eigen_INCLUDE_DIRS}
#  LIBRARIES pips_msgs
  CATKIN_DEPENDS  message_runtime std_msgs geometry_msgs #tf2 tf2_eigen
  DEPENDS 
)

#message([WARN] "${tf2_INCLUDE_DIRS} ${tf2_eigen_INCLUDE_DIRS}")

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
# include_directories(include)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
