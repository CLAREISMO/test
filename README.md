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























#############################################################################################


### **Sumary Function**

**describe() method:**









































































































































































