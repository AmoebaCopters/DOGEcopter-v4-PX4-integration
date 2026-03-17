# DOGEcopter-v4-PX4-integration
DOGEcopter-v4's files for integration with PX4 and Gazebo simulation
# QUICK SETUP
1. Copy "module/" contents into PX4-Autopilot/src/modules/tricopter_indi/
2. Copy airframe files into their respective ROMFS airframes folders (init.d/airframes/ and init.d-posix/airframes/), and add the filenames to both CMakeLists.txt files in those folders.
3. Replace ROMFS/px4fmu_common/init.d/rc.mc_apps with the one from startup/ (this stops PX4's default controllers from fighting ours).
4. Copy gazebo_model/ contents into PX4-Autopilot/Tools/simulation/gz/models/tricopter_indi/
5. Add "CONFIG_MODULES_TRICOPTER_INDI=y" to boards/px4/sitl/default.px4board
6. Build and run: "make px4_sitl gz_tricopter_indi", then type "commander takeoff" in the PX4 shell. The drone will spin in yaw — that's normal.
