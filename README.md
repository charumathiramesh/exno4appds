# Exno 4:APPDS
## Aim:
      To Implement Advanced Visualizations and Geospatial Data using python.
## Algorithm:

Step 1: Include the necessary libraries

Step 2: Add the necessary values to the initialized variables.

Step 3: Install the advanced python necessary libraries such as pygal,plotnine,altair etc. 

Step 4: Use the necessary arguments for the functions used from advanced library

Step 5: Import Geopandas and folium

Step 6: Use folium map function to display the map location

## Coding & Output:
```c
import numpy as np
import matplotlib.pyplot as plt
x=np.array([1,2,3,4,5,6,7,8,9,10])
y=np.tan(x)
z=np.sin(x)
plt.xlabel("Natural Numers")
plt.ylabel("TAN AND SIN VALUES")
plt.plot(x,y,'m', marker='*',markersize=8,markeredgecolor='red')
plt.plot(x,z,'b',linewidth=4,linestyle="--")
plt.title("TAN AND SIN VALUES")
plt.legend(["TAN","SIN"])
plt.show()

```
![386437732-072b3468-49f3-4ee2-a541-6b7842c97ab5](https://github.com/user-attachments/assets/dd4c462f-0360-42a2-98af-fca6a93cf823)


```c
a = np.arange(1, 20)
b = np.log(a)
c = np.cos(0)

plt.xlabel("Numbers")
plt.ylabel("Log numbers")
plt.plot(a, b, 'b', marker='+', markersize=8, markeredgecolor="red", linewidth=5)
plt.plot(a, [c]*len(a), 'k', marker='D', markersize=5, markeredgecolor="blue", linestyle='--')


```


![386437845-db434612-8ea4-4c63-a07d-f8ab769efe83](https://github.com/user-attachments/assets/ba099ef2-3b33-451b-96ba-19af94e4d2bb)

```c
pip install pygal
import pygal
from pygal.style import Style
# Create a custom style
custom_style = Style(
    background='transparent',
    plot_background='transparent',
    foreground='red',
    foreground_strong='blue',
    foreground_subtle='yellow',
    opacity='.6',
    opacity_hover='0.9',
    transition='400ms',
    colors=('#E80080', '#404040')
)

# Create a line chart
line_chart = pygal.Line(style=custom_style, show_legend=True, x_title='Months', y_title='Values')
line_chart.title = 'Monthly Trends'
line_chart.add('Series 1', [1, 3, 5, 7, 9])
line_chart.add('Series 2', [2, 4, 6, 8, 10])

# Render the chart to a file
line_chart.render_to_file('line_chart.svg')
from bokeh.models import HoverTool
from bokeh.plotting import figure, show
from bokeh.io import output_notebook

output_notebook()

p = figure(title="Scatter Plot with Hover Tool", x_axis_label='X-Axis', y_axis_label='Y-Axis')
p.scatter(x=[1, 2, 3, 4, 5], y=[6, 7, 2, 4, 5], size=10, color="green", alpha=0.5)

# Add HoverTool
hover = HoverTool()
hover.tooltips = [("X", "@x"), ("Y", "@y")]
p.add_tools(hover)

# Show the plot
show(p)


```

![386438018-ef4e72e9-4560-469a-82ca-33ddd1c0cc50](https://github.com/user-attachments/assets/7a10782a-aa74-4876-bae7-84fe6ca448fe)


```c
pip install plotnine
import seaborn as sns
df = sns.load_dataset("tips")

from plotnine import theme, element_text

plot = (
    ggplot(df)
    + facet_grid("~sex")
    + aes(x="day", y="total_bill", fill="time")
    + labs(x="day", y="total_bill")
)


# Save the plot
plot.save("gfg_plotnine_tutorial.png")
!pip install altair
pip install vega_datasets
import pandas as pd
import altair as alt
# Making a Pandas DataFrame
score_data = pd.DataFrame({
    'Website': ['StackOverflow', 'FreeCodeCamp', 'GeeksForGeeks', 'MDN', 'CodeAcademy'],
    'Score': [65, 50, 99, 75, 33]
})

# Making the Simple Bar Chart
chart = alt.Chart(score_data).mark_bar().encode(
    x='Website',
    y='Score'
)

# Display the chart
chart


```

![386438248-cdecf867-4c17-4425-8799-08a7d78ae6fd](https://github.com/user-attachments/assets/3aeba697-06b9-4b3d-ab9e-8dfbd63a496c)

```c
# Importing altair
import altair as alt
# Importing the data object from vega_datasets
from vega_datasets import data

# Selecting the data
iris = data.iris()

# Making the Scatter Plot
scatter_plot = alt.Chart(iris).mark_point().encode(
    x='sepalLength',
    y='petalLength',
    shape='species'
)

# Display the scatter plot
scatter_plot


```

![386438329-c8e39772-8cf0-44b8-b9cc-3b2f621f443e](https://github.com/user-attachments/assets/8918bfac-b979-4e31-bd12-23f7fbe74b56)

```c
# Importing the necessary libraries
import altair as alt
import pandas as pd

# Create data
data = pd.DataFrame([
    ['A', 10, 20],
    ['B', 5, 29],
    ['A', 15, 29],
    ['B', 15, 20]
], columns=['Team', 'Round 1', 'Round 2'])

# View data
print(data)

# Create the grouped bar chart
gp_chart = alt.Chart(data).mark_bar().encode(
    alt.Column('Round 2'),       # Column for Round 2
    alt.X('Team'),               # X-axis for Team
    alt.Y('Round 1', axis=alt.Axis(grid=False)),  # Y-axis for Round 1 without grid lines
    alt.Color('Team')            # Color by Team
)

# Display the chart
gp_chart



```



![386438406-a0fc2267-a233-4c25-acac-4a1267727159](https://github.com/user-attachments/assets/bec514d6-0ab1-4b7f-ade7-638ba4c10eb3)

```c
# Import the necessary libraries
import geopandas as gpd
import folium
import pandas as pd

# Initialize the map and store it in a variable 'm'
m = folium.Map(
    location=[10.9, 77.519],
    zoom_start=7,
    tiles='Stamen Terrain',
    attr='Map tiles by Stamen Design, under CC BY 3.0. Data by OpenStreetMap, under ODbL.'
)

# Show the map
m.save('my_map.html')


```







## Result:
Thus , To Implement Advanced Visualizations and Geospatial Data using python.
