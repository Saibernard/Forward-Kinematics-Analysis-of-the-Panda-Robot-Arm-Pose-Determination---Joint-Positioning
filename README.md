# Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning
This repository delves into the forward kinematics of the Panda robot arm. By inputting joint angles, the function provides the pose of the end effector frame and joint positions, all relative to the world frame. 


# Forward Kinematics Model for Panda Robot Arm

## Introduction

The essence of this project revolves around developing a comprehensive forward kinematics model for the renowned Panda robot arm. The main objective is to map given joint angles to the resulting pose of the end effector in a world-centric frame of reference.

## Technical Breakdown

### Coordinate Frame Designation:
- Every link of the Panda robot was assigned a unique coordinate frame.
- Established a consistent frame convention for the entire class: the end effector frame (originated between the gripper fingers, with the z-axis pointing in the approach direction and the y-axis along the sliding direction) and the world frame (located on the axis of the first joint, at the robot's mounting point).

  ![image](https://github.com/Saibernard/Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning/assets/112599512/30663e43-90e2-416b-8837-ff636e5ddceb)
  
  ![image](https://github.com/Saibernard/Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning/assets/112599512/b54547fc-da7e-4c68-8ecb-85c1f042307d)



### Relative Transformations:
- Derived mathematical models to capture the transformation between each consecutively paired coordinate frame as functions of the robot’s configuration q.
- Utilized established conventions like Denavit-Hartenberg (DH) where necessary, while also noting the distinction between intermediate frame origins under such conventions and the actual joint positions.

 ![image](https://github.com/Saibernard/Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning/assets/112599512/b3ff37de-19a6-4029-b70b-66c07b8219ad)


### Composing Transformations:
- An algorithmic approach was employed to compute how these transformations interplay to provide a coherent transformation matrix between any given robot link and the global world frame.

### End-Effector Pose & Joint Positions:
- Leveraged the composed transformation matrices, alongside critical dimensional data, to compute the full pose of the end effector.
- Canonical positions for joints were deduced, adhering to the mechanical design cues of the robot, specifically emphasizing “cut planes” orthogonal to joint rotation axes which bifurcate two links.



## Considerations

It's pivotal to note that while conventions like the Denavit-Hartenberg (DH) were at times employed, they don’t always equate intermediate frame origins with joint positions. Our meticulous approach ensured that our transformations and computations align with the physical reality of the Panda robot arm.

## FK Results

### Joint angles configuration 1: 

𝑞 = [π/2, 0, π/4, -π/2, -π/2, π/2, 0]


![image](https://github.com/Saibernard/Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning/assets/112599512/d950fb4e-84e6-438a-a6ac-ec99789125bc)

### Joint angles configuration 2: 

𝑞 = [0, 0, 0, -π/2, 0, π/2, 0]

![image](https://github.com/Saibernard/Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning/assets/112599512/0b402235-710d-415d-960a-e700a507dc17)


## Reachable workspace analysis:

The reachanble workspace analysis was done and simulated using matplot lib to check the possible positions, the robot could reach.

![image](https://github.com/Saibernard/Forward-Kinematics-Analysis-of-the-Panda-Robot-Arm-Pose-Determination---Joint-Positioning/assets/112599512/e9b2053a-b892-4f5d-af89-41b217f59985)



## Conclusion

This project offers a holistic and accurate representation of the Panda robot arm's spatial configuration through the forward kinematics paradigm. It ensures seamless and accurate mapping of joint angles to the end effector's pose and joint positions in a real-world scenario.
