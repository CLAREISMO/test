# test

## **3. Summary Functions and Maps**

### **Introduction**

we learned how to select relevant data out of a DataFrame or Series. Plucking the right data out of our data representation is critical to getting work done, as we demonstrated in the exercises.

However, the data does not always come out of memory in the format we want it in right out of the bat. Sometimes we have to do some more work ourselves to reformat it for the task at hand. 

This tutorial will cover different operations we can apply to our data to get the input "just right".

we will use a new dataset so that you can observe different behaviors and infer that any code provided throughout these tutorials can be applied to any dataset.

**You can get different datasets on different topics to practice on the Kaggle portal: https://www.kaggle.com/datasets**


### **Sumary Function**

**describe() method:**

The describe() method: returns a DataFrame with a statistical summary of the columns of the DataFrame df of the type


**describe() method for numeric values:** . For numeric data (number) the mean, standard deviation, minimum, maximum, and quartiles are calculated. This method generates a high-level summary of the attributes of the given column. It is type-aware, meaning that its output changes based on the data type of the input. The output above only makes sense for numerical data.

Below we can see the describe() method applied to numeric data:

![image](https://github.com/CLAREISMO/test/assets/63759427/289faa50-8e29-4c90-bfff-dc030d44e5fe)

![image](https://github.com/CLAREISMO/test/assets/63759427/ba6c869f-de48-4f6f-a31d-d57cfad90d92)


**describe() method for non-numeric values:** For non-numeric data (object) the number of values, the number of distinct values, the mode, and their frequency are calculated. If the type is not specified, only numeric columns are considered. 

Below we can see the describe() method applied to string data:

![image](https://github.com/CLAREISMO/test/assets/63759427/18f00235-934c-4d8e-93d7-1a1686846314)

![image](https://github.com/CLAREISMO/test/assets/63759427/d8af7196-77cf-4a3f-a812-dbdca59c5e75)

![image](https://github.com/CLAREISMO/test/assets/63759427/701f1d5a-be72-491b-af4e-ce54e634db77)




**mean() function**

If you want to get some particular simple summary statistic about a column in a DataFrame or a Series, there is usually a helpful Pandas function that makes it happen.

![image](https://github.com/CLAREISMO/test/assets/63759427/98a03d1e-1bf0-4d17-88ad-686ae1a788a1)


**unique() function**

To see a list of unique values we can use the unique() function:

![image](https://github.com/CLAREISMO/test/assets/63759427/4ddce6a4-e628-4bd4-84e7-eade13986739)


**value_counts() method**
To see a list of unique values and how often they occur in the dataset, we can use the value_counts() method:

![image](https://github.com/CLAREISMO/test/assets/63759427/1e195f53-dc86-4e15-875f-082ff38380cc)

![image](https://github.com/CLAREISMO/test/assets/63759427/36d4f2b1-c5eb-4091-bbdd-de218f645fa3)


### **Maps**

A map is a term, borrowed from mathematics, for a function that takes one set of values and "maps" them to another set of values. 

In data science, we often have a need for creating new representations from existing data, or for transforming data from the format it is in now to the format that we want it to be in later. 

Maps are what handle this work, making them extremely important for getting your work done!

There are two mapping methods that you will use often.


**1. map() method**: map() is the first, and slightly simpler one

![image](https://github.com/CLAREISMO/test/assets/63759427/03f880fe-19e4-4273-b90b-32fd21fb0db4)
![image](https://github.com/CLAREISMO/test/assets/63759427/4c99a60c-187e-4ee9-8c6f-b99e29f81687)


Going deeper into the map() method we have that:

![image](https://github.com/CLAREISMO/test/assets/63759427/d0f1bb60-d6e3-4955-9d74-ac27fa69123c)

![image](https://github.com/CLAREISMO/test/assets/63759427/d65c7d74-f377-47de-9148-04d98b3680a7)


**2. apply() method**: The function you pass to map() should expect a single value from the Series (a point value, in the above example), and return a transformed version of that value. map() returns a new Series where all the values have been transformed by your function.
apply() is the equivalent method if we want to transform a whole DataFrame by calling a custom method on each row.

![image](https://github.com/CLAREISMO/test/assets/63759427/213db147-bf27-4851-a4d1-4f9f4d3129dd)

![image](https://github.com/CLAREISMO/test/assets/63759427/e158d6a9-bea9-4838-81f7-467ca397d445)

![image](https://github.com/CLAREISMO/test/assets/63759427/f4f413db-211b-45da-884b-f7e11689f6c8)









































































































































































