---
title: "Geocoding"
sub-title: "Tips for formatting; Info about geocoding."
parent: "admin-units"
parent_url: /resources/admin-units/
permalink: /resources/geocoding/
jobs_to_be_done:
  - "Locate GIS datasets for research"
  - "Access open geospatial data repositories"
  - "Identify reliable data sources for your project"
next-steps:
  - label: "I need to do some data cleanup first"
    type: resource
    ref: cleaning-messy-data
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
Geocoding is the process of determining geographic coordinates for place names, street addresses, and codes (e.g., zip codes). Geocoding is typically preceded by the data cleaning step of preprocessing and standardizing the format of the data you will be geocoding. The resulting locations are output as geographic features with attributes, which can be used for mapping or spatial analysis. 

Related tasks include:

* **Batch geocoding:** geocoding multiple addresses, place names or codes at one time.  
* **Reverse geocoding:** determining the nearest street address for a given point location specified as a latitude and longitude.

Geocoding is an iterative process. At times it requires mapping/geocoding your data, reviewing the results, and then doing data clean up to improve your results. As you review your results, double check to make sure the locations make sense based on what your expectations are. 

<!-- Expand / Collapse Controls -->
<div style="margin: 1.5rem 0;">
  <button onclick="expandAll()">Expand all</button>
  <button onclick="collapseAll()">Collapse all</button>
</div>
<details class="collapsible" markdown="1">
  
<summary markdown="span"><strong>Esri / ArcGIS</strong></summary>

[ArcGIS Online World Geocoding Service](http://desktop.arcgis.com/en/arcmap/latest/manage-data/geocoding/working-with-arcgis-online-geocoding-service.htm)  
The Esri World Geocoding Service provides high quality geocoding for place names, addresses and zip codes within the USA. It also works with locations outside of the USA, but in sometimes more limited ways. You can also access this through ArcGIS Pro, ArcMap, or the browser-based ArcGIS Online. Using this service requires an ArcGIS Online account and credits. 
</details>
<details class="collapsible" markdown="1">
  
<summary markdown="span"><strong>QGIS</strong></summary>

The [MMQGIS plugin](https://michaelminn.com/linux/mmqgis/) is a Python plugin for QGIS that contains geocoding tools, which can draw on the Google Geocoding API data, the OpenStreetMap Nominatim service, or a local street address layer, such as the [US Census Bureau's TIGER/Line data](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html). To use it, download the plugin first. Then select the “Geocode CSV with Google / OpenStreetMap” feature found under MMQGIS--\>Geocode.

</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Other</strong></summary>

Browser-based:

* [Batchgeo](https://www.batchgeo.com/) \-Free online tool to do basic geocoding. Once your information is geocoded, you can then use it for analysis or visualization in a GIS. The site also has a tool to calculate distances to multiple addresses from a single point.  
* [Geocodio](https://www.geocod.io/) \-US and Mexico, browser based, 2,500 addresses per month, must create account. Once your information is geocoded, you can then use it for analysis or visualization in a GIS.  
* [Texas A\&M Geoservices](http://geoservices.tamu.edu/Services/Geocode/) \- US only, browser based, 2,500 addresses, then must purchase plan, must create account.

</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Python:</strong></summary> 

* [Geopy](https://github.com/geopy/geopy) **\-** General purpose geocoding and reverse geocoding via various online services.  
* [Geocodio Python Library](https://www.geocod.io/updates/2025-08-11-introducing-the-official-geocodio-python-library/) \- Bulk geocoding and data enrichment for US and Canadian addresses.  
* [Pgeocode](https://pypi.org/project/pgeocode/) \- Fast lookups for data within a single country using postal codes, no internet required.  
* [GeoPandas](https://geopandas.org/en/stable/) \- Data analysis pipelines and mapping, often used with Folium for visualization.  
* [Python Geocoder](https://pypi.python.org/pypi/geocoder) \-  is another open-source library that leverages Python to retrieve latitude and longitude coordinates from Google Maps. One of its advantages is that it can be used completely separately from QGIS.

</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>R</strong></summary>

* [Tidygeocoder](https://jessecambon.github.io/tidygeocoder/) \- A unified high-level interface is provided for a selection of supported geocoding services and results are returned in tibble (dataframe) format.  
* [Ggmap](https://www.rdocumentation.org/packages/ggmap/versions/4.0.1/topics/geocode) \- Geocodes (finds latitude and longitude of) a location using the Google Geocoding API. Note: To use Google's Geocoding API, you must first enable the API in the Google Cloud Platform Console.  
* [Arcgisgeocode](https://cran.r-project.org/package=arcgisgeocode) \- A very fast and robust interface to ArcGIS 'Geocoding Services'. Provides capabilities for reverse geocoding, finding address candidates, character-by-character search autosuggestion, and batch geocoding.  
* [Tmaptools](https://cran.r-project.org/web/packages/tmaptools/index.html) \-Set of tools for reading and processing spatial data. The aim is to supply the workflow to create thematic maps. This package also facilitates 'tmap', the package for visualizing thematic maps.

API services? (Nominatum, Census geocoder, etc.)

</details>
<details class="collapsible" markdown="1">
<summary markdown="span"><strong>Tips for Geocoding</strong></summary>

Geocoding works well when you have done some data cleanup. Below are considerations you might want to consider before you geocode your data. 

* The more data one has, the longer it might take to standardize and clean up the data.  
* One address column vs. multiple \- clean data by separating address components (street, city, state, zip) into distinct columns and remove non-essential text.  
* Check your tool for how they handle standard abbreviations \- internal consistency is important.  
* Streets with numbers for names can cause issues. There’s no single solution, this may be a trial and error approach. The data you want to geocode should match the spelling of the name in the Locator, which should match the real world name. (e.g. First Street vs. 1st Street)  
* Remove unit numbers if they cause matching issues,   
* Standardize spellings for prefixes (E. Countyline Rd. vs. Countyline Rd.)  and suffixes (e.g., "St." vs "Street").  
* Standardize ZIP codes to be with and without extensions (e.g. 92517 vs 92517-5900)  
* Block addresses, such as 2400 Block of Main Street, will not map. Your data might map if the address is changed to 2400 Main Street.   
* If you have a million addresses and half are duplicates, clean up the data.  
* Always review your output to check for addresses that couldn't be matched. Anticipate needing to undergo one or more iterations of data clean up and geocoding attempts.   
* To ensure data is accurately mapped, use common mapping programs such as Google Maps to verify problematic addresses.  
* The above are just some examples, but your data may have other unique characteristics that need to be reviewed.
</details>

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
