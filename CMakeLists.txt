cmake_minimum_required(VERSION 3.8)
project(gazebo_no_physics_plugin)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# find_package(rclcpp REQUIRED) find_package(gazebo_ros REQUIRED)
find_package(gazebo_dev REQUIRED)

# link_directories(${gazebo_dev_LIBRARY_DIRS})

add_library(gazebo_no_physics_world_plugin SHARED src/no_physics_world_plugin.cpp)
target_include_directories(
    gazebo_no_physics_world_plugin PRIVATE $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
                                           $<INSTALL_INTERFACE:include>
)

ament_target_dependencies(gazebo_no_physics_world_plugin gazebo_dev # "gazebo_ros" "rclcpp"
)
ament_export_dependencies(gazebo_dev)

# ament_export_libraries(gazebo_no_physics_world_plugin)
ament_export_targets(GazeboNoPhysicsPlugin HAS_LIBRARY_TARGET)
# ament_export_dependencies(rclcpp)

# ament_export_dependencies(gazebo_ros)
ament_export_include_directories(include)
ament_export_libraries(gazebo_no_physics_world_plugin)

# ament_environment_hooks("${CMAKE_CURRENT_SOURCE_DIR}/env-hooks/gazebo_plugins.sh.in")

install(DIRECTORY include/ DESTINATION include)

install(
    TARGETS gazebo_no_physics_world_plugin
    EXPORT GazeboNoPhysicsPlugin
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
    RUNTIME DESTINATION bin
    INCLUDES
    DESTINATION include
)

ament_package()
