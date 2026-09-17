---
title: "What is the geographic identifier?"
sub-title: "Includes general spreadsheet formatting tips."
parent: "do-you-have-data"
jobs_to_be_done:
  - "Differentiate between longitude (X) and latitude (Y) coordinates and identify common coordinate formats."
  - "Select an appropriate geographic identifier and visualization method based on mapping needs."
next-steps:
  - label: "It's an address or cross-street."
    type: resource
    ref: geocoding
  - label: "It's a named place or administrative unit (census geographies, zip codes, school districts, National Parks, etc.)"
    type: resource
    ref: admin-units
  - label: "It's in latitude and longitude (XY coordinates)."
    type: resource
    ref: lat-long
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
Many times you might have data that has geographic information in a table form. Geographic information might include: an address or cross-street, an administrative unit (e.g. census geographies, zip codes, provinces, territories, school districts, etc.), XY coordinates (e.g. latitude and longitude), or place names. Sometimes the geographic identifier is easily understandable such as a county name. Other times a unique identifier such as a FIPS code will be the geographic identifier that can be used. 

It just takes a little work to convert your geographic information into a geospatial format. 

You might choose different approaches depending on how you wish to visualize your data on your map. Some methods result in points while others represent results in areas. 

<!-- Expand / Collapse Controls -->
<div style="margin: 1.5rem 0;">
  <button onclick="expandAll()">Expand all</button>
  <button onclick="collapseAll()">Collapse all</button>
</div>

<div>

<details class="collapsible" markdown="1">

<summary markdown="span"><strong>Addresses</strong></summary>
Addresses may be in a single field or in multiple fields. They may be street blocks, or missing the actual street number. P.O. Boxes will only map to the Zip code, not the actual address. Addresses are typically visualized as points.

**Examples:**

| Address |
| :---- |
| 124 Main Street |

OR 

| Street\_Number | Street |
| :---- | :---- |
| 124  | Main Street |

| Address |
| :---- |
| 2400 Block of Elm St |

| Street\_Number | Street | City | State | Zip |
| :---- | :---- | :---- | :---- | :---- |
| 917 | 1st Avenue | Anywhere | CA | 12398 |

</details>

</div>

<div>

<details class="collapsible" markdown="1">

<summary markdown="span"><strong>Administrative units</strong></summary> 
Administrative units may vary greatly based on your area of interest. Administrative units also vary around the world. Administrative units are typically visualized as areas (polygons). 

**Examples:**
* Census block/tract/group    
* Zip codes (5 or 9 digit) \- 12398 or 12398-3485  
* State name \- California or 06 (FIPS code)  
* Voting district \- San Francisco Supervisorial District 1  
* Parcel numbers
</details>

</div>

<div>

<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Place names & points of interest</strong></summary>

Place names can be interesting. The approach you select will depend on how you want to visualize the data. They may also require some data wrangling. Place names and points of interest can be represented by points or areas (polygons) depending on the method that you use. 

**Examples:**
* [Federal Information Processing Standards (FIPS)](https://www.nist.gov/standardsgov/compliance-faqs-federal-information-processing-standards-fips) \- Numerical identifiers that describe geographic areas includes two digit states codes and five digit county and entity codes.  
  * California FIPS code is 06  
  * Alameda County FIPS code is 06001          
  * [Full list of FIPS codes](https://transition.fcc.gov/oet/info/maps/census/fips/fips.txt)  
* [Geographic Names Information System (GNIS)](https://www.usgs.gov/tools/geographic-names-information-system-gnis) \- Official names for geographic features in the 50 States, the District of Columbia, and the dependent areas of the United States, as well as Antarctica. Includes populated places, lakes, streams, summits, valleys, and ridges.
</details>

</div>

<div>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>XY coordinates (latitude and longitude)</strong></summary>

With XY coordinates, the X value indicates how far east or west a feature is (longitude), and the Y value indicates how far north or south it is (latitude). Negative values are possible. XY coordinates can come in a number of formats. These are visualized as points.

**Examples:**
* 37.375184, \-120.419319  
* 37° 22' 30.6624", \- 120° 25' 9.5484"  
* 37° 22.51104', \- 120° 25.15914'  
* Easting: 487,000 m, Northing: 3,618,000 m
</details>

</div>
<script>
function expandAll() {
  document.querySelectorAll('details.collapsible')
    .forEach(d => d.open = true);
}

function collapseAll() {
  document.querySelectorAll('details.collapsible')
    .forEach(d => d.open = false);
}
</script>
