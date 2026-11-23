Independent research in space robotics: spacecraft GNC, autonomous surface robotics, and in-space manipulation.

## Highlighted Work

**Spacecraft Autonomy**

- [spacecraft-attitude-ekf-fdir](https://github.com/amoeinn/spacecraft-attitude-ekf-fdir): attitude estimation with an error-state EKF fusing gyro and star tracker, tracking to 0.05 to 0.2 degrees, with fault detection that watches the estimated gyro bias rather than the measurement residual, because a gyro fault corrupts the prediction model and leaves the residual intact, and Monte Carlo validation across seeds
- [spacecraft-relative-navigation-ekf-ros2](https://github.com/amoeinn/spacecraft-relative-navigation-ekf-ros2): ROS 2 relative navigation with truth dynamics, a noisy sensor model and an EKF as separate nodes, and an analysis node pairing samples by nearest timestamp rather than by arrival, so the pipeline's own latency stays out of the error, measuring position RMSE from 0.086 m raw down to 0.052 m

**Manipulation**

- [dual-arm-closed-chain](https://github.com/amoeinn/dual-arm-closed-chain): two arms on a free-flying servicer berthing a station module, where closing the second gripper turns a tree into a closed kinematic loop and the one-armed formulation stops describing the system at the instant the task succeeds, giving either hand all six task directions with the base held exactly still against one of six for a single arm, while the inherited generalized Jacobian returns a plausible answer 22 percent wrong rather than raising, and the base response to the same joint motion changes by a factor of 9.4 once contact makes the servicer push off the station instead of conserving momentum
- [free-floating-manipulation](https://github.com/amoeinn/free-floating-manipulation): manipulation planning for an arm on an uncontrolled free-floating base, where a closed joint-space loop leaves the spacecraft 18.98 degrees rotated because momentum is conserved and MoveIt certifies plans collision free that collide once the base reacts, with a 3D Gaussian splatting implementation written from scratch that reconstructs the target from approach imagery and no CAD model, pose tracking on two losses where each one's blind spot is the other's strength, and a ROS 2 behavior tree that returns SUCCESS end to end on a mission an independent audit reports 180 degrees wrong
- [panda-manipulation-planning](https://github.com/amoeinn/panda-manipulation-planning): RRT-Connect and a learned signed distance field for a 7-DOF arm in PyBullet, with gradient-based trajectory optimization benchmarked against the classical baseline, and a pick and place sequence that treats a grasped object as part of the moving robot

**Lunar Robotics**

- [lunar-polar-traverse](https://github.com/amoeinn/lunar-polar-traverse): time-dependent path planning for a rover at the lunar south pole on the LOLA 20 m DEM and a SPICE sun ephemeris, where shadow edges sweep at a median 172.69 m/hr, the same order as a slow rover, so a path is a schedule, with an exact label-setting search over cell, arrival time and continuous shadow time and an independent C++ replay checker sharing no code with the planner, and a result that splits: the illumination model agrees with the published permanent shadow map and observed LRO frames, the claim that plans ignoring time fail replay is not passed, and the predicted payoff is absent, the time-dependent plan arriving 0.14 percent earlier at the median against a registered 10 percent, while paired per instance the two planners never disagree on the checker's verdict on the 221 instances where both produced a plan, all after a correction that found two defects, the sun passed in kilometres and a replay checker stepping on map-plane distance rather than along the slope, and re-ran everything with every verdict kept before and after
- [lunar-landing-gnc](https://github.com/amoeinn/lunar-landing-gnc): guidance, navigation and control for a lunar lander at the south pole, with terrain relative navigation, convex powered descent guidance, LiDAR hazard detection, abort logic and flight code in C++, testing whether a navigation map expires as low-sun shadows move, where on a seed flown after its bar was registered a fresh map lands 400 of 400 flights knowing its touchdown position to 0.12 m, while a week-old map loses 72 to 92 percent of landings and does worse than no map, and an independent replay checker failed its own bar with every violation traced, including a fault in the simulation's ground whose fix leaves the result unchanged

**Motion Planning and Algorithms**

- [motion-planning-playground](https://github.com/amoeinn/motion-planning-playground): A*, Dijkstra, RRT and RRT* on a shared grid world, with a four-way comparison, animated search replay, and tests covering optimality and path validity

## Interests

Space robotics, guidance/navigation/control, autonomous surface robotics for lunar and Mars applications, in-space assembly and servicing, spacecraft rendezvous and proximity operations, planetary rotorcraft.