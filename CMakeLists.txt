cmake_minimum_required(VERSION 2.8.3)
project(ethzasl_apriltag)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  cv_bridge
  sensor_msgs
  image_transport
  tf
  visualization_msgs
  dynamic_reconfigure
  cmake_modules
)

generate_dynamic_reconfigure_options(
  cfg/ethzasl_apriltagParams.cfg
)

find_package(OpenCV REQUIRED)
find_package(Eigen3 REQUIRED)

add_definitions(-std=c++11)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
  ${EIGEN3_INCLUDE_DIR}
  ${EIGEN3_INCLUDE_DIR}/unsupported/
  ${ESM_HEADER}
)

catkin_package(
  INCLUDE_DIRS include
)

add_subdirectory(application)

