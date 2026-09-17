---
title: "Working with Latitude and Longitude Data in GIS."
sub-title: "How to Format, Convert, and Use Coordinate Data."
parent: "what-is-geo-id"
parent_url: /resources/what-is-geo-id/
permalink: /resources/lat-long/
jobs_to_be_done:
  - "Distinguish between latitude and longitude coordinates."
  - "Identify whether a dataset is ready for mapping in a GIS application."
next-steps:
  - label: "Let's choose a platform for your map."
    type: question
    ref: choose-a-platform
---
<!--
<nav class="breadcrumbs">
  <a href="{{ '/' | relative_url }}">Home</a>

  {% if page.parent %}
    /
    <a href="{{ page.parent_url | relative_url }}">{{ page.parent }}</a>
  {% endif %}

  /
  <span>{{ page.title }}</span>
</nav>
-->
Does your data look like this? (i.e. latitude and longitude formatted as decimal degrees in two separate columns) 

| long | lat |
| :---- | :---- |
| \-122.254  | 37.871 |
| \-120.426  | 37.364 |
| \-117.863 | 33.645 |

Yes? …feel free to move to the next section

No? …keep reading for how to get your data into a format that can be used for mapping.

## Best Practices for GIS

When working with XY coordinates (longitude or latitude) in a GIS system, coordinates in a spreadsheet of data are expected to:

* be in decimal degree (DD) format  
* contain X and Y locations in two separate columns

It saves a little time if the column headings match what the GIS software will automatically recognize as containing coordinate values. These field names include:

**Latitude:** Y, Latitude, lat  
**Longitude:** X, Longitude, long

For example: 

| X | Y |
| :---- | :---- |
| \-120.419319  | 37.375184 |
| 106.737  | 47.891 |
| \-70.98866 | \-53.14163 |

## Background information on XY coordinates (latitude and longitude)

In a GIS, locations on the Earth’s surface are described by a pair of values, or XY coordinates, representing horizontal and vertical distance from a point of origin. With XY coordinates, the X value indicates how far east or west a feature is of the Prime Meridian (longitude), and the Y value indicates how far north or south of the Equator it is (latitude). We divide the Earth into 360 degrees of longitude (180 east and 180 west of the Prime Meridian), and 180 degrees of latitude (90 north and 90 south of the Equator). Negative values represent locations that are south of the Equator or west of the Prime Meridian. 

<img src="{{ '/assets/images/lat-long.png' | relative_url }}"
     alt="Latitude and Longitude of the Earth "
     style="max-width:450px; width:100%; height:auto;"> 

