---
title: "Visualize your data in a GIS program"
sub-title: "Does your data show up in the map where you expect it to?"
parent: "choose-a-platform"
parent_url: /choose-a-platform/
permalink: /resources/ingest-data/
jobs_to_be_done:
  - "Explain the role of basemaps in GIS visualization."
  - "Import and view common GIS data formats."
next-steps:
  - label: "Yes, it's where I expected it to be."
    type: question
    ref: data-coverage
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
## Basemaps

Regardless of what GIS platform you choose to use, a basemap will orient your data to the real world and provide context for maps at global or local scales. A basemap layer is typically the first layer added to a map. It allows you to easily see where geographic features are located. It typically includes features and labels for land, water, roads, buildings, cities, places, and administrative boundaries, but can also include satellite and aerial image data.

## Adding Data

There are a few different ways to add data to a map.

<div style="margin: 1.5rem 0;">
  <button onclick="expandAll()">Expand all</button>
  <button onclick="collapseAll()">Collapse all</button>
</div>

<details class="collapsible">
  <summary><strong>ArcGIS Online</strong></summary>

  <p>
    We recommend adding data first to the <strong>My Content</strong> section and then adding the data to a map.
  </p>
</details>

<details class="collapsible">
  <summary><strong>ArcGIS Pro</strong></summary>

  <p>
    We recommend using the Add Data button and selecting the appropriate data source.
  </p>
</details>

<details class="collapsible">
  <summary><strong>QGIS</strong></summary>

  <p>
    Add data in QGIS using the Data Source Manager tool. Another option is to drag and drop data from the Browser panel into the Layers panel.
  </p>
</details>

<details class="collapsible">
  <summary><strong>Python</strong></summary>

<pre><code class="language-python">
# Adding GIS (Geographic Information System) data to Python is very common
# in data science, mapping, and spatial analysis.

# General workflow:
# 1. Install the right libraries
# 2. Load GIS data (e.g., shapefiles, GeoJSON, raster)
# 3. Work with it (analyze, transform, visualize)

import geopandas as gpd

# Load shapefile
gdf = gpd.read_file("data/shapefile.shp")

# View data
print(gdf.head())

# Load GeoJSON
gdf = gpd.read_file("data/file.geojson")

</code></pre>

</details>

<script>
function expandAll() {
  document
    .querySelectorAll("details.collapsible")
    .forEach(function(d) {
      d.open = true;
    });
}

function collapseAll() {
  document
    .querySelectorAll("details.collapsible")
    .forEach(function(d) {
      d.open = false;
    });
}
</script>

## Did You Know?

- If you ingested your data using ArcGIS Pro or ArcGIS Online, you can add additional datasets using the ArcGIS Living Atlas.
- In ArcGIS Online, you can drag and drop a data file directly onto the map, which will automatically add it to **My Content**.
- In QGIS, you can connect to publicly hosted ArcGIS Online services through the ArcGIS REST Server connection.
- In ArcGIS and QGIS, polygon layers near the top of the layer list can hide layers underneath them.

## Troubleshooting

- **Coordinate System and Projection Errors**
  - **Missing or Wrong CRS:** If you load tabular data such as a CSV with XY coordinates and the points appear in the wrong location, your coordinate reference system (CRS) is likely incorrect or undefined.
  - Confirm the source CRS and ensure it matches your map projection.

- **Corrupt Geometry**
  - **Check Geometry:** Some features may contain invalid, null, self-intersecting, or looping geometries.
  - **The Fix:**
    - **ArcGIS Online:** Download and repair the data outside ArcGIS Online.
    - **ArcGIS Pro:** Run **Check Geometry** and then **Repair Geometry**.
    - **QGIS:** Run **Fix Geometries** from **Processing > Toolbox**.

- **Attribute Table Errors ("Could Not Load Data")**
  - **Failed to Load Rows:** Schema mismatches, corrupt records, or invalid spatial indexes can cause attribute tables to fail.
  - **The Fix:**
    - **ArcGIS Online:** Download the data and check for null values or unsupported characters.
    - **ArcGIS Pro:** Recalculate the spatial index or export the data to a new File Geodatabase.
    - **QGIS:**
      - Run **Create Spatial Index**.
      - Use the **Table Structure Compare** plugin to identify schema issues.

## General Resources

- [ESRI Basemaps](https://developers.arcgis.com/documentation/mapping-and-location-services/mapping/basemaps/)
- [ArcGIS Online: Add Files as Items](https://doc.arcgis.com/en/arcgis-online/manage-data/add-files-as-items.htm)
- [ArcGIS Pro: Add Data](https://doc.esri.com/en/arcgis-pro/latest/get-started/add-data-to-your-project.html)
- [QGIS: Basic Map Preparation](https://docs.qgis.org/3.44/en/docs/training_manual/basic_map/preparation.html)
