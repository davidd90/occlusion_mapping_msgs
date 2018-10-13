cmake_minimum_required(VERSION 2.8.3)
project(occlusion_mapping_msgs)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
	roscpp
  	std_msgs
	message_generation
)


################################################
## Declare ROS messages, services and actions ##
################################################

add_message_files(
  FILES
  GroundPlaneStamped.msg
)
add_service_files(
  FILES
  AddBBX.srv
  RemoveBBX.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
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
	CATKIN_DEPENDS
		message_runtime
#	DEPENDS boost
)


#############
## Install ##
#############

## Mark cpp header files for installation
install(DIRECTORY include/${PROJECT_NAME}
	DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
	FILES_MATCHING PATTERN "*.h"
	PATTERN ".git" EXCLUDE
)
