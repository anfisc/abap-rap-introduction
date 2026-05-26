
# RAP Basics

---

## Generate UI Service

To start with just follow the steps to generate a starter app

[Create Database Table and Generate UI Service](https://developers.sap.com/tutorials/abap-environment-rap100-generate-ui-service.html)

---

## Enhance the UI

### Working with pictures

A RAP Business Object supports basic handling of smaller pictures so that they can uploaded in your Fiori Elements UI without the need to implement frontend coding.

[Enhance the Business Object Data Model and Enable OData Streams](https://developers.sap.com/group.abap-build-fiori-element-rap.html)

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


[Enhance the Business Object Behavior With Validations](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-input-checks-using-validations)

---

## Numbering & Determinations

### Slides

[Setting Values Using Numbering and Determinations](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/setting-values-using-numbering-and-determinations)

Hint for save sequence

https://help.sap.com/docs/abap-cloud/abap-rap/save-sequence-runtime?locale=en-US

### Hands On

In the following exercise *internal early numbering* is added to the behavior of our RAP business object

[RAP 100 - Enhance the Business Object Behavior With Unmanaged Internal Numbering](https://developers.sap.com/tutorials/abap-environment-rap100-early-numbering.html)

---

# RAP100 Intermediate

---

## Feture control

Lecture

[Implementing Dynamic Feature Control](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/implementing-dynamic-feature-control)

Implementation - RAP100

[Enhance the Business Object Behavior With Instance Action](https://developers.sap.com/tutorials/abap-environment-rap100-instance-action.html)

[Enhance the Business Object Behavior With Dynamic Feature Control
](https://developers.sap.com/tutorials/abap-environment-rap100-dynamic-feature-control.html)

---

## Unit Tests - Optional

---

# How the to handle Draft

Use the prepare action to run validations during draft

Use side effects for responsive UI's


[Understanding the Draft Concept](https://learning.sap.com/courses/building-transactional-apps-with-the-abap-restful-application-programming-model/understanding-the-draft-concept)

---

# Composite RAP BO's

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






# Composite BO's

