# gummi_moveit
Core files for Moveit! for the GummiArmCE.

### How to launch it

Requires gummi_base + gummi_ee + gummi_interface (required for node "gummi_right_arm_controller of type "follow_joint_trajectory.py" - not necessary for simulation, but still loaded in demo) 

#### Simulated robot

    $ roslaunch gummi_moveit demo.launch

#### Simulated robot with gui interface

    $ roslaunch gummi_moveit demo.launch usegui:=true

#### Run it on the real robot

1. Launch manager (roscore and the usb dongles for the dynamixels):

    `$ roslaunch gummi_base_XXX manager.launch`
    
2. Launch controllers (defines what motor acts on which joint): 

    `$ roslaunch gummi_base_XXX controllers.launch`

3. Launch gummi (loads antagonists, PIDs, encoder feedbacks, sets contraction levels, initializes joints, etc):

**ATTENTION: This is the first package that actually makes the robot move, be ready to shut it down promptly in case of improper behaviour**

    `$ roslaunch gummi_interface gummi.launch`

4. Run moveit planner with rviz interface:

    `$ roslaunch gummi_moveit gummi_moveit.launch`


<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />

This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
