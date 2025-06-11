## Unit Description

The units for the xyz coordinates in the end_effector are: meters (m).

The units for the rpy (roll, pitch, yaw) angles in the end_effector are: radians (rad).

The units for the link angles in joint_position are: radians (rad).

The units for depth_images are: millimeters (mm).

Note:

When using depth images, pay attention to the units. If the maximum value in the depth image is greater than 100, the units are millimeters (mm); otherwise, the units are meters (m).

It is recommended to include the following check when using depth images:

```
if np.max(depth_image) > 100:
    depth_image = depth_image / 1000  # Convert from millimeters to meters
```

## AgileX 3RGB

end_effector (7d): [x, y, z, r, p, y, gripper]

joint_position (7d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./h5_agilex_3rgb/10_packplate/success_episodes/train/2024_09_18-10_40_22-172952636630221088.00/data/trajectory.hdf5
    
    File structure:

    master (Group)
        end_effector_left (Dataset)
            Shape: (762, 7), Type: float64
        end_effector_right (Dataset)
            Shape: (762, 7), Type: float64
        joint_effort_left (Dataset)
            Shape: (762, 7), Type: float64
        joint_effort_right (Dataset)
            Shape: (762, 7), Type: float64
        joint_position_left (Dataset)
            Shape: (762, 7), Type: float64
        joint_position_right (Dataset)
            Shape: (762, 7), Type: float64
        joint_velocity_left (Dataset)
            Shape: (762, 7), Type: float64
        joint_velocity_right (Dataset)
            Shape: (762, 7), Type: float64
    observations (Group)
        depth_images (Group)
            camera_front (Dataset)
                Shape: (762,), Type: object
            camera_left_wrist (Dataset)
                Shape: (762,), Type: object
            camera_right_wrist (Dataset)
                Shape: (762,), Type: object
        rgb_images (Group)
            camera_front (Dataset)
                Shape: (762,), Type: object
            camera_left_wrist (Dataset)
                Shape: (762,), Type: object
            camera_right_wrist (Dataset)
                Shape: (762,), Type: object
    puppet (Group)
        end_effector_left (Dataset)
            Shape: (762, 7), Type: float64
        end_effector_right (Dataset)
            Shape: (762, 7), Type: float64
        joint_effort_left (Dataset)
            Shape: (762, 7), Type: float64
        joint_effort_right (Dataset)
            Shape: (762, 7), Type: float64
        joint_position_left (Dataset)
            Shape: (762, 7), Type: float64
        joint_position_right (Dataset)
            Shape: (762, 7), Type: float64
        joint_velocity_left (Dataset)
            Shape: (762, 7), Type: float64
        joint_velocity_right (Dataset)
            Shape: (762, 7), Type: float64



## Franka 1RGB

end_effector (6d): [x, y, z, r, p, y]

joint_position (8d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./h5_franka_1rgb/bread_in_basket/success_episodes/train/1014_144602/data/trajectory.hdf5
    
    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (96, 8), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (96,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (96,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (96, 6), Type: float64
        joint_position (Dataset)
            Shape: (96, 8), Type: float64

## Franka 3RGB

### 3RGB

end_effector (6d): [x, y, z, r, p, y]

joint_position (8d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./h5_franka_3rgb/241021_close_trash_bin_1/success_episodes/train/1021_151112/data/trajectory.hdf5

    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (122, 8), Type: float64
    observations (Group)
        depth_images (Group)
            camera_left (Dataset)
                Shape: (122,), Type: object
            camera_right (Dataset)
                Shape: (122,), Type: object
            camera_top (Dataset)
                Shape: (122,), Type: object
        rgb_images (Group)
            camera_left (Dataset)
                Shape: (122,), Type: object
            camera_right (Dataset)
                Shape: (122,), Type: object
            camera_top (Dataset)
                Shape: (122,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (122, 6), Type: float64
        joint_position (Dataset)
            Shape: (122, 8), Type: float64

### 2RGB

end_effector (6d): [x, y, z, r, p, y]

joint_position (8d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./h5_franka_3rgb/2024_09_20_close_cabinet/success_episodes/train/0920_142729/data/trajectory.hdf5
    
    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (200, 8), Type: float64
    observations (Group)
        depth_images (Group)
        rgb_images (Group)
            camera_left (Dataset)
                Shape: (200,), Type: object
            camera_right (Dataset)
                Shape: (200,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (200, 6), Type: float64
        joint_position (Dataset)
            Shape: (200, 8), Type: float64

## Simulation Franka

end_effector (7d): [x, y, z, quaternions (x,y,z,w)]

joint_position (8d): [base link, ..., end_effector link, gripper]

Note: In Isaac Sim simulation, we sample the robot state values at four times the camera frame rate. As a result, the timestep for the RGB images is about one-fourth that of the end-effector and joint position values.

    Found HDF5 file: ./h5_simulation/open_and_close_01/success_episodes/train/2024_10_10-10_19_11/data/trajectory.hdf5
    
    File structure:

    franka (Group)
        end_effector (Dataset)
            Shape: (448, 7), Type: float64
        joint_effort (Dataset)
            Shape: (448, 8), Type: float64
        joint_position (Dataset)
            Shape: (448, 8), Type: float64
        joint_velocity (Dataset)
            Shape: (448, 8), Type: float64
    observations (Group)
        depth_images (Group) 
            camera_front_external (Dataset)
                Shape: (110,), Type: object
            camera_handeye (Dataset)
                Shape: (110,), Type: object
            camera_left_external (Dataset)
                Shape: (110,), Type: object
            camera_right_external (Dataset)
                Shape: (110,), Type: object
        rgb_images (Group)
            camera_front_external (Dataset)
                Shape: (108,), Type: object
            camera_handeye (Dataset)
                Shape: (108,), Type: object
            camera_left_external (Dataset)
                Shape: (108,), Type: object
            camera_right_external (Dataset)
                Shape: (108,), Type: object
    sim_time_seq (Dataset)
        Shape: (427,), Type: float64

## Tien Kung Gello 1RGB

joint_position (16d): [left arm (7d), left hand closure (1d), right arm (7d), right hand closure (1d)]

arm (7d): [base link, ..., end_effector link]

    Found HDF5 file: ./h5_tienkung_gello_1rgb/clean_table_2_241211/success_episodes/train/1211_111152/data/trajectory.hdf5
    
    File structure:

    master (Group)
        joint_position (Dataset)
            Shape: (1197, 16), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (1197,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (1197,), Type: object
    puppet (Group)
        joint_position (Dataset)
            Shape: (1197, 16), Type: float64

## Tien Kung Xsens 1RGB

end_effector (12d): [left hand (6d), right hand (6d)]

hand (6d): [little finger, ring finger, middle finger, index finger, thumb0 for bending, thumb1 for rotation]

joint_position (14d): [left arm (7d), right arm (7d)]

arm (7d): [base link, ..., end_effector link]

For more detail of the Insipre Dexterous hand, please refer to [the dexterous hands instructions](https://en.inspire-robots.com/wp-content/uploads/2024/02/INSPIRE-ROBOTS-THE-DEXTEROUS-HANDS-INSTRUCTIONS.pdf).

    Found HDF5 file: ./h5_tienkung_xsens_1rgb/battery_insertion_with_pullout/success_episodes/train/2024-09-19-10-20-11/data/trajectory.hdf5

    File structure:
    
    master (Group)
        end_effector (Dataset)
            Shape: (1160, 12), Type: float64
        joint_position (Dataset)
            Shape: (1160, 14), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (1160,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (1160,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (1160, 12), Type: float64
        joint_position (Dataset)
            Shape: (1160, 14), Type: float64

## UR 1RGB

end_effector (6d): [x, y, z, r, p, y]

joint_position (7d): [base link, ..., end_effector link, gripper]

    Found HDF5 file: ./h5_ur_1rgb/bread_in_basket_1/success_episodes/train/1014_140258/data/trajectory.hdf5
    
    File structure:
    
    master (Group)
        joint_position (Dataset)
            Shape: (388, 7), Type: float64
    observations (Group)
        depth_images (Group)
            camera_top (Dataset)
                Shape: (388,), Type: object
        rgb_images (Group)
            camera_top (Dataset)
                Shape: (388,), Type: object
    puppet (Group)
        end_effector (Dataset)
            Shape: (388, 6), Type: float64
        joint_position (Dataset)
            Shape: (388, 7), Type: float64

