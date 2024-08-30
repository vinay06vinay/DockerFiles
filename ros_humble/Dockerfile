FROM osrf/ros:humble-desktop-full

SHELL [ "/bin/bash" , "-c" ]

# Set environment variables and suppress additional permissions while installing packages
ENV DEBIAN_FRONTEND=noninteractive


# Install general Ubuntu tools and ROS-related packages
RUN apt-get update && apt-get install -y \
    # General Ubuntu tools. Add more tools as required
    build-essential \
    terminator \
    nano \
    gedit \
    git \
    # ROS related packages. Add more as required
    ros-humble-rqt \
    ros-humble-tf2-tools \
    ros-humble-turtlesim \
    ros-humble-gazebo-ros-pkgs \
    ros-humble-turtlebot3* \
    python3-colcon-common-extensions \
    ros-humble-turtlebot4-desktop \
    && apt-get clean && rm -rf /var/lib/apt/lists/*


RUN apt-get clean all
# Install Git
RUN apt-get update && apt-get install -y git

# Add a function to .bashrc to set up the ROS Humble environment
RUN echo 'source /opt/ros/humble/setup.bash' >> /root/.bashrc && \
    echo 'export TURTLEBOT3_MODEL=waffle_pi' >> /root/.bashrc
# Setup a localhost variable
RUN echo 'export ROS_LOCALHOST_ONLY=1' >> /root/.bashrc


RUN source /opt/ros/humble/setup.bash && \
    mkdir -p /humble_ws/src 

# Set the working folder at startup
WORKDIR /humble_ws

# Default command to run when the container starts
CMD ["bash"]