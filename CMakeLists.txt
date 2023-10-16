cmake_minimum_required(VERSION 3.5)
project(conceptio_interfaces)

find_package(ament_cmake_ros REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geographic_msgs REQUIRED)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

rosidl_generate_interfaces(${PROJECT_NAME}
  msg/Utm.msg
  msg/Remoteid.msg
  msg/CapellaPropertyValue.msg
  msg/CapellaTrigger.msg
  msg/ArenaKinematics.msg
  msg/ArenaHeartbeat.msg
  msg/ArenaEntities.msg
  srv/RequestArenaEntityList.srv
  DEPENDENCIES geographic_msgs
)

ament_export_dependencies(
  rosidl_default_runtime
  geographic_msgs)

ament_package()