[Illustration of geographic latitude and longitude of the earth by Djexplo](https://commons.wikimedia.org/wiki/File:Latitude_and_Longitude_of_the_Earth.svg)

XY coordinates can come in a number of formats. These are visualized as points.  
	
| Type of XY coordinates | Example format |
| :---- | :---- |
| Decimal degrees | 37.375184, \-120.419319 |
| Degrees \- Minutes \- Seconds | 37° 22' 30.6624", \- 120° 25' 9.5484" |
| Degrees \- Minutes | 37° 22.51104', \- 120° 25.15914' |
| Universal Transverse Mercator (UTM) | Easting: 487,000 m, Northing: 3,618,000 m |

### Understanding Degrees \- Minutes \- Seconds

The symbols used  
 **°** : degree  
 **'** : minute  
 **"** : second

1 minute is equal to 60 seconds.  
*1 degree is equal to 1 hour*, that is equal to 60 minutes or 3600 seconds.

Note: West longitude and south latitude should either be 

* negative values or   
* explicitly marked with W or S.

## Converting to Decimal Degree Format

### Why would we need to convert our coordinate format?

Most GIS software, spatial databases, and programming languages expect coordinates in decimal degree format, making conversion critical for data portability across platforms. Decimal degrees also enable accurate distance calculations and geospatial analyses, since mathematical operations require a continuous numeric format rather than the segmented DMS structure. Additionally, special characters used in DMS notation, such as the degree symbol (°) are not code-compatible and can cause errors or parsing failures in scripting environments like Python or R.

There are several ways to convert coordinate data to decimal degrees. The recommended approach is to convert it in your spreadsheet prior to using a program to map the data.  

### Converting one (or a few)

Use this [online converter](https://www.latlong.net/degrees-minutes-seconds-to-decimal-degrees) to convert coordinate values manually one by one from degrees minutes seconds to decimal degrees: 

### Convert your data from DMS to DD in your spreadsheet 

You can use a spreadsheet to convert DMS to DD in a spreadsheet program (like Excel or Google Sheets) before importing to a GIS program.

<details  markdown="1" class="collapsible">
<summary markdown="span"><strong>Expand for step-by-step instructions…</strong></summary>

1. **Open your CSV** in a spreadsheet program.  
2. **Use a formula** to convert the DMS values to DD. The general formula is:  
    Decimal Degrees \= Degrees \+ (Minutes / 60\) \+ (Seconds / 3600\).

1\.      Be mindful to retain or include negative signs in front of values for South latitudes and West longitudes.

3. **Create new columns** for the converted Decimal Latitude and Decimal Longitude values.  
4. **Save the modified file** as a new CSV file.  
5. **Import the new DD CSV** into the GIS platform you’ve chosen.
</details>

### Convert your data 

Different GIS software programs have different methods for importing and converting coordinate data to decimal degrees.Expand the different options below for step-by-step instructions for each program.

<details class="collapsible" markdown="1">
<summary markdown="span"><strong>ArcGIS Pro: Convert Degrees Minutes Seconds (DMS)</strong></summary>

If you haven’t followed the recommended procedure of converting DMS to DD in your spreadsheet, the **Convert Coordinate Notation** tool can accomplish the task. 

* Ensure your CSV has columns for Latitude and Longitude in a recognized format (e.g., 34 50 12N or 34°50’12”N).  
* Add CSV to [ArcGIS Pro via Map tab \> Add Data](https://support.esri.com/en-us/knowledge-base/how-to-import-xy-data-tables-to-arcmap-and-convert-the--000012745). The CSV will be added as a Standalone Table.  
* On the Analysis tab, in the Geoprocessing section, click **Tools**.  
* In the search box in the Geoprocessing pane, search for [**Convert Coordinate Notation**](https://www.youtube.com/watch?v=Fh1KybEFOdU).  
  * Select your Standalone Table as the **Input Table**.  
  * Enter the appropriate field names from your table for X (Longitude) and Y (Latitude).  
  * Set the Output Coordinate System to **GCS\_WGS\_1984**.  
  * For Input Coordinate Format, select **DMS 2** (or another format, if appropriate)  
  * For Output Coordinate Format, select **DD 2**.  
  * Click Run. If all goes well, points will be created in the proper locations on your map, and the coordinates will be expressed in decimal degrees in new columns in the attribute table.
</details>

#### Keep in Mind

* **Coordinate System:** Ensure you define the input coordinate system as Geographic (e.g., GCS\_WGS\_1984 or NAD83) for the conversion to work accurately.  
* **Export Data:** After displaying the points, right-click the layer and choose **Export Data** to save the points as a permanent feature class.

<details class="collapsible" markdown="1">
<summary markdown="span"><strong>QGIS: Convert Degrees Minutes Seconds (DMS)</strong></summary>

**–** *(courtesy of Gemini)*

You can convert DMS coordinate data from a CSV file to QGIS by importing directly using QGIS's "Add Delimited Text Layer" tool.

##### Direct Import into QGIS using the Add Delimited Text Layer tool 

This method uses the built-in functionality in QGIS to interpret DMS coordinates. 

1. **Prepare your CSV:** Ensure your DMS coordinates are in separate columns for Latitude and Longitude, and that the format is consistent (e.g., using spaces, dashes, or degree/minute/second symbols as separators).  
2. **Open QGIS** and navigate to the menu: Layer \> Add Layer \> Add Delimited Text Layer.... You can also use the corresponding icon in the toolbar (often a comma icon).  
3. **Browse to your CSV** file and select it. QGIS will attempt to populate the sample data view.  
4. **Configure import settings:**

1\.           Confirm "CSV (Comma Separated Values)" is chosen as the file format.

2\.           Check "First record has field names" if your first row contains headers.

3\.            In the **Geometry Definition** section, ensure "Point coordinates" is selected.

4\.            Specify the column for the X field (Longitude) and the Y field (Latitude).

5\.           **Crucially, check the "DMS Coordinates" checkbox** (this option may vary by QGIS version).

6\.          Set the **Geometry CRS** (Coordinate Reference System) to EPSG:4326 \- WGS 84, which is the standard geographic system for global latitude/longitude data.

5. **Add the layer** by clicking the "Add" button. The points should now be visible on your map canvas.  
6. **Export the layer** to a permanent format (like a Shapefile or GeoPackage) by right-clicking the layer and selecting Export \> Save Features As.... This makes the layer editable and permanent. 

**Alternative: Use a QGIS Plugin: ** For recurring conversions or more advanced options, the [Coordinates Converter](https://plugins.qgis.org/plugins/coordinates_converter/) plugin from the QGIS Python Plugins Repository can also be used.
</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Convert Degrees Minutes Seconds (DMS) in Python</strong></summary> 

To convert a DMS (Degrees, Minutes, Seconds) coordinate CSV file to a format with decimal degrees (DD) in Python, the recommended methods involve using the pandas library for data manipulation and the csv module for file handling, along with custom functions to perform the mathematical conversion. 

**Python: Methods to Convert a CSV with data in DMS to XY (lat/long)**

**Using pandas for Data Manipulation:** This approach is efficient for large datasets and complex column structures. It involves extracting the D, M, S components using regular expressions and then applying the conversion logic.

1. **Install pandas**: pip install pandas  
2. **Conversion Logic**: Define a function to convert DMS to DD, handling hemisphere signs (N/S, E/W).  
3. **Read and Convert**:  
   1.  Load your CSV into a pandas DataFrame using pd.read\_csv().  
   2. Use string extraction and mapping with the pandas.DataFrame.apply() method to convert the columns in-place.  
   3. Save the resulting DataFrame to a new CSV file using df.to\_csv(filename, index=False). 

```py
import pandas as pd
import re

def dms2dd(dms_str):
	"""Convert DMS string to decimal degrees."""
	if pd.isna(dms_str):
    	return None

	# Normalize string
	dms_str = dms_str.strip().upper()

	# Flexible regex
	match = re.search(r'(\d+)[°\s]+(\d+)[\'\s]+(\d+(?:\.\d+)?)[\"\s]*([NSEW])', dms_str)
	if not match:
    	return None

	d, m, s, h = map(float, match.group(1, 2, 3)) + (match.group(4),)

	dd = d + m / 60 + s / 3600
	if h in ['S', 'W']:
    	dd *= -1

	return dd


# Load data
df = pd.read_csv('input.csv')

# Convert columns
df['Lat_DD'] = df['Lat_DMS'].apply(dms2dd)
df['Lon_DD'] = df['Lon_DMS'].apply(dms2dd)

# Save output
df.to_csv('output_dd.csv', index=False)
```

The regex approach (\\d+)°(\\d+)\\'(\\d+(?:\\.\\d+)?)\\"(\[NSEW\]) parses specific formats efficiently. 

**Using the Built-in csv Module:**  For simpler scenarios or to avoid dependencies, use Python's built-in csv module. 

```py
import csv
import re

def dms_to_dd(d, m, s, direction):
	dd = float(d) + float(m)/60 + float(s)/3600
	return -dd if direction in ['S', 'W'] else dd

def parse_dms(dms_str):
	match = re.search(r'(\d+)°(\d+)\'(\d+)"([NSEW])', dms_str)
	if not match:
    	return None
	return match.groups()

with open('input.csv', newline='') as infile, open('output.csv', 'w', newline='') as outfile:
	reader = csv.DictReader(infile)
	fieldnames = reader.fieldnames + ['Lat_DD', 'Lon_DD']
	writer = csv.DictWriter(outfile, fieldnames=fieldnames)
	
	writer.writeheader()
	
	for row in reader:
    	lat_parts = parse_dms(row['Lat_DMS'])
    	lon_parts = parse_dms(row['Lon_DMS'])
    	
    	if lat_parts:
        	row['Lat_DD'] = dms_to_dd(*lat_parts)
    	if lon_parts:
        	row['Lon_DD'] = dms_to_dd(*lon_parts)
    	
    	writer.writerow(row)
```
</details>

## Troubleshooting

Is your data not lining up where you want it to be? 

* Are your XY values switched? For example Google Maps and many other mapping platforms list the Y value first.  
* Double-check the projection of your XY coordinates.  
* The precision of your coordinates (i.e. how many decimal places there are) impacts where your data will show up. 

## General Resources

* [Lat-Long Graphic](https://en.wikipedia.org/wiki/Geographic_coordinate_system#/media/File:FedStats_Lat_long.svg)   
* [Formula for converting Degrees Minutes Seconds to Decimal Degrees](https://www.latlong.net/degrees-minutes-seconds-to-decimal-degrees)  
* [UTM to Latitude and Longitude Convertor](https://www.ngs.noaa.gov/NCAT/)  
* [Map Projections](https://gistbok-ltb.ucgis.org/page/current/concept/CV-03-006)
