FROM althack/ros:noetic-gazebo

# ** [Optional] Uncomment this section to install additional packages. **
#
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
    && git clone https://github.com/Livox-SDK/Livox-SDK.git \
    && cd Livox-SDK \
    && cd build && cmake .. \
    && make \
    && sudo make install
ENV DEBIAN_FRONTEND=interactive

# Set up auto-source of workspace for ros user
ARG WORKSPACE
RUN echo "if [ -f /opt/ros/noetic/setup.bash ]; then source /opt/ros/noetic/setup.bash; fi" >> /home/ros/.bashrc
