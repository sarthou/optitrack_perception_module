cmake_minimum_required(VERSION 3.0.2)
project(optitrack_perception_module)

add_compile_options(-std=c++17)

find_package(catkin REQUIRED COMPONENTS
  optitrack_msgs
  overworld
  pluginlib
  roscpp
)
catkin_package()

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_library(${PROJECT_NAME}
  src/OptitrackPerceptionModule.cpp
)
target_link_libraries(${PROJECT_NAME} PUBLIC
                      ${catkin_LIBRARIES}
                      ${overworld_LIBRARIES})
target_compile_definitions(${PROJECT_NAME} PUBLIC OWDS_ROS_VERSION=$ENV{ROS_VERSION}) 