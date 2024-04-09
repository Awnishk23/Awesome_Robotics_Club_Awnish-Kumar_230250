Firstly we have created  the FabrikRobotArm class it initialises with a list of link lengths which represents the length of each segment of the robotic arm .
num_joints represent the number of joints in the robotic arm and the max_iterations Specifies the maximum number of iterations allowed for the FABRIK algorithm.
In Forward kinematics it calculate the position of 3D space based on the input of joint angles and the length of the links and used np.cos and np.sin for calculating the coordinates
and then using distance we calculated the distance between two points in 3D space
And then using FABRIK Algorithm move the Robotics Arm effector towards the target position as it adjust the joint angles to minimize the distance between end effector and the target 
The FABRIK Algorithm consists of two main phases 
i) Forward Reaching which take care of position from base to end effector.
ii) Backward Reaching which adjust positions from end effector to base.
It iterates until the end effector reaches the target position or it reached the maximum iteration 
Now, in check_reachability checks if the robotic arm is reachable to target or not by calculating the distance between the end effector position
and the target position it will return True if the distance is less than or equal to the sum of the link lengths and 
indicates that the target position is within reach and if not in reach then print Not reachable 
In the main we allow user to take input of initial joint angles and target position coordinates and then use the check_reachabilty to check whether the target position is reachable or not
and then using FABRIK Algorithm it find the optimal joint angle to reach the target position and finally it print TARGET POSITION REACHABLE or not.
