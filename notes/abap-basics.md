# ABAP Basics

The first part of the lecture basically makes use of the course [Learning Basic ABAP Programming](https://help.sap.com/docs/abap-cloud/abap-rap/save-sequence-runtime) which is part of the learning offering on https://learning.sap.com.

In the following the different units are listed and where applicable it is described where a deviation from the standard lecture has been choosen.

---

## UNIT 1: Getting Started

When creating your package please use the following naming convention

ZS4D400_<abreviation_for_university>_## 

(So for **SRH University** on the campus **Stuttgart** I suggested to use ZS4D400_SRH_ST_##)

that means, please add the additional suffix (e.g. `_SRH_ST`) in front of your personal suffix **`_##`**.

This would result in the following suggestion for a package name `ZS4D400_SRH_ST_##`. 

---
## UNIT 2: Applying Basic Techniques and Concepts

---

## UNIT 3: Working with Local Classes

Here instead of local classes a global class is being used. 


### Lesson - Defining a local class  

(We work with global classes instead !)

Change of **Task 2**: Define a Local Class  

- Define a second **global** class **`zcl_connection_##*`** (as you did in task 1) instead of a local class **`lcl_connection`**  
- Use code snippets provided in the script for **`lcl_connection`** and replace **`lcl_connection`** by **`zcl_connection_##`** where needed

### Lesson - Creating Instances of a Class

In Task 2: Create an Instance change  
 `DATA connection TYPE REF TO lcl_connection.`
To  
 `DATA connection TYPE REF TO zcl_connection_##.`

In Exercise 9 declare a reference variable (suggested name: connection) and use your global class `ZCL_CONNECTION_##` as type (instead of a local class `lcl_connection`).   

---

### Lesson - Using Encapsulation to Ensure Consistency

In this lesson we again have to perform changes for the tasks being desribed. Instead of using the local class `lcl_connection` we will use the global class  `zcl_connection_##` that has been created beforehand.

**Task 1 – Changes**

You can use the code of the local class `lcl_connection` in the global class `/lrn/cl_s4d400_cls_methods` and replace the definition section and implementation section of your global class `zcl_connection_##` if if you have not performed the lesson before.   
Otherwise continue with Task 2, make the attributes private and apply the changes to your global class `zcl_connection_##`.

## Unit 4: Reading Data from the Database  

Where the script refers to the local class `lcl_connection`, please use instead with your global class `ZCL_CONNECTION_##` 

## Unit 5: Working with Structured Data Objects
## Unit 6: Working with Complex Internal Tables
## Unit 7: Implementing Database Updates Using Business Objects
Exercise can be done as a home work  
## Unit 8: Describing the ABAP RESTful Application Programming Model
Exercise can be done as a homework   



Now continue with [RAP Programming](./abap-rap.md).





