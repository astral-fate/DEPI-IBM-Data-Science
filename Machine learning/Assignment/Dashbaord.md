```python
import dash
from dash import dcc, html
import plotly.express as px
import pandas as pd

data = pd.read_csv('data.csv') 

app = dash.Dash(__name__)

# Function to create a bar chart
def create_bar_chart(df, column, title):
    df_count = df[column].value_counts().reset_index()
    df_count.columns = [column, 'Count']
    fig = px.bar(df_count, x=column, y='Count', title=title)
    return fig

# Function to create a pie chart
def create_pie_chart(df, column, title):
    df_count = df[column].value_counts().reset_index()
    df_count.columns = [column, 'Count']
    fig = px.pie(df_count, values='Count', names=column, title=title)
    return fig

# Function to create a histogram
def create_histogram(df, column, title):
    fig = px.histogram(df, x=column, title=title)
    return fig

app.layout = html.Div([
    html.H1("EDA Dashboard"),
    
    html.Div([
        dcc.Graph(id='status-chart', figure=create_bar_chart(data, 'Status', 'Status Distribution')),
        dcc.Graph(id='gender-chart', figure=create_pie_chart(data, 'Gender', 'Gender Distribution')),
    ], style={'display': 'flex'}),
    
    html.Div([
        dcc.Graph(id='education-chart', figure=create_bar_chart(data, 'Education', 'Education Distribution')),
        dcc.Graph(id='marital-status-chart', figure=create_bar_chart(data, 'MaritalStatus', 'Marital Status Distribution')),
    ], style={'display': 'flex'}),
    
    html.Div([
        dcc.Graph(id='employment-status-chart', figure=create_bar_chart(data, 'EmploymentStatus', 'Employment Status Distribution')),
        dcc.Graph(id='home-ownership-chart', figure=create_bar_chart(data, 'HomeOwnershipType', 'Home Ownership Type Distribution')),
    ], style={'display': 'flex'}),
    
    html.Div([
        dcc.Graph(id='use-of-loan-chart', figure=create_bar_chart(data, 'UseOfLoan', 'Use of Loan Distribution')),
        dcc.Graph(id='age-chart', figure=create_histogram(data, 'Age', 'Age Distribution')),
    ], style={'display': 'flex'}),
    
    html.Div([
        dcc.Graph(id='amount-chart', figure=create_histogram(data, 'Amount', 'Loan Amount Distribution')),
        dcc.Graph(id='income-chart', figure=create_histogram(data, 'IncomeTotal', 'Total Income Distribution')),
    ], style={'display': 'flex'}),
])

if __name__ == '__main__':
    app.run_server(debug=True)
```



<iframe
    width="100%"
    height="650"
    src="http://127.0.0.1:8050/"
    frameborder="0"
    allowfullscreen

></iframe>


