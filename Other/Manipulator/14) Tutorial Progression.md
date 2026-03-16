
We want to include some kind of programming tutorial for the dev, in the form of docs via a static site generator accessible on github and also a little paper book, that would be cute.

SIM
- setting up SDK
- starting + navigating tel server
- reading state/pose using SIM
- commanding robot to a pose using UI for SIM
- reading state and commanding robot to a pose using SDK for sim
	- steps for installing deps (docker, anything you need e.g. py)
	- steps for packaging e.g. making ros zip
	- steps for testing
- adding a frontend component + using it

Prerequisites:
- Reading manipulator state (powering on (not sure if needed, while caps are precharging before calibration started), calibrating, error, user controller, finished)

Basic
- commanding real robot to a pose using UI
- commanding real robot to a pose using SDK

Advanced
- trajectories

```
int GetJointCount
int GetJointPosition int joint
float GetJointVelocity int joint
float GetJointTorque int joint

// also voltage, current, temp for driver

int GetAllJointPositions float[] positions
int GetAllJointVelocities float[] velocities

int GetCartesianPose float[] pose   # x y z rx ry rz
int GetCartesianVelocity float[] vel

---

int MoveJoint int joint float position
int MoveJoints float[] positions
int MoveJointsRelative float[] delta

int MoveJoints float[] positions float speed
int MoveJointsBlocking float[] positions float speed

---

int MoveLinear float x float y float z float rx float ry float rz
int MoveLinearRelative float dx float dy float dz float drx float dry float drz (moves in a straight line if possible)

---

int StopMotion
int PauseMotion
int ResumeMotion
int IsMoving

---

int SetMaxJointSpeed float speed
int SetMaxJointAcceleration float accel

int SetCartesianSpeed float speed
int SetCartesianAcceleration float accel

---

int Home
int IsHomed
int Calibrate

---

int ForwardKinematics float[] joints float[] pose
int InverseKinematics float[] pose float[] joints

---

int StartTrajectory
int AddTrajectoryPoint float[] joints float time
int ExecuteTrajectory
int ClearTrajectory

---

```