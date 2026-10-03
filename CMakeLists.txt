cmake_minimum_required(VERSION 3.10)
project(robot_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ImuData.msg"
  "msg/MotorCommand.msg"
  "msg/MotorStatus.msg"
  "msg/Ping.msg"
  DEPENDENCIES std_msgs
)

ament_package()
