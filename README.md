# MTI-Toolbox-v4

  This repo contains a downloadable toolbox for ArcGIS Pro for the handling of STANAG4607, GMTI data. This tool was developed against STANAG4607 ED3 and ArcGIS Pro 2.4. Compatibility with previous versions is not guaranteed. 
  
**This tool is in development**
 
  This tool is still in active development. There are documented issues with processing live mission files. If you encounter any other errors please report them here or to the POC so that we can work to fix them. 
  
  Currently this tool processes data for a select number of segments within the .4607 file inorder to streamline the code. If there is additional information needed from within the file please contact the POC for the script capable of parsing all data transmitted.
 
# How To

  To use this tool first download the entire 'MTI Toolbox v4' folder and place it in an accessible place on your machine. The entire folder and its structure should remain unchanged as there are resource files within the folder to allow the translation script to run.
  
  In ArcGIS Pro select add a toolbox to your project and add the .tbx found inside the 'MTI Toolbox v4' folder. When you open the tool you should see an interface like the one below:
  
<p align="center">
  <img src=https://github.com/phornstein/MTI-Toolbox-v4/blob/master/mti_tool.PNG />
</p>

  Populate the .4607 File(s) field with one or more .4607 files. You can select multiple from the file explorer at a single time.
  
  The remaining fields are optional, leaving them blank with not return any data for them:
  
1. Area of Interest: import an existing feature layer or draw one on the fly to filter the output of the mover feature class only to a specific AOI
1. Movers FeatureClass: the output filename for the movers or detections in your .4607 files
1. Sensor Location: the output filename for the data transmitted about the sensor's location. This includes both Sensor Location segments and sensor data trasmitted over the Dwell Segment
1. Scan Areas FeatureClass: the output filename for the scans from the sensor. This returns a polygon featureclass showing what the sensor was looking at. Generating polygons is computationally expensive and is not recommended for very large datasets
1. Spatial Reference: if a specific projection is required for your data entering it here will reproject all results

<p align="center">
  <img src=https://github.com/phornstein/MTI-Toolbox-v4/blob/master/mti_tool_report.PNG />
</p>

  After running this tool a report will be generated under 'View Details' on the bottom of the tool. This report details the Highest Classification of the data contained in all files processed along with an Caveats. Additionally, the number of files processed, all digital elevation models used, and all sensors contirbuting to the processed files will be reported.
