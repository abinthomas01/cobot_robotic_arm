
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
like that the RViz is a visual debugging + planning tool, running continusly, each small movement will display on the rviz, it will plan the movement and exicute exactly like that, we can change the position of robot however we want in rviz, eg: if we want to take a position of the robot and that is not in a perfect place, insted of coding we can directly change the position,
it will provide the sensor data, like camera, etc.. 
next is moveit, it's a motion planning system for robots, it will calculate the path from one position to another position, and avoide the colition which is in the path, this will convert the joint angles, from one position to another position

after the installation check is everything is there, the files wont be there, some files will be missing, so check carefully, for that i will give my full list of files, in different systen the files will be different, that time my gazebo is looks like this, withot the robot, just empty world.

<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-03-06%2011-06-44.png" />

after these installation we need to downlod the cobot robot, if you ask about that to chat gpt you will get the code, i dont that with terminal.
the first problem i faced is the robot is not showing inside the gazebo, so i checked everything from the beginning, that's how i understand i didnt downlod few files, adn i didnt movit, after the installation i check once more but that was not there, with the help of claude AI i understand the rbot was not there it is because the updated file, the old version will work but the updated version of the robot wont work, so check the version, always check the version is compatable or not.
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-03-08%2016-33-47.png" />

the robot appeared on the gazebo the next step is giving a gripper to the cobot, so we choose vacuum gripper insted of 2 finger gripper, we installed the packages for the gripper using claude, the gripper is also now showing at the beginning the i check inside the gazebo the i changed few things drom it, i will provide the picture
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-03-18%2014-58-23.png" />
after the installation of gripper the robot will looks like this
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-03-10%2014-18-01.png" />

the next step is to build few thing in gazebo which is build the table, 6 boxes, 3 different color basket, but is seems like 1 basket, so for that we installed vs code and all the files give to vs code, exactly saying, the ur5_ws folder, i uploded there so we can add and edit the code easly, 
i will sent the code, i done in the vs code, just put exactly like that, check "spown_box.py" code
"red_box.py", check that code that is for working all at onece, once we run the code the robot will star to move and take all the boxes one by one, place it over the basket based on the color, first blue box, then the red box, after that the green box. it will pick one by one and place in order.
we give 4 position for movement, Home -> Move ABOVE box -> Lift UP -> Move to basket, then again going to home, 
the working is like this.
Home -> 
Move ABOVE box -> 
Vacuum ON ->
Lift UP -> 
Move to basket ->
Vacuum OFF ->
Home

if you want to see the boxes inside the rviz you can use the "add_seen_object.py", so that way it will be easy to see and controll the robotic arm
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-03-18%2014-45-52.png" />

now it will work well, but the thing is it is fixed position, the boxes and the robot, not dynamic.

i give my boxe's position and the robot position, it will move one position to another, 
eg: if we are in home position and if we need to move above the box we need to give 2 location, i is home's position and the above the box position, based on the position the joint angle will change. 

<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-04-22%2013-43-05.png" />


after the working we updated few things, i tryed to do that dynamicaly, so for that i added camera n top of the robot, first i tried to place in the robot arm, but that will not work in simulation, because of the camera view, if we add the camera on top of the gripper when it try to pick the box the camera view pass through the boxes, so the picking won't work, the line and the mirrir like thing, that is the camera view, 
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-03-28%2022-07-55.png" />

now the camera on top of the robot like this
<img width="993" height="612" alt="Screenshot from 2026-03-25 12-31-10" src="https://github.com/abinthomas01/cobot_robotic_arm/blob/main/assets/Screenshot%20from%202026-04-21%2020-18-15.png" />

