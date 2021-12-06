# Use Waypoints on Similar Structure Tool (MYOModel Toolbox v.1.0)
Version 1.0

## Summary
The "Use Waypoints on Similar Structure" tool allows a user to take the camera waypoints for a previously analyzed structure and move/rotate them to a new structure with a similar configuration.
The accuracy of the new waypoints is highly dependent on the measurements of the original and new structures' center coordinates and the similarity of the two structures.
The result of this tool is a feature class with flight-planning-ready waypoints including longitude, latitude, elevation, and camera azimuth (yaw) and pitch.

## Usage
* The tool requires an accurate center coordinate for the original and similar structure. These coordinates should be directly between 2 poles (in the case of a h-frame), the center of a lattice tower, or the center of a single pole
* The elevations of the original and similar structures should be in Height Above Ellipsoid (WGS84 HAE) on the ground at the center coordinates
* These coordinates can be derived within ArcGIS by placing a point in the correct locations (see above), or using an accurate RTK GNSS measurement in the field
* A counter-clockwise rotation angle relative to North (0 degrees) must be determined between the two structures. For example, if the original structure has cross arms running east-west (from 90-270 degrees) and a similar structure has cross arms running north-south (0-180 degrees), the rotation angle would be 90 degrees.
* Determination of the rotation angle can be done within an ArcGIS Scene Map using the "Measure" tool to find the angle difference relative to North.

## Parameters
**Input Waypoints:** *The camera waypoints feature class created with the "Run MYOModel" tool*

**Input Project GeoDatabase (WGS84):** *The WGS84 project geodatabase used previously with the "Run MYOModel" tool*

**Input New Feature Class Name:** *The name to be given to the similar structure's camera waypoints*

**Input Original Structure Center Coordinate (WGS84):** *The longitude and latitude coordinates for the center of the original structure*

**Input Original Structure Ground Elevation (HAE Meters):** *The elevation (on the ground) for the center of the original structure*

**Input New Structure Center Coordinate (WGS84):** *The longitude and latitude coordinates for the center of the similar structure*

**Input New Structure Ground Elevation (HAE Meters):** *The elevation (on the ground) for the center of the similar structure*

**Input Rotation Angle (Degrees):** *The counter-clockwise angle to rotate the points, based on the difference between the two structures' orientations relative to North*

## Derived Output
**Project GeoDatabase (WGS84).gdb/Input New Feature Class Name:** *The waypoints to fly to collect images with the required views of the targets on the similar structure*