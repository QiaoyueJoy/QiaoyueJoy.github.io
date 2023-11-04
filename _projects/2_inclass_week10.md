---
name: Homework8
tools: [Python, HTML, vega-lite]
image: assets/pngs/city.png
description: Licenses Data
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Dataset:
https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv

# Number of Licenses Issued in Top Cities

<vegachart schema-url="{{ site.baseurl }}/assets/json/city_chart.json" style="width: 100%"></vegachart>

This chart shows the Number of Licenses Issued by Top 20 Cities visualization. This bar chart is designed to provide a clear understanding of which cities have the highest number of licenses issued. 

Encoding type: I used nominal encoding (`"City:N"`) for the x-axis to represent the city names, and quantitative encoding (`"Count:Q"`) for the y-axis to represent the number of licenses. Besides, I used a green color scheme (`scale=alt.Scale(scheme='greens')`) .

Data transformations: The conversion of the 'Original Issue Date' from a string to a datetime object using `pd.to_datetime` function. The `format`  was set to `'%m/%d/%Y'` to match the date format in the dataset. Additionally,  `errors='coerce'` ensures that if any string does not match the specified date format, insert a 'NaT'.

Interactivity: Used `alt.selection_point()` on mouse to enhance the chart by highlighting the bar which the user hovers over. This interaction helps in drawing user's attention to specific city data. Besides, it also makes the chart more easier to read, since there are a lots of cities.

# Licenses Issued Each Year

<vegachart schema-url="{{ site.baseurl }}/assets/json/year_chart.json" style="width: 100%"></vegachart>

This bar chart shows the number of licenses issued each year. 

Encoding type: I used ordinal encoding (`"Year:O"`) for the x-axis since the years are discrete but ordered, and quantitative encoding (`"Counts:Q"`) for the y-axis. There is no color encoding used in this chart.

Data transformations: Already did in first process.



<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/QiaoyueJoy/QiaoyueJoy.github.io/blob/main/assets/json/city_chart.json" text="First Plot Data" %}
</div>

<div class="left">
{% include elements/button.html link="https://github.com/QiaoyueJoy/QiaoyueJoy.github.io/blob/main/assets/json/year_chart.json" text="Second Plot Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/QiaoyueJoy/QiaoyueJoy.github.io/tree/main/python_notebooks/homework8.ipynb" text="The Analysis" %}
</div>

