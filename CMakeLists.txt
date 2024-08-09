cmake_minimum_required(VERSION 3.10.0)
set(CMAKE_EXPORT_COMPILE_COMMANDS 1)
project(optitrack_perception_module)

add_compile_options(-std=c++14)

find_package(catkin REQUIRED COMPONENTS
  optitrack_msgs
  overworld
  pluginlib
  roscpp
)
find_package(ontologenius REQUIRED CONFIG)

catkin_package(
  CATKIN_DEPENDS overworld ontologenius roscpp
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_library(${PROJECT_NAME}
  src/OptitrackPerceptionModule.cpp
)
target_link_libraries(${PROJECT_NAME} PUBLIC
                      ${catkin_LIBRARIES}
                      ${overworld_LIBRARIES}
                      ${ontologenius_LIBRARIES}
                      ontologenius::ontologenius_compat)
add_dependencies(${PROJECT_NAME} optitrack_msgs_generate_messages_cpp)