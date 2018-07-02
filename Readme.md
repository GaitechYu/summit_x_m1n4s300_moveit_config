# MoveIt config files for Summit X with Kinova arm

This package allows to use a 4DOF Mico (m1n4s300) from Kinova in a Summit X.

## Interacting with the arm using Moveit Rviz plugin

Launch the kinova driver:

> roslaunch kinova_bringup kinova_robot.launch kinova_robotType:=m1n6s300

Notice that the robotType is m1n6s300. This is because the planner didn't work with a 4DOF arm  when creating this package with the Moveit! setup assistant. It is used the description file of the m1n4s300 adding two fake joints.

Launch the demo:

> roslaunch summit_x_m1n4s300_moveit_config summit_x_demo.launch

This launches:
-   move_group node with controllers
-   joint_trajectory_action_server node available in kinova_driver
-   gripper_command_action_server node available in kinova_driver
-   rviz

**Note:** This configuration will move the actual robot, so be careful before you execute your trajectories.