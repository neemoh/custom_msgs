cmake_minimum_required(VERSION 2.8.3)
project(custom_msgs)

find_package(catkin REQUIRED COMPONENTS geometry_msgs message_generation std_msgs)

# For point_cloud2.py
#catkin_python_setup()

include_directories(include)

add_message_files(
  DIRECTORY msg
  FILES
  TaskState.msg
)


generate_messages(DEPENDENCIES geometry_msgs std_msgs)

catkin_package(
  CATKIN_DEPENDS geometry_msgs message_runtime std_msgs)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h")


