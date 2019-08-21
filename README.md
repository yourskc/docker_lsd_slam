# docker_lsd_slam

This Image can use in Linux OS and windows OS with Installed WSL (Windows Subsystem for Linux) 

1. Pull docker images 

   Pull the images from docker hub using the command:

   - *docker pull yourskc/skc_lsd*


2. Build container

  a. To build container in Linux OS you can use the command:

  - *docker run -it --privileged=true --net=host -e DISPLAY --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1 --name {name-container} yourskc/skc_lsd /bin/bash*

  b. To build container in windows OS with Installed WSL (Windows Subsystem for Linux) or using CMD you must install Xserver such as in here I use X410:

  - *docker run -it --privileged=true --net=host -e DISPLAY=docker.for.win.localhost:0.0 --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1 --name {name-container} yourskc/skc_lsd /bin/bash*

***{name-container}** : modify this name with your own

3. Get in to container

  a. Linux:

  - *docker exec -it -e DISPLAY {name-container} bash*

  b. WSL

  - *docker exec -it -e DISPLAY=docker.for.win.localhost:0.0 {name-container} bash*

  The easist way to test ROS(Robot Operating System) node is running the turtle simulator. Follow this guide in the docker container:
  
4. Test the image can work

  a. run roscore

  - *roscore*

  b. run turtle simulator

  - *rosrun turtlesim turtlesim_node*

  c. run turtle key controller, use arrow keys to make the movements

  - *rosrun turtlesim turtle_teleop_key*


