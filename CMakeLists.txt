cmake_minimum_required(VERSION 2.8.3)
project(teleoperation_msgs)

set(PACKAGE_DEPENDENCIES
  geometry_msgs
  message_generation
  std_msgs
  sensor_msgs
  actionlib_msgs
  nav_msgs
)

# Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  ${PACKAGE_DEPENDENCIES}
)

add_message_files(
    FILES
    WrenchPoseStamped.msg
    WrenchPoseTrajectory.msg
    DynaTeleop.msg
    DualDynaTeleop.msg
)

# # Declare the service files to be built
# add_service_files(
#         FILES
#         TriggerStamped.srv
# )

# add_action_files(
#   DIRECTORY
#     action
#   FILES
#     JointPosition.action
#     ReachPose.action
#     MoveToPose.action
#     MiraPointer.action
#     ResetTeleop.action
#     FollowTrajectory.action
# )

generate_messages(
  DEPENDENCIES
    std_msgs
    geometry_msgs
    nav_msgs
    actionlib_msgs
    sensor_msgs
)

# Generate a package
catkin_package(CATKIN_DEPENDS
  ${PACKAGE_DEPENDENCIES}
)
