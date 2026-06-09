
# RAP Basics

In this part of the lecture we will use (_selected_) slides from the course **Building Transactional Apps with the ABAP RESTful Application Programming Model (S4D437)**

For the hands-part we will **NOT** work on the tasks listed in S4D437, but we will use the tutorial group [Build an SAP Fiori elements App Using the ABAP RESTful Application Programming Model (RAP) – Beginner RAP100](https://developers.sap.com/group.abap-build-fiori-element-rap.html) instead.  

> 🔔Hint:   
> The lecturer should import the solution package of this hands-on beforehand. It can then be found in package **ZRAP100_SOL**.

---

## Generate UI Service

> As in the last hands-on part of the course **Learning Basic ABAP Programming** we again generate a simple RAP BO based on one table from scratch.

To start with just follow the steps to generate a starter app

Hands-on RAP100 ⌨️: [Create Database Table and Generate UI Service](https://developers.sap.com/tutorials/abap-environment-rap100-generate-ui-service.html)

---

## Explain Draft

[Understanding the Draft Concept](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/understanding-the-draft-concept)

Slides of the following sections:
- Draft Motivation  
- Draft Tables  

Demo:  

- Edit an entry
  - Show content of draft table --> changed entry is in draft table
  - Show content of active table --> no changes visible
- Save the changes
  - Show content of draft table again --> it is empty now
  - Show content of active table again --> it now shows the changed data  

## Enhance the UI

### Working with pictures 

A RAP Business Object supports basic handling of smaller pictures so that they can uploaded in your Fiori Elements UI without the need to implement frontend coding.

Hands-on ⌨️: [Enhance the Business Object Data Model and Enable OData Streams](https://developers.sap.com/group.abap-build-fiori-element-rap.html)

### Add Google Like Search  

Using the annotation ``@Search.searchable: true`` and other `@Seach` annotations a Google Like Search is being added to the RAP BO

### Add Text

Using associations and appropriate annotations texts such as the name of a customer can be added to the customer id.

---

## Validations

[Lecture S4D437](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-input-checks-using-validations)

We do not have to implement all validations since a validation has already been implemented in the ABAP Basics part.

Hands-on ⌨️: [Enhance the Business Object Behavior With Validations](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-input-checks-using-validations)

---

## Numbering & Determinations

### Slides

[Setting Values Using Numbering and Determinations](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/setting-values-using-numbering-and-determinations)

Diagram that depicts the **Save Sequence Runtime** 🪄 :[Save sequence in SAP Online Help](https://help.sap.com/docs/abap-cloud/abap-rap/save-sequence-runtime?locale=en-US)

### Hands On

In the following exercise *internal early numbering* is added to the behavior of our RAP business object

Hands-on ⌨️: [RAP 100 - Enhance the Business Object Behavior With Unmanaged Internal Numbering](https://developers.sap.com/tutorials/abap-environment-rap100-early-numbering.html)



Hands-on ⌨️: [Enhance the Business Object Behavior With Determinations](https://developers.sap.com/tutorials/abap-environment-rap100-determination.html)

---

# RAP100 Intermediate

---

## Actions

Lecture

[Defining Actions and Messages](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/defining-actions-and-messages)

Implementation - RAP100

[Enhance the Business Object Behavior With Instance Action](https://developers.sap.com/tutorials/abap-environment-rap100-instance-action.html)

## Dynamic Feature Control 

[Implementing Dynamic Feature Control](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-dynamic-feature-control)



[Enhance the Business Object Behavior With Dynamic Feature Control](https://developers.sap.com/tutorials/abap-environment-rap100-dynamic-feature-control.html)

---


# Composite RAP BO's 

## Slides

[Defining Composite Business Objects](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/defining-composite-business-objects)


## Hands-On 

1. Demo of Exercise 1 of RAP200 (Create a RAP BO (Header/Item) manually using 2 structures as templates)
2. Run Exericse 1 of RAP 200 yourself
https://github.com/SAP-samples/abap-platform-rap200/blob/main/exercises/ex01/README.md
   and check the generated code (tables, cds views, behavior defintion)


3. Demo of Exericse 1 of RAP120 (Create nearly the same BO as in Exercise 1, this time using AI)
4. Run Exericse 1 of RAP 120 yourself
https://github.com/SAP-samples/abap-platform-rap120/blob/main/exercises/ex01/README.md
   and check the generated code (tables, cds views, behavior defintion)

- Skip exercise 2&3 of RAP120

5. Demo implementing a validation (showcase predict business logic)
6. Implement a validation using AI
   https://github.com/SAP-samples/abap-platform-rap120/tree/main/exercises/ex04




---



