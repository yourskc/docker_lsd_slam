# docker_lsd_slam

This Image can use in Linux OS and windows OS with Installed WSL (Windows Subsystem for Linux) 

### 1.   Pull docker images 

   Pull the images from docker hub using the command:

   - *docker pull yourskc/skc_lsd*

### 2.   Run container

   a. To run container in Linux OS:

   - *docker run -it --name ***{name}** --privileged=true --net=host -e DISPLAY --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1  yourskc/skc_lsd*

   b. To run container in windows 10 with WSL (Windows Subsystem for Linux), you must install X server such as in here I use X410:

   - *docker run -it --name ***{name}** --privileged=true --net=host -e DISPLAY=docker.for.win.localhost:0.0 --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1 yourskc/skc_lsd*

***{name}** : modify this name with your own

### 3.   Get in to container

   open termial window and input
   
   - *docker exec -it {name-container} bash*

### 4.   Test the image can work

   The easist way to test ROS(Robot Operating System) node is running the turtle simulator. Please repeat step 3 to open three terminal window and input the followings seperately:
  
  a. run roscore

   - *roscore*

  b. run turtle simulator

   - *rosrun turtlesim turtlesim_node*

  c. run turtle key controller, use arrow keys to make the movements

   - *rosrun turtlesim turtle_teleop_key*


