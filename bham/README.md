bham
===========

The package provides a simulation of the CS building at Birmingham. This comprises of a Blender model of the building (data/CS_Building.blend) and a couple of Morse actuators to simulate the four-level lift.

To test it out, get bham on your ROS path and run:

 rosrun bham simulator.sh

and after that has loaded up:

 rosrun bham lift_controller.py.

In the current simulation a B21 is sitting in the centre of floor 1. It can be controlled through ROS using /b21/cmd_vel. 

The lift is controlled by publishing a std_msgs/Bool message on  "/lift_sim/[command|call]floor", where floor is [B|G|1|2]. These topics correspond to a user pressing the "call" button on the outside of the lift, or the "command" button on the inside of the lift to goto to "floor". The lift travels in the order requested, and waits 8 seconds before closing the door.

