# test

## **2. CLASS: Indexing, Selecting & Assigning**

### **Introduction**

The data scientists do this dozens of times a day. You can, too!

Selecting specific values of a pandas DataFrame or Series to work on is an implicit step in almost any data operation you'll run, so one of the first things you need to learn in working with data in Python is how to go about selecting the data points relevant to you quickly and effectively.

### **Selecting data**
There are two core objects in pandas: the DataFrame and the Series.

**head() method**: The first way we as data scientists can display a maximum number of columns is with the method head(x) where x is the number of records we want to display.

![image](https://github.com/CLAREISMO/test/assets/63759427/a6ca679e-c60d-470c-a52a-7113ae6b82bb)

**pd.set_option() function**: This is a function in pandas that allows you to set specific options for the behavior of the library, such as the number of rows or columns to be displayed in the output.

![image](https://github.com/CLAREISMO/test/assets/63759427/ee8c1c18-ea9e-4588-89a0-cca650c23a78)

![image](https://github.com/CLAREISMO/test/assets/63759427/b7582614-b16d-4b6f-90dd-92a9ddba64db)

![image](https://github.com/CLAREISMO/test/assets/63759427/e7c08e26-588e-4e4d-8871-5dba1e97316b)


### **Native accessors**

Native Python objects provide good ways of indexing data. Pandas carry all of these over, which helps make it easy to start with.

In Python, we can access the property of an object by accessing it as an attribute. A book object, for example, might have a title property, which we can access by calling book.title. Columns in a Pandas DataFrame work in much the same way.

![image](https://github.com/CLAREISMO/test/assets/63759427/b23dd4af-1abf-4b87-b6b6-7715be263919)

Let's see a second example with the Sku column:

![image](https://github.com/CLAREISMO/test/assets/63759427/1e00ccb1-e145-4095-b1f5-42452efd0c9f)

Let's see a third example with the column Ajio MRP

![image](https://github.com/CLAREISMO/test/assets/63759427/3c266f16-ca09-4933-a1c1-403b856109b9)

If the attribute name has spaces in it, as in this case "Ajio MRP", we can't access it in this way because it will generate an error. We can access it by the column number or by the indexing operator ([]).

**the indexing ([]) operator**: If we have a Python dictionary, we can access its values using the indexing ([]) operator. We can do the same with columns in a DataFrame:

![image](https://github.com/CLAREISMO/test/assets/63759427/dbd26057-6837-446a-99e8-b0d1a65f05c3)

These are the two ways of selecting a specific Series out of a DataFrame. Neither of them is more or less syntactically valid than the other, but the indexing operator [] does have the advantage that it can handle column names with reserved characters in them (e.g. if we had a country providence column, reviews.country providence wouldn't work).

Doesn't a Pandas Series look kind of like a fancy dictionary? It pretty much is, so it's no surprise that to drill down to a single specific value, we need only use the indexing operator [] once more:

![image](https://github.com/CLAREISMO/test/assets/63759427/d90835ea-1667-4871-ada9-3939032fb73d)


### **Indexing in Pandas**

The indexing operator and attribute selection are nice because they work just like they do in the rest of the Python ecosystem. As a novice, this makes them easy to pick up and use. 
However, Pandas have their own accessor operators, loc and iloc. For more advanced operations, these are the ones you're supposed to be using.

**Index-based selection**

**iloc**: Pandas indexing works in one of two paradigms. The first is index-based selection: selecting data based on its numerical position in the data. iloc follows this paradigm.

To select the first row of data in a DataFrame, we may use the following:

![image](https://github.com/CLAREISMO/test/assets/63759427/29ff61b9-a3f5-4103-aa82-32d63abe794c)

![image](https://github.com/CLAREISMO/test/assets/63759427/b72aa2ad-7d68-45d0-b239-4a214924afa9)

+ **Both loc and iloc are row-first, and column-second. This is the opposite of what we do in native Python, which is column-first, row-second. This means that it's marginally easier to retrieve rows, and marginally harder to get retrieve columns.** 


+ To get a column with iloc, we can do the following:

![image](https://github.com/CLAREISMO/test/assets/63759427/4497b583-5196-4fa9-853b-490baa735420)

![image](https://github.com/CLAREISMO/test/assets/63759427/38c34db6-998e-4277-ac5b-079daa7d6f55)

On its own, the (:) operator, which also comes from native Python, means "everything". When combined with other selectors, however, it can be used to indicate a range of values. 

+ For example, to select the first, second, and third rows of the first column, we would have to:

![image](https://github.com/CLAREISMO/test/assets/63759427/67d8d95d-d6a3-4796-9a91-a8ac64bfcfc4)

+ If we want to select the second and third row of column 0, we have to:

![image](https://github.com/CLAREISMO/test/assets/63759427/7fc2842c-1a97-433c-8409-9d797955b5c8)

+ It's also possible to pass a list:

![image](https://github.com/CLAREISMO/test/assets/63759427/56d50fdd-7372-4993-a972-60f449170de7)


Finally, it's worth knowing that negative numbers can be used in selection. This will start counting forwards from the end of the values. So for example here are the last five elements of the dataset.

![image](https://github.com/CLAREISMO/test/assets/63759427/f6ab155f-cc17-49cc-8ec8-1266e580a93e)

**Label-based selection**

**loc**: The second paradigm for attribute selection is the one followed by the loc operator: label-based selection. In this paradigm, it's the data index value, not its position, that matters.

For example, to get the first entry in reviews, we would now do the following:

![image](https://github.com/CLAREISMO/test/assets/63759427/33b03190-3814-4b31-8803-c064286cefda)

![image](https://github.com/CLAREISMO/test/assets/63759427/396fd907-bc5c-4076-988a-92b9dd2c0899)

+ **iloc is conceptually simpler than loc because it ignores the dataset's indices. When we use iloc we treat the dataset like a big matrix (a list of lists), one that we have to index by position.**

+ **loc, by contrast, uses the information in the indices to do its work. Since your dataset usually has meaningful indices, it's usually easier to do things using loc instead. For example, here's one operation that's much easier using loc:**

![image](https://github.com/CLAREISMO/test/assets/63759427/2746fee0-7409-4dbc-978a-6d695a221a9f)

### **Choosing between loc and iloc**

When choosing or transitioning between loc and iloc, there is one "gotcha" worth keeping in mind, which is that the two methods use slightly different indexing schemes.

+ **iloc uses the Python stdlib indexing scheme, where the first element of the range is included and the last one excluded. So 0:10 will select entries 0,...,9.**

+ **loc, meanwhile, indexes inclusively. So 0:10 will select entries 0,...,10.**

Why the change? Remember that loc can index any stdlib type: strings, for example. If we have a DataFrame with index values Apples, ..., Potatoes, ..., and we want to select "all the alphabetical fruit choices between Apples and Potatoes", then it's a lot more convenient to index df.loc['Apples':'Potatoes'] than it is to index something like df.loc['Apples', 'Potatoes'] (t coming after s in the alphabet).

**This is particularly confusing when the DataFrame index is a simple numerical list, e.g. 0,...,1000. In this case df.iloc[0:1000] will return 1000 entries, while df.loc[0:1000] return 1001 of them! To get 1000 elements using loc, you will need to go one lower and ask for df.loc[0:999]. Otherwise, the semantics of using loc are the same as those for iloc.**


### **Manipulating the index**

Label-based selection derives its power from the labels in the index. Critically, the index we use is not immutable. We can manipulate the index in any way we see fit.

The set_index() method can be used to do the job. Here is what happens when we set_index to the title field:

![image](https://github.com/CLAREISMO/test/assets/63759427/efda0bcf-75ea-45ca-80bb-8598049a8878)

![image](https://github.com/CLAREISMO/test/assets/63759427/17db00a1-c3ef-470a-9804-b6580412022c)

This is useful if you can come up with an index for the dataset which is better than the current one


### **Link code Conditional selection**

So far we've been indexing various strides of data, using the structural properties of the DataFrame itself. To do interesting things with the data, however, we often need to ask questions based on conditions.

Let's see the following example:

![image](https://github.com/CLAREISMO/test/assets/63759427/d0e2bd34-37b4-4678-b6a5-c19a2253ad65)

![image](https://github.com/CLAREISMO/test/assets/63759427/208d70fc-ac5a-4fc7-81f6-2c0cde6d3ec4)

![image](https://github.com/CLAREISMO/test/assets/63759427/70a7fc9e-f638-4c58-901d-cf7e892e10de)

This operation produced a Series of True/False booleans based on the condition of each record. This result can then be used inside of loc to select the 
relevant data:

+ We can know the percentage of occurrence of a value:

![image](https://github.com/CLAREISMO/test/assets/63759427/410f6a20-30e4-4b9f-bf60-050d3965cf0c)

![image](https://github.com/CLAREISMO/test/assets/63759427/d0f22c8a-b834-4b96-a23b-fcc8d70a3c87)

![image](https://github.com/CLAREISMO/test/assets/63759427/2631d85f-076e-429f-bd13-361481375ba9)


+ We can use the ampersand (&) to join two queries: in this case, we want to return the records of the DataFrame that meet the following conditions at the same time:  TP =="538" & Weight <= 0.4

![image](https://github.com/CLAREISMO/test/assets/63759427/914d38ca-cd3a-459d-8c62-a898d693a272)

![image](https://github.com/CLAREISMO/test/assets/63759427/0193d308-2cc0-4d17-9bed-8a4300e5fa45)

![image](https://github.com/CLAREISMO/test/assets/63759427/7e721f49-9cc5-4503-8135-988352413944)


+ We can also use the conditional pipe (|) to join two queries: in this case, we want to return the records of the DataFrame that meet one of the two requested queries, they only have to meet one condition TP =="538" | Weight <= 0.4. For this, we use a pipe (|):

![image](https://github.com/CLAREISMO/test/assets/63759427/4aa13e35-16c3-48cf-8a4c-0215135fd488)

**We can conclude that the ampersand(&) operator behaves as an AND conditional while the pipe (|) operator behaves as an OR conditional.**


### **Pandas  built-in conditional selectors**

Pandas come with a few built-in conditional selectors, two of which we will highlight here. The first is isin. isin lets you select data whose value "is in" a list of values.


**isin method**: 

![image](https://github.com/CLAREISMO/test/assets/63759427/def24936-ab29-48d3-893d-0fd3fac1e7fd)

+ We can request several objects that meet the given condition through the isin method!

![image](https://github.com/CLAREISMO/test/assets/63759427/add5a376-ac4f-4653-b18b-106d8d13e659)

+ We can also apply the loc selector together with the method isin:

![image](https://github.com/CLAREISMO/test/assets/63759427/d20951b8-79cd-4f41-9f2c-523e53e8645d)


+ It is also possible to filter the data given a condition:

![image](https://github.com/CLAREISMO/test/assets/63759427/2ba2c723-6380-463d-91ee-4cbd33fe5639)


**isnull and notnull methods**

The second Pandas built-in conditional selector is isnull (and its companion notnull). These methods let you highlight values that are (or are not) empty (NaN). 


**isnull method**

Return the null records from our DataFrame or from the given DataFrame selection.

![image](https://github.com/CLAREISMO/test/assets/63759427/d4ff87eb-6363-487f-8edf-3e5f2a64aec2)



**notnull method**

Returns the notnull records, that is to say, that do not have a null value from our DataFrame or from the given DataFrame selection.

![image](https://github.com/CLAREISMO/test/assets/63759427/f60ce9b1-8496-4f33-a717-a70a5204e252)


**Null Register check in DF**

We can check for the existence of null records in our DataFrame:
![image](https://github.com/CLAREISMO/test/assets/63759427/ffc97f76-51cc-4dfa-9f04-9354e8a7ca0d)



**Not-Null with Notna Register check in DF**
Also, we can check for the existence of not-null records in our DataFrame with notna function:

![image](https://github.com/CLAREISMO/test/assets/63759427/63de664b-2064-44eb-9cdd-25109bedf98b)


### **Assigning data**

Going the other way, assigning data to a DataFrame is easy. You can assign either a constant value:

![image](https://github.com/CLAREISMO/test/assets/63759427/048fca6d-846f-446f-8603-f86c1cb53a79)


![image](https://github.com/CLAREISMO/test/assets/63759427/95d24d4c-d8e0-46a0-84f9-eb78d02142cc)


#* Iterable data Assignment 

We generate a new column index_backwards which returns an inverted index starting with the last value of the index of the original DataFrame and ending with the first record of the index of the original DataFrame.

![image](https://github.com/CLAREISMO/test/assets/63759427/84b778fc-4843-4c9c-a1c3-8a01fb567e50)

When printing the DataFrame again we get an additional index_backwards column. Therefore the value of the columns increases to 17:

![image](https://github.com/CLAREISMO/test/assets/63759427/5143fa61-c669-43ee-a2f3-a2948ee065fa)

















































































































