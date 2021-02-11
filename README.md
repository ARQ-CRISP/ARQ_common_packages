# ARQ_common_packages
Repository containing all the packages required to integrate and run the robots we have in our lab at Advanced Robotics at Queen Mary University of London

## arq_robots
This ROS package contains urdf and controller files describing the robots we have in the ARQ lab and how to control them.

## arq_description_common
This ROS package contains all files that describe the different environments at ARQ. This ROS package (whatever its name) must contain all required information regarding the robot's setup. It gathers gazebo __.__world files, as well as all the models required to display it and scenes in order to restrain robot's movement and having proper collision checking (.scene files). These files should be shared among the following directories.
```
- models
- scenes
- worlds
```
The folder named __*models*__ must contain at least all the objects used to compose a world, defined as sdf files. It is also **strongly** recommended to add inside the same folder all the objects you want to be able to spawn in gazebo.
The minimal directory structure of `models` is the following:
```
models
+-- <model_using_mesh_name>
|   +-- meshes
|       +-- <model_using_mesh_name>.stl
|   +-- model.config
|   +-- model.sdf
+-- <model_no_mesh_name>
|   +-- model.config
|   +-- model.sdf
```
Please note that the meshes can only be *.dae* files, allowing you to add texture. These models, will allow you to create Gazebo worlds. It exists several ways of creating gazebo *worlds*, but we encourage to follow the steps described [here](https://shadow-experimental.readthedocs.io/en/latest/user_guide/1_6_software_description.html#creating-a-new-world-scene) (all required dependencies are installed in the docker). If you are not a big fan of GUI and you already have a good hang of how Gazebo world files are working, you can still create your world by going on the [wiki](https://github.com/ARQ-CRISP/ARQ_common_packages/wiki/How-to-create-a-Gazebo-world-without-using-the-GUI). </br>
If you followed this [link](https://shadow-experimental.readthedocs.io/en/latest/user_guide/1_6_software_description.html#creating-a-new-world-scene) you should already know how to create a *.scene* from *.world* file. The former allows you to gather all the obstacles constraining your robot's workspace and make sure to plan accordingly to the real scene.
