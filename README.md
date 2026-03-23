2‑Link Inverse Kinematics Arm Simulator
This project implements a real‑time 2‑link robotic arm simulation using inverse kinematics. The arm consists of two connected segments that automatically adjust their joint angles to reach a target point selected by the user. The simulation demonstrates concepts in kinematics, coordinate transformations, animation, and graphical rendering using Pygame.


Features
- Two‑segment articulated arm with hierarchical joint structure
- Real‑time inverse kinematics solver for target positioning
- Smooth angle interpolation for natural arm movement
- Click‑to‑move interface for selecting target positions
- Cartesian‑to‑screen coordinate conversion
- Accurate geometric modeling of arm segments and rotations
- Modular class structure for easy extension (additional joints, constraints, etc.)


Technologies Used
- Python
- Pygame for rendering and event handling
- Trigonometry and rotation matrices for kinematic calculations
- Object‑oriented design for arm segments and joint relationships


How to Run
- Clone the repository:
git clone https://github.com/yourusername/inverse-kinematics-arm.git
- Navigate into the project directory:
cd inverse-kinematics-arm
- Run the simulation:
python main.py


Controls
- Click anywhere on the screen to set a new target point.
- The arm will compute the required joint angles and animate toward the target.
- Close the window to exit the simulation.


Implementation Overview
The arm is composed of two Arm objects, each defined by a length, angle, and optional connection to a parent segment. The end of the first arm serves as the base for the second. Each frame, the simulation:
- Converts mouse clicks from screen coordinates to Cartesian coordinates.
- Computes the required joint angles using a closed‑form inverse kinematics solution for a 2‑link planar arm.
- Smoothly interpolates each arm’s current angle toward its target angle.
- Recalculates segment endpoints and renders the updated arm geometry.
The inverse kinematics solver uses the law of cosines to compute the elbow angle and trigonometric relationships to determine the shoulder angle. Angle clamping ensures numerical stability.

Future Improvements
- Add joint angle limits
- Add a third arm segment for more complex kinematics
- Implement Jacobian‑based IK for smoother motion
- Add path tracing to visualize the end‑effector trajectory
- Add obstacles and collision avoidance
- Improve rendering with anti‑aliasing or a physics engine
