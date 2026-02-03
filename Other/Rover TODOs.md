1) Robot agnostic high level orchestration and low level robot specific drive are connected via `cmd_vel` topic. Nav2 publishes to this and we need to subscribe to this and send it to the VESCs.
	1) Currently the VESC control node subscribes to `joy` and publishes to `front_left/commands/motor/speed`. 
	2) We need to put a node in the middle that subscribes to joy and publishes to `cmd_vel` so our existing teleop system continues to work, while adding a new node that reads from `cmd_vel` and publishes to `front_left/commands/motor/speed`.

2) Write URDF and get teleop in sim working

3) Run sim and irl rover that both read from cmd_vel at the same time to get both running at the same time, even if there is drift




#### Prompts

lets say i have the following situation when trying to put rgbd cartographer nav2 ros2 humble SLAM into a 1x1x1m rover: i have teleop in sim and irl by connecting xbox controller -> joy node -> convert joy signals to cmd_vel in an adapter node -> vesc node reads cmd_vel signals and sends commands to VESC by publishing to front_left/commands/motor/speed etc. What is the next step, how can i set up cartographer and nav2 with my d435i mounted to the rover (depth camera is not in urdf)