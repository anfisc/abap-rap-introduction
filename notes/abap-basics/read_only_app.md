# How to create a read-only "report"

In this demo it is shown how to create a **_read-only report_**   

1. based on the R-view of the sample app that you created in **Unit 8** of the course [Learning Basic ABAP Programming](https://learning.sap.com/courses/basic-abap-programming).  

and

2. based on an existing table.

# Create a read-only view on top of your business object

<details>
<summary>Click to expand!</summary>

## Create a CDS view

1. Right-click on the view entity `ZR_S4D400_AFI_RAP` and select **New Data Definition**. 

    ![](images/read_only_report_100.png) 

2. Enter the following values:

   | Field | Value |
   |---|---|
   | Name              | **`ZC_S4D400_###_READONLY`** |
   | Description       | **`Read-only report`** |
   | Referenced Object | **`ZR_S4D400_###_RAP`** |   
   | Package           | **`<your_package>`** |

    Press **Next >**   

3. Click **Next >** to continue, select a transport request if requested, click **Next >** to continue, select the template **`DefineViewEntity`** under **View (creations)** in the tree, and confirm with **Finish**.

   ![](images/demo_report_020.png)    

4. The source code will show an error because the annotation of **CurrencyCode** is missing.

```ABAP
@AbapCatalog.viewEnhancementCategory: [#NONE]
@AccessControl.authorizationCheck: #NOT_REQUIRED
@EndUserText.label: 'Read-only UI'
@Metadata.ignorePropagatedAnnotations: true
define view entity ZC_S4D400_###_READONLY
  as select from ZR_S4D400_###_RAP
{
  key CarrierID,
  key ConnectionID,
  key FlightDate,
      @Semantics.amount.currencyCode: 'CurrencyCode'
      Price,
      CurrencyCode,
      PlaneTypeID,
      LocalCreatedBy,
      LocalCreatedAt,
      LocalLastChangedBy,
      LocalLastChangedAt,
      LastChangedAt
}


```

5. Add a `where` clause to your code so that only connections are selected with a price that exceeds 1000 EUR.

```ABAP
@AbapCatalog.viewEnhancementCategory: [#NONE]
@AccessControl.authorizationCheck: #NOT_REQUIRED
@EndUserText.label: 'Read-only UI'
@Metadata.ignorePropagatedAnnotations: true
define view entity ZC_S4D400_###_READONLY
  as select from ZR_S4D400_###_RAP
{
  key CarrierID,
  key ConnectionID,
  key FlightDate,
      @Semantics.amount.currencyCode: 'CurrencyCode'
      Price,
      CurrencyCode,
      PlaneTypeID,
      LocalCreatedBy,
      LocalCreatedAt,
      LocalLastChangedBy,
      LocalLastChangedAt,
      LastChangedAt
}
where
  Price > 10

```

6. Add UI and Search annotations



5. Save and activate your coding

## Create a service definition

1. Right-click on the package and select **New** > **Other ABAP Repository Object** > **Service Definition**.

2. Enter the following values:

   | Field | Value |
   |---|---|
   | Name              | **`ZUI_S4D400_###_RO_O4`** |
   | Description       | **`Read-only report`** |
   | Source Type        | **`Definition`** |
   | Referenced Object | **`ZC_S4D400_###_READONLY`** |   
   | Package           | **`<your_package>`** |

Press Next several times and then finish

3. Add an alias `FlightsAfterToday` so that the source code now reads

```ABAP
@EndUserText.label: 'Demo report'
define service ZUI_S4D400_###_RO_O4
{
    expose ZC_S4D400_###_READONLY as ExpensiveFlights;
    
}

```
   

4. Save and Activate your changes.


## Create a service binding

1. Right click on the service definition that you have just created and select **New Service Binding**.

2. Enter the following values:

   | Field | Value |
   |---|---|
   | Name              | **`ZUI_S4D400_###_RO_O4`** |
   | Description       | **`Read-Only report`** |
   | Binding Type        | **`OData V4 - UI`** |
   | Service Definition | **`ZUI_S4D400_###_RO_O4`**|
   | Package           | **`<your_package>`** |

   and press **Next** and then **Finish**

 3. Activate the object   

 4. Press **Publish Locally**

 5. Test the service

    You will get a report that shows the flights after the current date and you are able to search for the airline name, e.g. `AA`.    

    ![](images/read_only_report_110.png)


</details>

# Create a readonly view on top of a table

<details>
<summary>Click to expand!</summary>

## Create a CDS view

1. Right-click on the package and select **New** > **Other ABAP Repository Object** > **Core Data Services** > **Data Definition**.  
    

2. Enter the following values:

   | Field | Value |
   |---|---|
   | Name              | **`Z_Flight_Aftertoday_###`** |
   | Description       | **`Demo report`** |
   | Referenced Object | **`/dmo/flight`** |   
   | Package           | **`<your_package>`** |

   > Hint:  
   > You can also use the C-view of a RAP BO as a data source to create a read-only view from your data and analyze it.  

   ![](images/demo_report_010.png) 

4. Click **Next >** to continue, select a transport request if requested, click **Next >** to continue, select the template **`DefineViewEntity`** under **View (creations)** in the tree, and confirm with **Finish**.

   ![](images/demo_report_020.png)

5. Replace the code with the following coding

```ABAP
@EndUserText.label: 'Flights with Flight Date Later Than Two Days From Today'
@Search.searchable: true

define view entity Z_Flight_Aftertoday_###

  as select from /dmo/flight as Flight

  association [1] to /DMO/I_Carrier as _Airline on $projection.AirlineID = _Airline.AirlineID


{
      @UI.lineItem: [ { position: 10, label: 'Airline'} ]
      @Search.defaultSearchElement: true
      @Search.fuzzinessThreshold: 0.7
      @ObjectModel.text.association: '_Airline'
  key Flight.carrier_id     as AirlineID,

      @UI.lineItem: [ { position: 20, label: 'Connection Number' } ]
  key Flight.connection_id  as ConnectionID,

      @UI.lineItem: [ { position: 30, label: 'Flight Date' } ]
  key Flight.flight_date    as FlightDate,

      @UI.lineItem: [ { position: 40, label: 'Price' } ]
      @Semantics.amount.currencyCode: 'CurrencyCode'
      Flight.price          as Price,

      Flight.currency_code  as CurrencyCode,

      @UI.lineItem: [ { position: 50, label: 'Plane Type' } ]
      @Search.defaultSearchElement: true
      @Search.fuzzinessThreshold: 0.7
      Flight.plane_type_id  as PlaneType,

      @UI.lineItem: [ { position: 60, label: 'Maximum Seats' } ]
      Flight.seats_max      as MaximumSeats,

      @UI.lineItem: [ { position: 70, label: 'Occupied Seats' } ]
      Flight.seats_occupied as OccupiedSeats,

      /* Associations */
      _Airline
}
where
  Flight.flight_date > $session.user_date

```

5. Save and activate your coding

## Create a service definition

1. Right-click on the package and select **New** > **Other ABAP Repository Object** > **Service Definition**.

2. Enter the following values:

   | Field | Value |
   |---|---|
   | Name              | **`ZUI_Flight_Aftertoday_###`** |
   | Description       | **`Demo report`** |
   | Source Type        | **`Definition`** |
   | Referenced Object | **`Z_Flight_Aftertoday_###`** |   
   | Package           | **`<your_package>`** |

Press Next several times and then finish

3. Add an alias `FlightsAfterToday` so that the source code now reads

```ABAP
@EndUserText.label: 'Demo report'
define service ZUI_Flight_Aftertoday_###
{
    expose Z_FLIGHT_AFTER2DAYS_### as FlightsAfterToday;
    
}

```
   

4. Save and Activate your changes.


## Create a service binding

1. Right click on the service definition that you have just created and select **New Service Binding**.

2. Enter the following values:

   | Field | Value |
   |---|---|
   | Name              | **`ZUI_Flight_Aftertoday_###`** |
   | Description       | **`Demo report`** |
   | Binding Type        | **`OData V4 - UI`** |
   | Service Definition | **`ZUI_FLIGHT_AFTERTODAY_###`**|
   | Package           | **`<your_package>`** |

   and press **Next** and then **Finish**

 3. Activate the object

    ![](images/demo_report_030.png)

 4. Press **Publish Locally**

 5. Test the service

    You will get a report that shows the flights after the current date and you are able to search for the airline name, e.g. `AA`.    

    ![](images/demo_report_040.png)

</details>
