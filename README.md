# Chemistry-Inspired Pattern Formation with Robotic Swarms
## 2022 IEEE RA-L with ROS

[![IMAGE ALT TEXT HERE](media/video.png)](https://www.youtube.com/watch?v=y7ls4djT3W4)

Dynamic Gibbs random field applied to swarm morphogenesis abstracting chemical binding mechanism.

## Abstract
```Self-organized emergent patterns can be widely seen in particle interactions producing complex structures such as chemical elements and molecules. Inspired by these interactions, this work presents a novel stochastic approach that allows a swarm of heterogeneous robots to create emergent patterns in a completely decentralized fashion and relying only on local information. Our approach consists of modeling the swarm configuration as a dynamic Gibbs Random Field (GRF) and setting constraints on the neighborhood system inspired by chemistry rules that dictate binding polarity between particles. Using the GRF model, we determine velocities for each robot, resulting in behaviors that lead to the emergence of patterns or shapes. Simulated experiments show the versatility of the approach in producing a variety of patterns, and experiments with a group of physical robots show the feasibility in potential applications.```

## Media
- [Video](https://youtu.be/y7ls4djT3W4)

## Dependecies

-  [ROS Melodic](http://wiki.ros.org/melodic/Installation)
-  [Gazebo 11](http://gazebosim.org/download)
- [Hero Common](https://github.com/verlab/hero_common)

## Installation

-   Using git (or download the zip file) clone this repository into the "source code" folder of your ROS workspace (e.g. ~/catkin_ws/src ).

```sh
$ cd ~/catkin_ws/src
$ git clone https://github.com/rezeck/gibbs_swarm_pattern_formation.git
$ git clone https://github.com/verlab/hero_common.git # for gazebo simulations and real robots
```

-   Fixing package dependencies:

```sh
$ cd ~/catkin_ws
$ rosstack profile && rospack profile
$ rosdep install --from-paths src/gibbs_swarm_pattern_formation --ignore-src -r -y
```

## Usage
### Numeric Simulations
```sh
$ roslaunch gibbs_swarm_pattern_formation grf_swarm.launch
```

### Gazebo Simulations
```sh
$ roslaunch hero_gazebo gazebo_bringup.launch
$ roslaunch hero_gazebo env_spawn_bridge.launch
$rosrun gibbs_swarm_pattern_formation gibbs_swarm_pattern_formation_gazebo
```

### Real Robots
```sh
$ roslaunch hero_bringup hero_bringup.launch
$ rosrun gibbs_swarm_pattern_formation gibbs_swarm_pattern_formation_real
```