# Two Simple Projects for ROS2 Jazzy, Ubuntu 24:
## 1. Blender_test_core was made for experimenting with chain: Blender -> LinkForge -> ros2 -> Gazebo -> RVIZ  
  '_etalon' xacro was made without Blender.   
  NOTES:  
    link to mesh in .xacro:  
      `<mesh filename="file://$(find blender_test_core)/meshes/neck_link_visual.stl" />`  
    in LinkForge -> Gazebo plugin: `gz_ros2_control-system`. It is the filename in gazebo plugin.  
    Add name="gz_ros2_control::GazeboSimROS2ControlPlugin"  
    
    
    <gazebo>  
      <plugin name="gz_ros2_control::GazeboSimROS2ControlPlugin" filename="gz_ros2_control-system">  
        <parameters>$(find blender_test_core)/config/my_robot_controllers.yaml</parameters>  
      </plugin>  
    </gazebo>    
    
Controll: 

`ros2 topic pub /position_controller/commands std_msgs/msg/Float64MultiArray "{data: [-1.0, 2.0]}" -1 ` 

## 2. my_robot project is simple diffdrive example.
Controlled with teleop_twist_keyboard: 
    
      `ros2 run teleop_twist_keyboard teleop_twist_keyboard   --ros-args -r /cmd_vel:=/cmd_vel ` 


   

    
