cmake_minimum_required(VERSION 3.0.2)
project(recive_rgb)
add_compile_options(-std=c++11)
find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  rospy
  sensor_msgs
  std_msgs
)
find_package(OpenCV 4.1.0 REQUIRED)
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES recive_rgb
 CATKIN_DEPENDS cv_bridge image_transport roscpp rospy sensor_msgs std_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS}
)
add_executable(recive_rgbc src/recevice_rgb.cpp)
target_link_libraries(recive_rgbc ${catkin_LIBRARIES} ${OpenCV_LIBS})

