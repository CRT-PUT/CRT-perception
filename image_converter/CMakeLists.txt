cmake_minimum_required(VERSION 2.8.3)
project(image_converter)
find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  sensor_msgs
  std_msgs
  tf
)
find_package(OpenCV REQUIRED)
catkin_package(
CATKIN_DEPENDS cv_bridge image_transport roscpp sensor_msgs std_msgs
)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
add_executable(image_converter src/image_converter.cpp)
target_link_libraries(image_converter ${OpenCV_LIBS} ${catkin_LIBRARIES})
