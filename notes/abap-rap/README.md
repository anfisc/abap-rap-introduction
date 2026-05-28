
# RAP Basics

In this part of the lecture we will use slides from the course

For the hands-part we will **NOT** work on the tasks listed in S4d437, but we will use the tutorial group [Build an SAP Fiori elements App Using the ABAP RESTful Application Programming Model (RAP) – Beginner RAP100](https://developers.sap.com/group.abap-build-fiori-element-rap.html) instead.  

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

Demo 
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

<details>
<summary>Click her to expand</summary>

Adjust the data model of the base RAP BO to enable the handling large objects (LOBs, aka OData stream) in your Fiori elements app. By doing that, you will give end-users the option to upload and download images from your Travel app.

The only things you will have to do in the RAP BO, is to specify the appropriate semantics annotations for the relevant fields: Attachment, MimeType, and FileName. You will also have to adjust the UI semantics in the CDS metadata Extension for the appearence in the Travel app.

</details>


### Add Google Like Search  

``@Search.searchable: true``

### Add Text

---

## Validations

We do not have to implement all valciations

[Lecture S4D437](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-input-checks-using-validations)


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

## Unit Tests - Optional

---



---

# Composite RAP BO's - Optional

## Slides

[Defining Composite Business Objects](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/defining-composite-business-objects)


## Hands-On 

Exercise: Run RAP200

## Slides

[Defining Compositions in OData UI Services](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/defining-compositions-in-odata-ui-services)

## Hands-On   

Exercise: Check the generated code in RAP200

---

# Optional - Call composite RAP BO 

[Implementing the Behavior of Composite Business Objects](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-the-behavior-of-composite-business-objects
)

Use the prepare action to run validations during draft

Use side effects for responsive UI's





# Composite BO's

