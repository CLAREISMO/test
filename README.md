# test

## **5. Data Types and Missing Values**


### **Introduction**

In this tutorial, you'll learn how to investigate data types within a DataFrame or Series. You'll also learn how to find and replace entries.


###**Dtypes**
The data type for a column in a DataFrame or a Series is known as the dtype.
You can use the dtype property to grab the type of a specific column. 

![image](https://github.com/CLAREISMO/test/assets/63759427/1f3dd988-3db4-4a89-b26d-1fa95fb7872f)

![image](https://github.com/CLAREISMO/test/assets/63759427/89ab3e0a-2ddd-4f3e-8ff9-e6d7589da01e)


Alternatively, the dtypes property returns the dtype of every column in the DataFrame:

![image](https://github.com/CLAREISMO/test/assets/63759427/a11bbfed-29ea-4a7a-83b3-146864b025de)

![image](https://github.com/CLAREISMO/test/assets/63759427/4a45519b-2bad-45c7-950f-ba4fe895608d)


+ Data types tell us something about how pandas is storing the data internally. float64 means that it's using a 64-bit floating point number; int64 means a similarly sized integer instead, and so on.

+ One peculiarity to keep in mind (and on display very clearly here) is that columns consisting entirely of strings do not get their own type; they are instead given the object type.

+ It's possible to convert a column of one type into another wherever such a conversion makes sense by using the astype() function. 

+ For example, we may transform the points column from its existing int64 data type into a float64 data type

![image](https://github.com/CLAREISMO/test/assets/63759427/d943a33b-08b1-4343-b9c4-be54b321e155)

![image](https://github.com/CLAREISMO/test/assets/63759427/e8c9da45-b2f4-4ee2-90ac-2a848971cfbd)


Pandas also supports more exotic data types, such as categorical data and timeseries data.


###**Missing data**
Entries missing values are given the value NaN, short for "Not a Number". For technical reasons these NaN values are always of the float64 dtype.

**ISNULL - NaN**
Pandas provides some methods specific to missing data. To select NaN entries you can use pd.isnull() (or its companion pd.notnull()). This is meant to be used thusly:

![image](https://github.com/CLAREISMO/test/assets/63759427/ad353c28-19e4-4c3c-b2aa-a4771bd45910)

![image](https://github.com/CLAREISMO/test/assets/63759427/ab9c1ab7-7729-41c4-a105-050df39d89ba)


###**Fillna() - Unknown**

+ Replacing missing values is a common operation. 

+ Pandas provides a really handy method for this problem: fillna(). fillna() provides a few different strategies for mitigating such data. 

+ For example, we can simply replace each NaN with an "Unknown"


![image](https://github.com/CLAREISMO/test/assets/63759427/6ab3ad3d-73a0-45e8-9d57-5415f53c15ae)

![image](https://github.com/CLAREISMO/test/assets/63759427/904539a5-207b-487e-a901-f125fdabf7d0)


###**Replace() Method**

+ Or we could fill each missing value with the first non-null value that appears sometime after the given record in the database. This is known as the backfill strategy.

+ Alternatively, we may have a non-null value that we would like to:

![image](https://github.com/CLAREISMO/test/assets/63759427/d6146fe3-c9ea-4ee4-a2ab-277bbf5ed543)

![image](https://github.com/CLAREISMO/test/assets/63759427/2ccabffc-0388-46bb-a617-5426488512e2)


The replace() method is worth mentioning here because it's handy for replacing missing data which is given some kind of sentinel value in the dataset: things like "Unknown", "Undisclosed", "Invalid", and so on.


















#############################################################################################################################

## **4. Grouping and Sorting**

### **Introduction**

Scale up your level of insight. The more complex the dataset, the more this matters!

Maps allow us to transform data in a DataFrame or Series one value at a time for an entire column. However, often we want to group our data, and then do something specific to the group the data is in.

As you'll learn, we do this with the groupby() operation. We'll also cover some additional topics, such as more complex ways to index your DataFrames, along with how to sort your data.

**Groupwise analysis**: One function we've been using heavily thus far is the value_counts() function. We can replicate what value_counts() does by doing the following:

![image](https://github.com/CLAREISMO/test/assets/63759427/235bfc4b-f289-47e4-a7cb-a81ee130702b)

+ value_counts() is just a shortcut to this groupby() operation.  

+ We can use any of the summary functions we have used before with this data!


**Groupwise analysis and min() function**: For example, we can use the min() function. We then group by the variable ANOS_ESCOLARIDAD and ask it to return the minimum value associated with the variable ESTRATO_VIVIENDA associated with.

![image](https://github.com/CLAREISMO/test/assets/63759427/27988d25-9dee-4bf4-b4d1-4aafe2f5b051)

![image](https://github.com/CLAREISMO/test/assets/63759427/13454ca3-bd0a-4642-8bfe-fed1f7f78f6c)


Let's see another example with the min() function associated with the groupby() method. We see the behavior of the minimum values of the salaries with respect to the variable ANOS_ESCOLARIDAD. 

![image](https://github.com/CLAREISMO/test/assets/63759427/b881c626-2cee-4aab-9d69-01aba174bf39)

We obtain the minimum value of the salaries with respect to the variable SCHOOL_YEARS


![image](https://github.com/CLAREISMO/test/assets/63759427/14544a7a-69dc-4379-af0c-2f6e602b68ca)

**Groupwise analysis and max() function**: We can also use the max() function to obtain the maximum values of the variable to be analyzed with respect to the variable established in the groupby() method.

Next, we are going to make a comparison with the previous example. We are going to analyze the maximum values of the salaries with respect to the variable  SCHOOL_YEARS.

![image](https://github.com/CLAREISMO/test/assets/63759427/fa925a30-274d-4c7f-8c84-6ffd969429ad)

![image](https://github.com/CLAREISMO/test/assets/63759427/3e70aa48-aa30-4089-8ea3-082019ba7c5d)

Through the relationship between Groupwise analysis and other functions, we can obtain valuable information in the analysis of our data.


**Apply() method**
You can think of each group we generate as being a slice of our DataFrame containing only data with values that match. This DataFrame is accessible to us directly using the apply() method, and we can then manipulate the data in any way we see fit.

For a better understanding of the Apply method let's take a look at the following example.

![image](https://github.com/CLAREISMO/test/assets/63759427/106eab59-f535-453a-9837-0aa566ce3d36)


![image](https://github.com/CLAREISMO/test/assets/63759427/d137afea-6eab-4513-bce4-d031f810ed45)

**More detailed control with apply:** For even more fine-grained control, you can also group by more than one column.


![image](https://github.com/CLAREISMO/test/assets/63759427/e446101a-29ed-4a15-a746-90d6242b4aac)

In the first detailed apply( we are grouping HOUSING_STRATUM AND N_CHILDREN WITH RESPECT TO LABOUR INCOME THAT'S WHY THE COLUMN OF N_CHILDREN_MINOR_15TH ANNUAL INCOME IS kept with the original information of the dataset.

![image](https://github.com/CLAREISMO/test/assets/63759427/e91e58c3-96de-40b2-8279-62d13c4795fe)

![image](https://github.com/CLAREISMO/test/assets/63759427/2d9483a3-23b8-46fc-8a4c-ce73690f607e)

In the second apply() the labels ESTRATO_VIVIENDA and N_HIJOS_HIJOS within the groupby are maintained, these labels are compared with respect to the label N_HIJOS_MENORES_15ANOS through the method apply(). the output shows the change in the presentation of the information.

![image](https://github.com/CLAREISMO/test/assets/63759427/fa695387-bd4c-4a2f-8896-eec363086a51)

![image](https://github.com/CLAREISMO/test/assets/63759427/7bf5e2ee-9d22-4a21-bd4f-51f3a1f39721)


**Agg() METHOD**

Another groupby() method worth mentioning is agg(), which lets you run a bunch of different functions on your DataFrame simultaneously. For example, we can generate a simple statistical summary of the dataset as follows:

![image](https://github.com/CLAREISMO/test/assets/63759427/7c9f0cbf-5682-4959-8b57-640595d2548d)

![image](https://github.com/CLAREISMO/test/assets/63759427/40f83f9e-e4b7-4862-885d-897428e9f94f)

We determine the length and the minimum and maximum values present along the values of the variables ESTRATO_VIVIENDA and NOMBRE_DEPT.

**Multi-indexes**

In all of the examples we've seen thus far we've been working with DataFrame or Series objects with a single-label index. groupby() is slightly different in the fact that, depending on the operation we run, it will sometimes result in what is called a multi-index.

A multi-index differs from a regular index in that it has multiple levels. For example:

![image](https://github.com/CLAREISMO/test/assets/63759427/bda70594-0c34-4e4a-ac9d-5406919edd97)

![image](https://github.com/CLAREISMO/test/assets/63759427/029fef30-9f60-4498-a4f3-0b5b2c8ee6bc)


Within groupby() we group the variables ANOS_ESCOLARIDAD and ESTRATO_VIVIENDA. The variable N_CHILDREN will be analyzed with respect to the previous ones in terms of length and maximum and minimum values.


**Various methods for the multiple indices**

Multi-indices have several methods for dealing with their tiered structure which are absent for single-level indices. They also require two levels of labels to retrieve a value. Dealing with multi-index output is a common "gotcha" for users new to pandas.

The use cases for a multi-index are detailed alongside instructions on using them in the MultiIndex / Advanced Selection section of the pandas documentation.

However, in general, the multi-index method you will use most often is the one for converting back to a regular index, the reset_index() method.

![image](https://github.com/CLAREISMO/test/assets/63759427/61993f70-3dfb-4b70-8e0d-ed25b5fb0e1b)

![image](https://github.com/CLAREISMO/test/assets/63759427/1ef309c8-85e6-413c-9d15-72e8666d76e5)


**Sorting**
We can see that grouping returns data in index order, not in value order. That is to say, when outputting the result of a groupby, the order of the rows is dependent on the values in the index, not in the data.

To get data in the order want it in we can sort it ourselves. The sort_values() method is handy for this.

![image](https://github.com/CLAREISMO/test/assets/63759427/eb14a5b3-2287-4e38-8bb8-a42fe0dfbe7d)

![image](https://github.com/CLAREISMO/test/assets/63759427/2ebca645-4d79-4df9-b680-e1301a6a21ba)


**Sorted by max():** We will then apply the sort method on the variable ESTRATO_VIVIENDA by max

![image](https://github.com/CLAREISMO/test/assets/63759427/d12ba6fa-57ed-48bf-b04c-c7ca7a607ae0)

![image](https://github.com/CLAREISMO/test/assets/63759427/744f63f8-9900-4d40-80be-07eb0996586c)


**Sort Value()**
sort_values() defaults to an ascending sort, where the lowest values go first. 

However, most of the time we want a descending sort, where the higher numbers go first. That goes thusly:

![image](https://github.com/CLAREISMO/test/assets/63759427/51632402-1353-42e1-848f-c87d6ec68dd5)

![image](https://github.com/CLAREISMO/test/assets/63759427/4b716658-9331-4952-ab4c-71310e273d1f)


**Sort_Index()**
To sort by index values, use the companion method sort_index(). This method has the same arguments and default order:

![image](https://github.com/CLAREISMO/test/assets/63759427/a1d532a7-82ad-4406-b09c-6b234975c000)

![image](https://github.com/CLAREISMO/test/assets/63759427/2696e4fd-7cd1-4b6f-9b5d-3d5e3152409e)


**Sort by more than one column at a time**
Finally, know that you can sort by more than one column at a time:

![image](https://github.com/CLAREISMO/test/assets/63759427/7b010db0-3ada-4671-99a3-6226b9f08697)

![image](https://github.com/CLAREISMO/test/assets/63759427/85a2584b-172b-4b30-9653-8524bebcf162)


















































#############################################################################################


### **Sumary Function**

**describe() method:**









































































































































































