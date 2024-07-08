## EDA

We were provided with pandas serise in the form of CSV, by checking its type.

''' 
type(df) 
'''

We then have to cast it to Pandas DataFrame.

''' 
df = pd.DataFrame(df)

'''

We then assigned the values of the 2nd row as the labels od the dataframe.

'''
df.columns = df.iloc[0]
'''

## EDA

To find the corr between "CPU_frequency", "Screen_Size_inch" and "Weight_pounds" against "Price". Also, print the value of correlation of each feature with "Price", we used Pandas '''bar'''.

'''
plt.bar(df.CPU_frequency, df.Price)

plt.show()   
'''
