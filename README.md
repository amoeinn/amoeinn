Independent research in space robotics: spacecraft GNC, autonomous surface robotics, and in-space manipulation.

## Highlighted Work

**Spacecraft Autonomy**

- [spacecraft-attitude-ekf-fdir](https://github.com/amoeinn/spacecraft-attitude-ekf-fdir): attitude estimation with an error-state EKF fusing gyro and star tracker, tracking to 0.05 to 0.2 degrees, with fault detection that watches the estimated gyro bias rather than the measurement residual, because a gyro fault corrupts the prediction model and leaves the residual intact, and Monte Carlo validation across seeds
- [spacecraft-relative-navigation-ekf-ros2](https://github.com/amoeinn/spacecraft-relative-navigation-ekf-ros2): ROS 2 relative navigation with truth dynamics, a noisy sensor model and an EKF as separate nodes, and an analysis node pairing samples by nearest timestamp rather than by arrival, so the pipeline's own latency stays out of the error, measuring position RMSE from 0.086 m raw down to 0.052 m

**Manipulation**

- [free-floating-manipulation](https://github.com/amoeinn/free-floating-manipulation): manipulation planning for an arm on an uncontrolled free-floating base, where a closed joint-space loop leaves the spacecraft 18.98 degrees rotated because momentum is conserved and MoveIt certifies plans collision free that collide once the base reacts, with a 3D Gaussian splatting implementation written from scratch that reconstructs the target from approach imagery and no CAD model, pose tracking on two losses where each one's blind spot is the other's strength, and a ROS 2 behavior tree that returns SUCCESS end to end on a mission an independent audit reports 180 degrees wrong
- [panda-manipulation-planning](https://github.com/amoeinn/panda-manipulation-planning): RRT-Connect and a learned signed distance field for a 7-DOF arm in PyBullet, with gradient-based trajectory optimization benchmarked against the classical baseline, and a pick and place sequence that treats a grasped object as part of the moving robot

**Motion Planning and Algorithms**

- [motion-planning-playground](https://github.com/amoeinn/motion-planning-playground): A*, Dijkstra, RRT and RRT* on a shared grid world, with a four-way comparison, animated search replay, and tests covering optimality and path validity

## Interests

Space robotics, guidance/navigation/control, autonomous surface robotics for lunar and Mars applications, in-space assembly and servicing, spacecraft rendezvous and proximity operations, planetary rotorcraft.