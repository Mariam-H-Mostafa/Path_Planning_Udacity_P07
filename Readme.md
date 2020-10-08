**Highway Driving Project**

The goal of this project is to build a path planner that creates smooth, safe trajectories for the car to follow. In this planner I consider minimizing jerk, don’t exceed allowed velocity, don’t hit front cars and if the front car is moving slowly I have to change lane.

At first, read the waypoints from the highway map given, then get the localization parameters from the simulator, car_x,car_y, car_s, car_d, car_yaw, car_speed, then get the previous path points, and sensor fusion data that has list of all other cars on the same side of the road.

Then, I checked if the front car is too close, if the difference between target vehicle and self driving vehicle is less that 30, I will set flag that it is too close, then check the free lanes that it is safe to make lane change to and I started to decrease speed gradually.

![enter image description here](https://i.ibb.co/hYNkBs5/Picture1.png)

I converted from vehicle coordinate to map coordinate, then spline function is used to estimate the location of points between the known waypoints, by interpolating the position of those points.

![enter image description here](https://i.ibb.co/kcR2Zj3/Picture2.png)

**Reflection (points need to be improved):**

 - Create a path planner that performs optimized lane changing, this means that the car only changes into a lane that improves its forward progress.
 - Incorporate cost functions in the algorithm.
