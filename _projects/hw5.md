--- 
layout: default 
title: HW5 - Bigfoot Visualizations 
--- 

# Bigfoot Sightings Visualizations 
[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv) 
[The Analysis](https://github.com/ppate475/ppate475.github.io/blob/main/python_notebooks/HW5_purva.ipynb) ---

---

## Visualization 1

This visualization shows the total count of reported Bigfoot sightings per U.S. state, allowing viewers to quickly find geographic patterns and regions with higher activity. I used a bar chart because it is effective for comparing categorical values across many groups.

The x-axis encodes the state as nominal data, while the y-axis represents the frequency of sightings as quantitative data. I sorted the bars in descending order so viewers can clearly see which states have the highest number of reports. To add more context, I incorporated color encoding to represent the lunar phase during each sighting using a categorical color scheme. This helps show any potential environmental patterns while still maintaining visual clarity.

On the analysis side in my Python notebook, I performed several data transformations. I first cleaned the dataset by removing incomplete records with missing spatial or temporal information for accuracy. I then grouped the data by state to calculate total counts. Additionally, I created a new categorical variable by binning the continuous `moon_phase` values into four categories (New, Waxing, Full, Waning), making the color encoding more meaningful and easier for viewers to understand.

<div id="vis1"></div>

---

## Visualization 2

This visualization is a scatter plot exploring the relationship between environmental conditions during reported Bigfoot sightings, specifically temperature and visibility. The x-axis encodes average temperature (quantitative), and the y-axis represents visibility in miles (quantitative), with each point corresponding to an individual sighting.

I used a scatter plot to examine potential relationships between these continuous variables. Color encodes the classification of sightings (Class A, B, or C), which allows viewers to distinguish between levels of credibility while maintaining visual clarity through a consistent categorical color scheme.

On the analysis side, I filtered the dataset to include relevant variables such as temperature, visibility, and classification, and removed records with missing or improperly formatted values to ensure accuracy and readability in the visualization.

To enhance clarity and user exploration, I implemented two layers of custom interactivity. First, I added a bound dropdown menu that allows users to filter sightings by classification. When a category is selected, other points fade to light gray, reducing visual clutter and making patterns within the selected group easier to identify while still preserving context. Second, I included detailed hover tooltips that display additional information such as date, state, temperature, and classification for each point. This transforms the plot from a static overview into an interactive tool, allowing users to investigate specific observations and outliers more effectively.

<div id="vis2"></div>

---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
vegaEmbed('#vis1', '/assets/plot1_bar.json');
vegaEmbed('#vis2', '/assets/plot2_interactive.json');
</script>
