# test

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









#############################################################################################


### **Sumary Function**

**describe() method:**









































































































































































