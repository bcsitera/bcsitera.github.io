# Cargoson Interface for Business Central User Guide

Cargoson Interface enables the following:
- Sending Transportation Orders (incl. Transportation Orders with Direct Booking option) from Business Central to Cargoson. Sending Transportation Orders is possible from Business Central Sales Quotes, Sales Orders, Posted Sales Shipments and Purchase orders.  
- Sending Transportation Price Requests from Business Central to Cargoson and applying the selection directly to the source documents. Sending Price Requests is possible from Business Central Sales Quotes, Sales Orders, Posted Sales Shipments and Purchase orders.
- See Data Exchange Log between Business Central and Cargoson.

## Contents
- [Cargoson Interface for Business Central User Guide](#cargoson-interface-for-business-central-user-guide)
  - [Contents](#contents)
  - [Cargoson App Installation](#cargoson-app-installation)
  - [Menu](#menu)
  - [How to setup](#how-to-setup)
    - [Setup API](#setup-api)
    - [Setup Package Types](#setup-package-types)
    - [Setup BC User for Cargoson](#setup-bc-user-for-cargoson)
    - [Setup Shipping Agents and Shipping Agent Services for Cargoson](#setup-shipping-agents-and-shipping-agent-services-for-cargoson)
  - [How to make transportation price requests from Cargoson](#how-to-make-transportation-price-requests-from-cargoson)
  - [How to send Transportation Orders to Cargoson](#how-to-send-transportation-orders-to-cargoson)
  - [How to check Cargoson Log entries](#how-to-check-cargoson-log-entries)

## Cargoson App Installation
Open **Extension Management** and check if extension named ‘Cargoson’ is installed. If not, please find and install it from AppSource or contact BCS Itera AS.

## Menu
Cargoson menu items can be found from all Business Central Role centers via search functionality. Actions can be run from related pages (see instructions below). 

## How to setup

### Setup API

Search for **Cargoson Setup** to open the Cargoson Setup page and fill the fields as following (mandatory fields marked with *):

|Field|Description|
|---|---|
|Service URL*|Cargoson Service URL given by Cargoson support person.|  
|Authentication Phrase*|Cargoson Authentication Phrase given by Cargoson support person.| 
|Default Line Description*|Specifies Cargoson transportation order default line description.|
|Default Package Code*|Specifies Cargoson transportation order line default Package Type.|
|Use Collection Location Code|If activated then Cargoson collection information is taken from Location card specified in sales document field **Collection Location Code**.|

  <br/>

### Setup Package Types

Search for **Package Types** to open the Package Types setup page and fill the fields as following (mandatory fields marked with *):

|Field|Description|
|---|---|
|Code*|Internal package code used in Business Central (may be the same as Cargoson Package Type code).|  
|Type*|Package Type code used in Cargoson queries. These codes must be mapped with Cargoson.| 
|Description|Package Type description (for internal use).|
|Length (cm)|Package Type Length (cm) which is taken to Cargoson Transportation Order lines.|
|Width (cm)|Package Type Length (cm) which is taken to Cargoson Transportation Order lines.|
|Calculate LDM|If marked then LDM is calculated to Cargoson Transportation Order lines automatically.|

  <br/>

![PackageTypes](1_package_types.png)

 <br/>

### Setup BC User for Cargoson

Search for **User Setup** to open the User Setup page and add necessary users and fill the fields as following (mandatory fields marked with *):

|Field|Description|
|---|---|
|Salespers./Purch. Code|User related salesperson code. Salesperson data is taken to Cargoson queries.|  
|E-Mail|User e-mail address. Data is used in Cargoson queries.| 
|Phone No.|User Phone Number. Data is used in Cargoson queries.|
|Cargoson Authentication Phrase|User based Cargoson Authentication Phrase given by Cargoson support. If defined in user level, it will be used in Cargoson queries instead of the one specified in Cargoson Setup table. It allows to differentiate Transportation Orders by users in Cargoson webpage.|

 <br/>

### Setup Shipping Agents and Shipping Agent Services for Cargoson

Search for **Shipping Agents** to open the Shipping Agents setup page and add necessary Shipping Agents and Shipping Agent Service Codes (these must be agreed with Cargoson): 

![ShippingAgents](2_shipping_agents.png)

 <br/>
 <br/>

## How to make transportation price requests from Cargoson
Price request from Cargoson can be initiated on the following Business Central documents:
- Sales Quotes, 
- Sales Orders, 
- Posted Sales Shipments, 
- Purchase orders

Process:
- Create Business Central document, e.g. Sales Order (process is the same with all prementioned source documents) 
- Initiate Cargoson price request query from the document header action  **Create Transport Order**  
- Cargoson Order Lines window will open:
![Cargoson Order Lines](3_cargoson_order_lines.png)
- Check transportation order data (mandatory fields marked with *):

|Field|Description|
|---|---|
|Header||
|Collection Date*|Transportation Order collection date.|  
|Delivery date|Transportation Order delivery date.|
|Shipping Agent Service|Transportation Order Shipping Agent Service Code.|
|Details||
|Collection Postcode*|Postcode has to be filled in Location card selected to source document.|  
|Collection Country*|Country code has to be filled in Location card selected to source document.|
|Delivery Postcode*|Ship-to postcode has to be filled in source document.|  
|Delivery Country*|Ship-to country has to be filled in source document.|
|Lines|User can add additional lines manually or modify existing ones if necessary.|
|Package Code*|Transportation Order Line package type.| 
|Quantity*|Transportation Order Line package quantity.|
|Weight (kg)*|Transportation Order Line package weight. Is filled automatically by items Gross weight sum from source document lines. If Gross weight has not been filled, Net weight is used instead.|
|Length (cm)|Transportation Order Line package length.|
|Width (cm)|Transportation Order Line package width.|
|Height (cm)|Transportation Order Line package height.|
|CBM|Transportation Order Line CBM.|
|LDM|Transportation Order line LDM.|
|Description|Transportation Order line description.|

- Press button **Cargoson Price Request** to send the query to Cargoson.
- Cargoson will reply instantly with price offers from different carriers:
![Cargoson Carrier Services](4_cargoson_carrier_services.png)
- Mark suitable line and press **OK** to select carrier service to the source document as Shipping Agent and Shipping Agent Service (it is needed for direct booking) or discard the selection by pressing **Cancel**.  

 <br/>
 <br/>

## How to send Transportation Orders to Cargoson

Transportation Order can be sent to Cargoson from the following Business Central documents:
- Sales Quotes, 
- Sales Orders, 
- Posted Sales Shipments, 
- Purchase orders

Process:
- Create Business Central document, e.g. Sales Order (process is the same with all prementioned source documents)
- On the document header click **Create Transport Order** to start Transportation Order sending process  
- Cargoson Order Lines window will open:
![Cargoson Order Lines](3_cargoson_order_lines.png)
- Check Transportation Order data (mandatory fields are marked with *):

|Field|Description|
|---|---|
|Header||
|Collection Date*|Transportation Order collection date. Field must be filled in with today's date or later otherwise Transportation Order cannot be sent to Cargoson.|  
|Delivery date|Transportation Order delivery date. This date is usually given by shipping agent, but it is possible to send it to Cargoson if necessary. Value must be equal on later from **Collection Date**.|
|Shipping Agent Service|Transportation Order Shipping Agent Service Code. Field must be filled with Shipping Agent Service Code if Transportation Order is sent to Cargoson with Direct Booking Option (it means that Carogoson will forward the order directly to Shipping Agent without user intervention in Cargoson's website).|
|Details||
|Collection Postcode*|Postcode has to be filled in Location card selected to source document.|  
|Collection Country*|Country code has to be filled in Location card selected to source document.|
|Delivery Postcode*|Ship-to postcode has to be filled in source document.|  
|Delivery Country*|Ship-to country has to be filled in source document.|
|Cargoson Delivery Comment|Additional delivery related information. (e.g., "Code to enter the gate is 1234"). Text can be added on related source document (excl. Posted Sales Shipment).|
|Cargoson Collection Comment|Additional collection related information. (e.g., "Code to enter the gate is 1234"). Text can be added on related source document (excl. Posted Sales Shipment).|
|Cargoson Customer Remark|Remarks to the customer. Text can be added on related source document (excl. Posted Sales Shipment).|
|Lines|User can add additional lines manually or modify existing ones if necessary.|
|Package Code*|Transportation Order Line package type.| 
|Quantity*|Transportation Order Line package quantity.|
|Weight (kg)*|Transportation Order Line package weight. Is filled automatically by items Gross weight sum from source document lines. If Gross weight has not been filled on item card, Net weight is used instead.|
|Length (cm)|Transportation Order Line package length.|
|Width (cm)|Transportation Order Line package width.|
|Height (cm)|Transportation Order Line package height.|
|CBM|Transportation Order Line CBM.|
|LDM|Transportation Order line LDM.|
|Description|Transportation Order line description.|

- Press button **Send to Cargoson** to send the Transportation Order to Cargoson. System checks if all mandatory fields have been filled with data (if not, corresponding message is displayed to the user).
- Press button **Send Directly to Shipping Agent** to send the Transportation Order to Cargoson with Direct Booking option (it means that Carogoson will forward the order directly to Shipping Agent without user intervention on Cargoson's website). System checks if all mandatory fields have been filled with data (if not, the corresponding message is displayed to the user). 
- Cargoson Order No. will be saved to source document field **Cargoson Order No.** indicating that Transportation Order related to this document has been sent to Cargoson. Clicking on the Cargoson Order No. opens related Cargoson log entry where you can open Cargoson website with related Transportation Order, open related package label or open related package tracking website (for details see next chapter **How to check Cargoson Log entries**).
- Transportation Order is listed on Cargoson website (depending on the sending option used **New** or **Booked**):
![Cargoson Website](6_cargoson_website.png)

 <br/>
 <br/>

## How to check Cargoson Log entries
Transportation order related query responses between Business Central and Cargoson are saved to Cargoson Log entries table. Search for **Cargoson Log Entries** to open the Cargoson Log entries page:
![Cargoson Log Entries](8_cargoson_log_entries.png)

|Field|Description|
|---|---|
|Document Type|Document type from which the query was sent.|
|Document No.|Document number from which the query was sent.|  
|Cargoson Order No.|Related Cargoson Order number. Field acts as a link and clicking on it opens Cargoson website with related Transportation Order.|
|Customer reference|Customer reference number.|
|Pickup|Company name where the goods were collected.|
|Postal|Transportation Order collection Postcode.|  
|Country|Transportation Order collection Country.|
|Delivery|Company name where the goods were delivered.|  
|Postal|Transportation Order Delivery Postcode.|  
|Country|Transportation Order Delivery Country.|
|Collection date|Transportation Order Collection Date.| 
|Delivery date|Transportation Order Delivery date.|
|Carrier Service ID|Transportation Order Service ID. Indicates that Transportation Order was sent to Cargoson with Direct Booking option.|
|Carrier Service Description|Transportation Order Service ID description from Business Central.|
|Incoterms Code|Incoterms code related Transportation Order.|
|Label link|Package label link. Field acts as link and clicking on it opens related package label.|
|Tracking ID link|Package tracking link. Field acts as s link and clicking on it opens related package tracking website.|
|Entry No.|Log Entry unique number.|
