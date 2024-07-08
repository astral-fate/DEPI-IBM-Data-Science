## EDA

We were provided with pandas serise in the form of CSV, by checking its type.

``` 
type(df) 
``` 

We then have to cast it to Pandas DataFrame.

```  
df = pd.DataFrame(df)

``` 

We then assigned the values of the 2nd row as the labels od the dataframe.

``` 
df.columns = df.iloc[0]
``` 

## EDA

To find the corr between "CPU_frequency", "Screen_Size_inch" and "Weight_pounds" against "Price". Also, print the value of correlation of each feature with "Price", we used Pandas ``` bar``` 

``` 
plt.bar(df.CPU_frequency, df.Price)

plt.show()   
```
Plotting the scatter-plot using Python, I have faced the issue ``` no numeric data to plot" error``` . Turns out this is because of the type of the data is Serise, we have converted it to DataFrame, then we forced Pandas to consider all data as float using 
``` df['GPU']=df['GPU'].astype(float) ``` to the rest of the cat variables.

## Data Viz using MatPlot

``` 
import matplotlib as plt

# to draw a bar
plt.bar(x,y)
plt.show()


# to draw a line
plt(x,y)
plt.show()

# to scatter plot
plt.scatter(x,y)
plt.show()

#to draw box plot
plt.boxplot(df['x'])
plt.show()

```

## Refrences
https://favtutor.com/articles/convert-pandas-series-to-dataframe/
https://www.kaggle.com/code/mariiagusarova/complete-data-science-fintech-project-part-i
https://www.youtube.com/watch?v=naRQyRZrXCE
https://www.sololearn.com/en/learn/courses/le-python-for-data-science?location=2

## Debuging issues

https://stackoverflow.com/questions/31494870/pandas-dataframe-no-numeric-data-to-plot-error
