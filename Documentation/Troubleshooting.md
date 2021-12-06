# MYOModel Toolbox Troubleshooting
Version 1.0

## Summary
The MYOModel Toolbox has requirements that if not met, may result in errors. Additionally, some aspects of the input data may cause problems with processing times and memory consumption.

## Crashes and errors
**The Run MYOModel Tool crashed, now what?**

Most crashes will be the result incorrect input data or a lack of computer resources.
Generally, make sure that:
1. You have used correct azimuth min/max and pitch min/max values for your targets (see "MYOModel Toolbox Data Preparation")
2. Your targets shapefile is a PointZ format with every target / point containing an elevation (z) geometry (see "MYOModel Toolbox Data Preparation")
3. Your lidar / photogrammetric point cloud and targets shapefile are in the same projected coordinate system and that the system uses meters (see "MYOModel Toolbox Data Preparation")
4. Your lidar / photogrammetric point cloud contain no more points than are necessary for the analysis (see "MYOModel Toolbox Data Preparation")
5. The input parameters are valid (see Run MYOModel Tool (MYOModel Toolbox v.1.0))

**The Run MYOModel Tool is taking more than 3+ hours to run**

As long as the tool has not crashed (which you would be notified about), it is still running. A run time of 3 hours can in fact be normal with many targets (as seen with 75 targets) and with a dense point cloud.
If you want to stop the tool from running and try to prepare the data to run more quickly, try any/all of the following tricks:
- Thin the 'ground' class in the point cloud and reduce the area of the point cloud (see "MYOModel Toolbox Data Preparation")
- Reduce the range of the target angles (azmin, azmax, pmin, pmax)
- Make sure you did not put in a bad parameter in the sensor information (see Run MYOModel Tool (MYOModel Toolbox v.1.0))

**The Run MYOModel Tool results in some targets having no visible camera stations**

There are a few possible reasons for this. Check the following list, which is ordered by most to least likely:
- Your target is too close to some point(s) in the point cloud and is therefore being considered obstructed. Try moving the target point away from the point cloud points some small amount < 0.2 meters is generally good.
- Your ranges of acceptable view angles (azmin, azmax, pmin, pmax) are too narrow or unreasonable. Try expanding the ranges by a couple degrees.
- Your target is legitimately, fully-obstructed from the specified view angles and will not be visible. This should be obvious when looking at the targets and point cloud in an ArcGIS Scene Map. Move the target point, change the view angles and/or gsd. 
