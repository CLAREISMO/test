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


**describe() method for numeric values:** The describe() method: returns a DataFrame with a statistical summary of the columns of the DataFrame df of the type. For numeric data (number) the mean, standard deviation, minimum, maximum, and quartiles are calculated. This method generates a high-level summary of the attributes of the given column. It is type-aware, meaning that its output changes based on the data type of the input. The output above only makes sense for numerical data.

Below we can see the describe() method applied to numeric data:


**describe() method for non-numeric values:** For non-numeric data (object) the number of values, the number of distinct values, the mode, and their frequency are calculated. If the type is not specified, only numeric columns are considered. 

Below we can see the describe() method applied to string data:

![image](https://github.com/CLAREISMO/test/assets/63759427/18f00235-934c-4d8e-93d7-1a1686846314)

![image](https://github.com/CLAREISMO/test/assets/63759427/d8af7196-77cf-4a3f-a812-dbdca59c5e75)

![image](https://github.com/CLAREISMO/test/assets/63759427/701f1d5a-be72-491b-af4e-ce54e634db77)































































































































