# optimal\_active\_guidance\_in\_mixed\_reality\_using\_prior\_floorplans
**optimal\_active\_guidance\_in\_mixed\_reality\_using\_prior\_floorplans** is a Semester Thesis project based upon the modular sample based active path planning approach [Mav Active 3d Planning](https://github.com/ethz-asl/mav_active_3d_planning/).

The goal of this project is:
- To incorporate strong prior knowledge of an environment in the form of a floorplan into the active path planning approach.
- To develop a novel approach to incorporate the floorplans in a suitable format into the information gain formulation.
- To evaluate the system with regards to current state of the art approaches that do not rely on prior knowledge.
- To build and showcase a simple mixed reality application that uses the developed system to guida a user to explore an environment.
  
# Setup

The project was intended to run on a Windows machine with WSL2 support. One would run the Simulation environment in Windows, whilst building & running the code in WSL2 on an Ubuntu 18.04 build.

## Windows

**Unreal**

1. Download Unreal 4.25

2. Download [Maze Environment]()
<!-- TODO: Make somehow available -->

3. Open the project in the Unreal 4.25

4. Play the game

5. Drag FusionCameraActor5 Under UnrealCVPawn

6. Change the location of FusionCameraActor5 to 0,0,0 (default will be 0, 0, 150.0)

**Nvidia Omniverse Isaac Sim**

TBD

## WSL 2

1. Setup mav_active_3d_planning package by following the documentation in [mav_active_3d_planning](mav_active_3d_planning/)

2. Setup unrealcv for Unreal 4.25 environment by substituting original unreal_cv_ros dependency with [makeecat/unreal_cv_ros: Unreal CV ROS Perception Simulator (github.com)](https://github.com/makeecat/unreal_cv_ros)
<!-- TODO: Change this dependency to personal fork -->

3. Setup IP of unreal_cv_ros
```
rosed unreal_cv_ros unreal_ros_client.py
# change ip of unreal_ros_client to its host ip: client = Client(('HOST_IP',9000))
```

# Run Experiments

## Unreal

1. launch active_3d_planning experiment for Maze

```
roslaunch active_3d_planning_app_reconstruction example.launch planner_config:=planners/exploration_planner.yaml experiment_config:=Maze.yaml uecv_mode:=standard
```

2. You can see Unreal Game Playe changing views, and rviz shows planned trajectory and moving the agents. If the ros node crash, try rebuilding "unreal_cv_ros" package

## Isaac Sim

TBD


