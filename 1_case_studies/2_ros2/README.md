\newpage

## Robot Operating System (ROS) 2

The Robot Operating System (ROS) is the de *facto* standard for robot application development [@Quigley09]. It's a framework for creating robot behaviors that comprises various stacks and capabilities for message passing, perception, navigation, manipulation or security, among others. It's [estimated](https://www.businesswire.com/news/home/20190516005135/en/Rise-ROS-55-total-commercial-robots-shipped) that by 2024, 55% of the total commercial robots will be shipping at least one ROS package.
ROS is to roboticists what Linux is to computer scientists.

This case study will analyze the security of ROS 2[^1] and demonstrate how flaws on both ROS 2 layer or its underlayers lead to the system being compromised.

[^1]: ROS 2 is the second edition of ROS targeting commercial solutions and including additional capabilities. ROS 2 (Robot Operating System 2) is an open source software development kit for robotics  applications. The purpose of ROS 2 is to offer a standard software platform to developers across industries that will carry them from research and prototyping through to deployment and  production. ROS 2 builds on the success of ROS 1, which is used today in myriad robotics applications  around the world.


### Dockerize the target environment
ROS 2 is nicely integrated with Docker, which simplifies creating a hacking development environment. Let's build on top of the default ROS 2 containers and produce two targets for recent ROS 2 releases:
- ROS 2 Foxy (latest LTS)
- ROS 2 Galactic (latest release)

### Build from source and run

```bash
# Build
docker build -t hacking_ros2:foxy --build-arg DISTRO=foxy .

# Run, using X11
xhost + # (careful with this)
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/home/xilinx/.Xauthority tb3nav2_demo:latest

# Run setup (inside container)
byobu -f configs/poc.conf attach
```

## Use pre-built containers

### `galactic`
```bash
docker pull registry.gitlab.com/xilinxrobotics/tb3nav2_demo:galactic
xhost + # (careful with this)
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/home/xilinx/.Xauthority registry.gitlab.com/xilinxrobotics/tb3nav2_demo:galactic

# Run setup (inside container)
byobu -f configs/poc.conf attach
```

### `foxy`
```bash
docker pull registry.gitlab.com/xilinxrobotics/tb3nav2_demo:foxy
xhost + # (careful with this)
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/home/xilinx/.Xauthority registry.gitlab.com/xilinxrobotics/tb3nav2_demo:foxy

# Run setup (inside container)
byobu -f configs/poc.conf attach
```