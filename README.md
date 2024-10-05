#%%
# pulling from plotly express and panda libraries
import plotly.express as px
import pandas as pd

#%%
# pulling from panda libraries
import pandas as pd
# read the csv file Air Passengers for the data we need to plot
df = pd.read_csv('AirPassengers.csv')

print(df.to_string())

#%%
# pulling from plotly express and panda libraries
import pandas as pd
import plotly.express as px
# read the csv file Air Passengers for the data we need to plot
df = pd.read_csv('AirPassengers.csv')
# Converting the 'Month' column to datetime format for proper time series plotting
df['Month'] = pd.to_datetime(df['Month'])
# creating line plot
fig_line = px.line(df, x='Month', y='#Passengers', title='Flight Volume by Month', 
                   line_shape='linear', line_dash_sequence=['solid'])
# adding customization for line
fig_line.update_traces(line=dict(color='red'))
# adding customization for ticker numbers on axis
fig_line.update_layout(
    xaxis=dict(tickfont=dict(color='green')),
    yaxis=dict(tickfont=dict(color='green'))
)
#display line plot
fig_line.show()

#%%
# creating bar plot
fig_bar = px.bar(df, x='Month', y='#Passengers', title='Flight Volume by Month', 
                labels={'Month': 'Month', '#Passengers': 'Number of Passengers'})
# customizing color to orange cars
fig_bar.update_traces(marker_color='orange')
#display bar plot
fig_bar.show()

#%%
# creating scatter plot
fig_scatter = px.scatter(df, x='Month', y='#Passengers', 
                             title='Flight Volume by Month',
                             labels={'Month': 'Month', '#Passengers': 'Number of Passengers'})
# customizing points as green triangles
fig_scatter.update_traces(marker=dict(symbol='triangle-up', color='green'))
# display scatter plot
fig_scatter.show()

#%%
# pulling from plotly graph objects and panda libraries
import pandas as pd
import plotly.graph_objects as go
# read the csv file Air Passengers for the data we need to plot
df = pd.read_csv('AirPassengers.csv')
# Converting the 'Month' column to datetime format for proper time series plotting
df['Month'] = pd.to_datetime(df['Month'])
# Creating a new figure object for the plot
fig = go.Figure()
# Adding a trace to the figure for the line plot including customizations
fig.add_trace(go.Scatter(
    x=df['Month'],
    y=df['#Passengers'],
    mode='lines+markers',
    name='Line Plot',
    line=dict(color='blue', width=2, dash='dash'),
    marker=dict(symbol='cross', size=5, color='red')
    ))
# layout for plot
fig.update_layout(title='Passenger Counts Over Time',
                  xaxis_title='Month',
                  yaxis_title='Number of Passengers')
# display line plot with 
fig.show()

#%%
# creating the new figure
fig2 = go.Figure()
# creating bar chart with custom purple bars
fig2.add_trace(go.Bar(x=df['Month'], y=df['#Passengers'], name='Flight Volume', marker_color='purple'))
# label for chart
fig2.update_layout(title='Flight Volume')
# display bar chart
fig2.show()

#%%
# creating new figure
fig3 = go.Figure()
# creating scatter plot with custom red stars
fig3.add_trace(go.Scatter(x=df['Month'], y=df['#Passengers'], mode='markers', name='Flight Volume', marker=dict(symbol='star', size=10, color='red')))
# label for chart
fig3.update_layout(title='Flight Volume')
# display scatter plot
fig3.show()

#%%
# I am really enjoying putting the code to practice now for visualization. 
# It is hard to say whether I like express or Graph Objects more. 
# They seem pretty similar in there fuctionality.
# I enjoyed the customization process. 
# I tried to use unqiue color and design patterns for each.
