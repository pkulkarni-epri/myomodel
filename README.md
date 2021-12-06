# MYOModel Toolbox
Version 1.0

## Summary
An ArcGIS Pro toolbox for determining the minimal yet optimal (MYO) drone camera stations of utility infrastructure.

The MYOModel Toolbox contains 2 tools, "Run MYOModel" and "Use Waypoints on Similar Structure"

### Run MYOModel Tool
The "Run MYOModel" is the primary tool in the MYOModel Toolbox. It evaluates a lidar or photogrammetric point cloud
and designated targets on a structure, to determine the ideal number and location of waypoints for a drone to fly and
capture images. The resultant waypoint feature class has all the needed information to plan a successful imaging flight,
including latitude, longitude, altitude, camera/drone yaw (azimuth) and pitch. 

### Use Waypoints on Similar Structure Tool
The "Use waypoints on Similar Structure" tool is optional and intended to be used with the output of the "Run MYOModel" tool
It takes the defined camera waypoints from the structure used in "Run MYOModel" and translates their positions and view angles to a different structure with a similar configuration to the original.
This negates the need to run the full "Run MYOModel" process on any similar structures.

## Documentation
**[Installation](/Documentation/Installation.md):** *How to install the MYOModel Toolbox and setup required components*


**[Data Preparation](/Documentation/Data_Preperation.md):** *How to prepare the data needed to run the MYOModel toolbox*


**[Run MYOModel Tool](/Documentation/Run_MYOModel.md):** *How to run the primary tool in the MYOModel Toolbox*


**[Use Waypoints on Similar Structure](/Documentation/Use_Waypoints_Similar_Structure.md):** *How to translate waypoints to similar structures*


**[Troubleshooting](/Documentation/Troubleshooting.md):** *How to resolve some potential problems when using the MYOModel Toolbox*