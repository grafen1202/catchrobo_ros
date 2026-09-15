cmake_minimum_required(VERSION 3.8)
project(robot_arm_description)

find_package(ament_cmake REQUIRED)

install(DIRECTORY
  launch
  urdf
  DESTINATION share/${PROJECT_NAME}
)

# Mesh assets may be supplied locally and are ignored by Git.
if(EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/meshes")
  install(DIRECTORY meshes
    DESTINATION share/${PROJECT_NAME}
  )
endif()

ament_package()
