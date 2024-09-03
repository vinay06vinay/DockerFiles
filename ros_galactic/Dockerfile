FROM osrf/ros:galactic-desktop

SHELL [ "/bin/bash" , "-c" ]

# Set environment variables and suppress additional permissions while installing packages
ENV DEBIAN_FRONTEND=noninteractive

# Install general Ubuntu tools and ROS-related packages
RUN apt-get update && apt-get install -y \
    # General Ubuntu tools. Add more tools as required
    build-essential \
    terminator \
    nano \
    cmake \
    vim \
    wget \
    gedit \
    git \
    # ROS-related packages. Add more as required
    ~nros-galactic-rqt* \
    ros-galactic-tf2-tools \
    ros-galactic-turtlesim \
    ros-galactic-gazebo* \
    ros-galactic-turtlebot3* \
    ros-dev-tools \
    ros-galactic-turtle-tf2-py \
    ros-galactic-tf2-tools\
    ros-galactic-tf-transformations \
    python3-colcon-common-extensions \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Add a function to .bashrc to set up the ROS Galactic environment
RUN echo 'source /opt/ros/galactic/setup.bash' >> /root/.bashrc && \
    echo 'export TURTLEBOT3_MODEL=burger' >> /root/.bashrc

# Setup a localhost variable
RUN echo 'export ROS_LOCALHOST_ONLY=1' >> /root/.bashrc

# Source ROS Galactic
RUN source /opt/ros/galactic/setup.bash && \
    mkdir -p /ros2_ws/src 

# Set the working folder at startup
WORKDIR /ros2_ws

# Default command to run when the container starts
CMD ["bash"]