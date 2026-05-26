# Preparation steps to be performed by the lecturer 

## Work on the pre-requisites as the participants

- install ADT
- install abapGIT Plugin

---

## Import of RAP100 solution into training system

For this step you have to have installed the **abapGIT** plugin as described in the following tutorial [Install the abapGit Plugin](https://developers.sap.com/tutorials/abap-install-abapgit-plugin..html) 

1. Create a package **ZRAP100_SOL** with **ZLOCAL** as the super package
2. Link the package with the following repository `https://github.com/SAP-samples/abap-platform-rap100`  
3. Import the content of the `main` branch
4. Activate all changes 
5. Run the class `zcl_rap100_gen_data_sol` via **F9**
6. Publish the service binding `ZRAP100_UI_TRAVEL_O4_SOL` locally
7. Check service using the ADT preview [ADT link](adt://L02/sap/bc/adt/businessservices/bindings/zrap100_ui_travel_o4_sol?version=active)
 

----



