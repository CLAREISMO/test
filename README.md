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



















