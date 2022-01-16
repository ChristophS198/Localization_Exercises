# Exercise: Mapping
Large files are missing, therefore the code can not be run!  
Complete the TODO's in `map-main.cpp`.

## Task description
The simulator is continuously scanning the environment with a virtual lidar which you can choose to customize its settings. Every time the car moves every so many meters and so much time has passed the scan gets added to the overall collected point cloud map. Currently the scans are in the same local reference frame as the car. This means they will also be centered at the origin (0,0) and the car's angle starts at 0 degrees on the x axis. When you drive around in the simulator you will notice scans stack up on top of each other with incorrect rotation. Your task for the mapping section of this exercise is to correct the scans transform by using the input pose information passed into lidar->Listen() function. The pose variable contains the ground truth for the cars location and orientation provided by the simulator. You can use transform3D to convert the input pose to a 4 x 4 matrix. Then multiply the transform matrix with the position vector of the scan point to complete the correction. After making the correction you will then be able to create accurate point cloud maps like the one seen below. As a final step you will be filtering the overall point cloud down by using a Voxel filter like you have done in previous exercises. This ensures the resolution is consistent across the entire map and helps prevent from having to filter it later again when using it for scan matching. You can save the map by pressing the s key on the keyboard, which saves it as my_map.pcd.

## Compiling

**Make sure the GPU is enabled**


```
cd /home/workspace
cmake .
make
```

## Run the code

```
su - student // Ignore Permission Denied, if you see student@ you are good
cd /home/workspace
./run_carla.sh
// Create new tab
cd /home/workspace
./cloud_mapper // Might have core dump on start up, just rerun if so. Crash doesn't happen more than a couple of times
```

Note that any visualizations will appear only the remote desktop; if you work in the workspace IDE you will need to click on the "Desktop" button in the bottom right, and only run the executable from the terminal within the remote desktop to view them.