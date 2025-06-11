## Unit Description

The units for the xyz coordinates in the end_effector are: meters (m).

The units for the rpy (roll, pitch, yaw) angles in the end_effector are: radians (rad).

The units for the link angles in joint_position are: radians (rad).

The units for depth_images are: millimeters (mm).

#### Note

> When using depth images, pay attention to the units. If the maximum value in the depth image is greater than 100, the units are millimeters (mm); otherwise, the units are meters (m).

It is recommended to include the following check when using depth images:

```
if np.max(depth_image) > 100:
    depth_image = depth_image / 1000  # Convert from millimeters to meters
```

## AgileX 3RGB

#### Note
> The h5 format is identical to that of the AgileX 3RGB described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

end_effector (7d): [x, y, z, r, p, y, gripper]

joint_position (7d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./benchmark1_1_release/h5_agilex_3rgb/20_takecorn_2/success_episodes/train/2024_10_08-16_13_09-172910045527931776.00/data/trajectory.hdf5
    
    File structure:

    master (Group)
        end_effector_left (Dataset)
            Shape: (539, 7), Type: float64
        end_effector_right (Dataset)
            Shape: (539, 7), Type: float64
        joint_effort_left (Dataset)
            Shape: (539, 7), Type: float64
        joint_effort_right (Dataset)
            Shape: (539, 7), Type: float64
        joint_position_left (Dataset)
            Shape: (539, 7), Type: float64
        joint_position_right (Dataset)
            Shape: (539, 7), Type: float64
        joint_velocity_left (Dataset)
            Shape: (539, 7), Type: float64
        joint_velocity_right (Dataset)
            Shape: (539, 7), Type: float64
    observations (Group)
        depth_images (Group)
            camera_front (Dataset)
                Shape: (539,), Type: object
            camera_left_wrist (Dataset)
                Shape: (539,), Type: object
            camera_right_wrist (Dataset)
                Shape: (539,), Type: object
        rgb_images (Group)
            camera_front (Dataset)
                Shape: (539,), Type: object
            camera_left_wrist (Dataset)
                Shape: (539,), Type: object
            camera_right_wrist (Dataset)
                Shape: (539,), Type: object
    puppet (Group)
        end_effector_left (Dataset)
            Shape: (539, 7), Type: float64
        end_effector_right (Dataset)
            Shape: (539, 7), Type: float64
        joint_effort_left (Dataset)
            Shape: (539, 7), Type: float64
        joint_effort_right (Dataset)
            Shape: (539, 7), Type: float64
        joint_position_left (Dataset)
            Shape: (539, 7), Type: float64
        joint_position_right (Dataset)
            Shape: (539, 7), Type: float64
        joint_velocity_left (Dataset)
            Shape: (539, 7), Type: float64
        joint_velocity_right (Dataset)
            Shape: (539, 7), Type: float64

## Franka 3RGB

#### Note
> The h5 format is identical to that of the Franka 3RGB described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

end_effector (6d): [x, y, z, r, p, y]

joint_position (8d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./benchmark1_1_release/h5_franka_3rgb/apples_placed_on_a_ceramic_plate/success_episodes/train/1112_141543/data/trajectory.hdf5

    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (98, 8), Type: float64
    observations (Group)
        depth_images (Group)
            camera_left (Dataset)
                Shape: (98,), Type: object
            camera_right (Dataset)
                Shape: (98,), Type: object
            camera_top (Dataset)
                Shape: (98,), Type: object
        rgb_images (Group)
            camera_left (Dataset)
                Shape: (98,), Type: object
            camera_right (Dataset)
                Shape: (98,), Type: object
            camera_top (Dataset)
                Shape: (98,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (98, 6), Type: float64
        joint_position (Dataset)
            Shape: (98, 8), Type: float64

## Franka Fr3 Dual Arm

end_effector (12d): [end_effector_left, end_effector_right]

end_effector_left/right (6d): [x, y, z, r, p, y]

joint_position (8d): [joint_position_left, joint_position_right]

joint_position_left/right (16d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./benchmark1_1_release/h5_franka_fr3_dual/both_pour_water/success_episodes/train/1213_141924/data/trajectory.hdf5
    
    File structure:
    
    master (Group)
        joint_position (Dataset)
            Shape: (407, 16), Type: float64
    observations (Group)
        depth_images (Group)
            camera_front (Dataset)
                Shape: (407,), Type: object
            camera_left (Dataset)
                Shape: (407,), Type: object
            camera_right (Dataset)
                Shape: (407,), Type: object
            camera_top (Dataset)
                Shape: (407,), Type: object
        rgb_images (Group)
            camera_front (Dataset)
                Shape: (407,), Type: object
            camera_left (Dataset)
                Shape: (407,), Type: object
            camera_right (Dataset)
                Shape: (407,), Type: object
            camera_top (Dataset)
                Shape: (407,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (407, 12), Type: float64
        joint_position (Dataset)
            Shape: (407, 16), Type: float64

## Simulation Franka

#### Note
> The h5 format is identical to that of the Simulation Franka described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

end_effector (7d): [x, y, z, quaternions (x,y,z,w)]

joint_position (8d): [base link, ..., end_effector link, gripper]

Note: In Isaac Sim simulation, we sample the robot state values at four times the camera frame rate. As a result, the timestep for the RGB images is about one-fourth that of the end-effector and joint position values.

    Found HDF5 file: ./benchmark1_1_release/h5_sim_franka_3rgb/open_and_close_07/success_episodes/train/307342-2024_10_24_15_25_24/data/trajectory.hdf5
    
    File structure:

    franka (Group)
        end_effector (Dataset)
            Shape: (720, 7), Type: float64
        joint_effort (Dataset)
            Shape: (720, 8), Type: float64
        joint_position (Dataset)
            Shape: (720, 8), Type: float64
        joint_velocity (Dataset)
            Shape: (720, 8), Type: float64
    observations (Group)
        depth_images (Group)
            camera_front_external (Dataset)
                Shape: (176,), Type: object
            camera_handeye (Dataset)
                Shape: (176,), Type: object
            camera_left_external (Dataset)
                Shape: (176,), Type: object
            camera_right_external (Dataset)
                Shape: (176,), Type: object
        rgb_images (Group)
            camera_front_external (Dataset)
                Shape: (170,), Type: object
            camera_handeye (Dataset)
                Shape: (170,), Type: object
            camera_left_external (Dataset)
                Shape: (170,), Type: object
            camera_right_external (Dataset)
                Shape: (170,), Type: object
    sim_time_seq (Dataset)
        Shape: (680,), Type: float64

## Simulation Tien Kung

arm_joint_pos_seq (7d): [base link, ..., end_effector link]

hand_joint_pos_seq (12d): [thumb0 for bending, thumb1 for rotation, passive thumb0, passive thumb1, index finger, passive index finger, middle finger, passive middle finger, ring finger, passive ring finger, little finger, passive little finger]

For more detail of the Insipre Dexterous hand, please refer to [the dexterous hands instructions](https://en.inspire-robots.com/wp-content/uploads/2024/02/INSPIRE-ROBOTS-THE-DEXTEROUS-HANDS-INSTRUCTIONS.pdf).

    Found HDF5 file: ./benchmark1_1_release/h5_sim_tienkung_1rgb/pick_and_place_01_tienkung/success_episodes/train/1101314-2024_12_10_10_11_44/data/trajectory.hdf5
    
    File structure:
    
    observations (Group)
        depth_images (Group)
            camera_chest (Dataset)
                Shape: (1363,), Type: object
            camera_head (Dataset)
                Shape: (1363,), Type: object
        rgb_images (Group)
            camera_chest (Dataset)
                Shape: (1140,), Type: object
            camera_head (Dataset)
                Shape: (1140,), Type: object
    sim_time_seq (Dataset)
        Shape: (1140,), Type: float64
    tiangong (Group)
        left_arm_joint_effort_seqs (Dataset)
            Shape: (1438, 7), Type: float64
        left_arm_joint_pos_seq (Dataset)
            Shape: (1436, 7), Type: float64
        left_arm_joint_vel_seq (Dataset)
            Shape: (1437, 7), Type: float64
        left_end_effector_waist (Dataset)
            Shape: (1438, 7), Type: float64
        left_hand_joint_effort_seq (Dataset)
            Shape: (1437, 12), Type: float64
        left_hand_joint_pos_seq (Dataset)
            Shape: (1436, 12), Type: float64
        left_hand_joint_vel_seq (Dataset)
            Shape: (1437, 12), Type: float64
        right_arm_joint_effort_seq (Dataset)
            Shape: (1438, 7), Type: float64
        right_arm_joint_pos_seq (Dataset)
            Shape: (1438, 7), Type: float64
        right_arm_joint_vel_seq (Dataset)
            Shape: (1438, 7), Type: float64
        right_end_effector_waist (Dataset)
            Shape: (1438, 7), Type: float64
        right_hand_joint_pos_seq (Dataset)
            Shape: (1438, 12), Type: float64
        right_hand_joint_vel_seq (Dataset)
            Shape: (1438, 12), Type: float64

## Tien Kung Gello 1RGB

#### Note
> The h5 format is identical to that of the Tien Kung Gello 1RGB described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

joint_position (16d): [left arm (7d), left hand closure (1d), right arm (7d), right hand closure (1d)]

arm (7d): [base link, ..., end_effector link]

    Found HDF5 file: ./benchmark1_1_release/h5_tienkung_gello_1rgb/close_cabinet_drawer/success_episodes/train/1213_171743/data/trajectory.hdf5

    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (566, 16), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (566,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (566,), Type: object
    puppet (Group)
        joint_position (Dataset)
            Shape: (566, 16), Type: float64

## Tien Kung Prod1 Gello 1RGB

#### Note
> The h5 format is identical to that of the Tien Kung Gello 1RGB described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

    Found HDF5 file: ./benchmark1_1_release/h5_tienkung_prod1_gello_1rgb/clean_table/success_episodes/train/1216_144211/data/trajectory.hdf5
    
    File structure:
    
    master (Group)
        joint_position (Dataset)
            Shape: (660, 16), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (660,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (660,), Type: object
    puppet (Group)
        joint_position (Dataset)
            Shape: (660, 16), Type: float64

## Tien Kung Xsens 1RGB

#### Note
> The h5 format is identical to that of the Tien Kung Xsens 1RGB described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

end_effector (12d): [left hand (6d), right hand (6d)]

hand (6d): [little finger, ring finger, middle finger, index finger, thumb0 for bending, thumb1 for rotation]

joint_position (14d): [left arm (7d), right arm (7d)]

arm (7d): [base link, ..., end_effector link]

    Found HDF5 file: ./benchmark1_1_release/h5_tienkung_xsens_1rgb/pick_cup_pour_cup_place/success_episodes/train/2024-11-13-16-52-40/data/trajectory.hdf5
    
    File structure:
    
    master (Group)
        end_effector (Dataset)
            Shape: (662, 12), Type: float64
        joint_position (Dataset)
            Shape: (662, 14), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (662,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (662,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (662, 12), Type: float64
        joint_position (Dataset)
            Shape: (662, 14), Type: float64


## UR 1RGB

#### Note
> The h5 format is identical to that of the UR 1RGB described in [all_robot_h5_info.md](./static/all_robot_h5_info.md).

end_effector (6d): [x, y, z, r, p, y]

joint_position (7d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./benchmark1_1_release/h5_ur_1rgb/put_the_garbage_in_the_trash_can_1112/success_episodes/train/1112_171103/data/trajectory.hdf5

    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (203, 7), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (203,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (203,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (203, 6), Type: float64
        joint_position (Dataset)
            Shape: (203, 7), Type: float64

