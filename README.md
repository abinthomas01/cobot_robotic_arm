
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/user-attachments/assets/6841e1a0-1e6b-4a49-856b-99f6c44d0e20" />

# cobot_robotic_arm
complete simulation setup of the cobot robotic arm in ROS2 and Gazebo using vacuum gripper for the arm, enabling motion planning, joint control, and pick-and-place tasks in a virtual environment. The project covers robot modeling, controllers, MoveIt2 integration, and environment interaction to mirror real-world robotic manipulation scenarios.

The objective of this project is to:
•	Simulate a cobot robot in Gazebo
•	Integrate MoveIt for motion planning
•	Implement a vacuum gripper system
•	Perform automated pick-and-place operations on multiple objects

the technology we used is 
    gazebo simulater
    moveit
    ROS2
    python

we need to carefull in 1 thing, the version of all the components and technologys we used need to be compatabale, if it is not the system wont work.

when we install ubuntu the new vwrsion wont work so we need to install ubuntu 22.04 LTS is better or we can use ubentu 20.04 LTS version. 

Go to official website:
👉 https://ubuntu.com/download/desktop

when i try to install the ubunt on my laptop i faced a small prolem which is the graphycs, ram, 3d visual, etc, and with that so many errors, it took almost 1 days to fix everything and downloding everything (to understand things and installation took somuch time), then i stat to install the ros2 on the ubuntu, that was the 2 time consuming part, 

ros2 installation link.
https://docs.ros.org/en/humble/Installation.html.

choose ypur platform the run all the given code, the last 2 line of code will take so much time, in my laptop it took morethan 5 hr, while that running dont off your internet, there are so mant files need to downlod, around morethat 300 files, so that why it taking so much time, 

after that with the help of chat gpt i downlod the gazebo and rviz, 
the ros2 is like communication channel between rviz and gazebo, all the physics based simulation is happaning in the gazebo and the output like things displayed over the rviz, eg: if we need to move the box from one position to another position so for that we using cobot robot, the gripper cuck the box, while the movement the gripper velosity, the angle, the position weight, everything is calculating and sent these thing one joint to another joint using ros2, so the calculation part, the physics thing happaning over the gazebo.
like that the rviz will give the movement like video, running continusly, each small movement will display on the rviz

