# CarPriceDashAppML_Integrated

## This is a web application project based on Dash which gives the predicted price respect to given feature of the second hand car. 
## This project also includes the data analysis part and selection of best ML model based on the original data.

### For dash applicaion

###### import dash
###### import dash_html_components as html
###### import dash_core_components as dcc
###### from dash.dependencies import Input, Output,State

#### These are the libraries required for dealing with html css component with python 

###### Creating Dash Application : app= dash.Dash()   

###### app.layout=html.Div( style={'backgroundColor': '#000000','height':'100vh'}, children=[
######     html.H1("Welcome to Car Price Prediction App",
######         style={
######              'textAlign':'center',
######             'color':'#FFA500'
######         }
######          ])

###### 17-23:  This is a set of app layout i.e adding the required component to the app. It contaiins here a div element cotains own style element and having one h1 ###### tag as a child element. In the app, There properties are enhenced for creating the app



##### callback part is required for the backend logic part, in this project this simply working on the selected ML model
##### below the code takes input value from the id of html element,output will be based on the creating function.
###### @app.callback(
    Output("output", "children"),
    Input("age", "value"),
    Input("km", "value"),
    Input("weight", "value"),
    Input("hp", "value"),
    Input("mc", "value"),
    Input("cc", "value"),
    Input("doors", "value"),
)

##### this is the output function which trasform the data first to be fitted for the ML model prediction with minmax scaler and return the prediction based on model output.
###### def update_output(input1,input2,input3,input4,input5,input6,input7):
    X=PredictorScalerFit.transform([[input1,input2,input3,input4,input5,input6,input7]])
    return loaded_model.predict(X);
