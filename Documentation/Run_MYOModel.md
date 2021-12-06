# Run MYOModel Tool (MYOModel Toolbox v.1.0)
Version 1.0

## Summary
"Run MYOModel" is the primary tool in the MYOModel Toolbox. It evaluates a lidar or photogrammetric point cloud
and designated targets on a structure, to determine the ideal number and location of waypoints for a drone to fly and
capture images. The resultant waypoint feature class has all the needed information to plan a successful imaging flight,
including latitude, longitude, altitude, camera/drone yaw (azimuth) and pitch. 

## Usage
* The input lidar/photogrammetric point cloud must be in LAS format
* The input targets shapefile must be PointZ and all points must have Z (elevation) attributes. Additionally, for each
  target:
    * A minimum (azmin) and maximum (azmax) view azimuth must be specified
    * A minimum (pmin) and maximum (pmax) view pitch must be specified
    * An acceptable ground sample distance (gsd) must be specified
* The input point cloud and targets must be in the same projected coordinate system in meters
    
## Parameters
**Input Targets:** *The input targets shapefile*

**Input Point Cloud:** *The lidar/photogrammetric point cloud with the structure and obstructions*

**Input Coordinate System:** *The Projected Coordinate System of the Input Targets and Input Point Cloud*

**Input Project GeoDatabase:** *The geodatabase that will hold the projected coordinate system outputs*

**Input Project GeoDatabase (WGS84):** *The geodatabase that will hold the WGS84 coordinate system outputs*

**Input Data Folder:** *The folder location of the two geodatabases, target shapefile and lidar point cloud*

**Input Desired Point Cloud Voxel Size (Meters):** *The size of the voxels used to subsample the lidar point cloud and obstructions*

**Input Desired Camera Station Voxel Size (Meters):** *The size of the voxels used to subsample potential camera stations, should be related to the GPS navigational accuracy of the UAS*

**Input Sensor Width (Meters):** *The physical dimension of the sensors' chip in the width direction*

**Input Sensor Height (Meters):** *The physical dimension of the sensors' chip in the height direction*

**Input Focal Length (Meters):** *The focal length of the camera's lens*

**Input Image Width (Pixels):** *The number of pixels in an image in the width direction*

**Input Image Height (Pixels):** *The number of pixels in an image in the height direction*

## Derived Output
**Project GeoDatabase (WGS84).gdb/camera_waypoints:** *The waypoints to fly to collect images with the required views of the targets*

**Project GeoDatabase (WGS84).gdb/cumulative_waypoint_views:** *A Table displaying the predicted primary and secondary views available to each camera waypoint with more than 1 visible target*