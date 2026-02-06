# FleetGuru - User Guide
FleetGuru fleet management app solution for Microsoft Dynamics 365 Business Central.
  
If you have a business where you need to manage vehicles in FleetGuru software, this solution allows you to send _General Ledger Entries_ related to Vehicle Expenses to the FleetGuru fleet management app.

## Table of Contents

- [Setup](#setup)
- [Sending General Ledger Entries](#sending-general-ledger-entries)

## Setup

### Connection

On the page _FleetGuru Setup_ you need to setup the "API URL" and the "API Key" to your fleet management app.  

### Dimensions

On the page _FleetGuru Setup_ you need to specify, which _Dimension_ corresponds as your Vehicle Dimension. If needed, also _Deprartment_ and _Person Dimensions_ can be sent to the fleet management app. 

The first time the "Vehicle Dimension" field is filled, a popup window opens asking whether you wish to mark all _Dimension Values_ for the chosen _Vehicle Dimension_ to be sent to FleetGuru. 

Whichever _Dimension_ is set as "Vehicle Dimension" here, gets two new fields added in the _Dimension Value_ setup. "Send to FleetGuru" - specifies if the _G/L Entries_ conataining this _Dimension Value_ are sent to FleetGuru or not. "Vehicle Reg. No." - should be used in case _Dimension Value Code_ is not vehicle registration number.

### Expenses

With the field "Costs G/L Account Filter" you can specify, which _G/L Accounts_ contain _G/L Entries_ related to vehicle expenses. "Last Sent G/L Entry No." is a so-called bookmark that keeps track of the most recent _G/L Entry_ that was sent to FleetGuru. If this field is empty, there is no need to worry - no _G/L Entries_ are sent twice. The process of checking for already sent entries just takes more time and can affect performance. 

If "Send Invoice PDF" is checked, the PDF file stored in the _Incoming Documents_ for the _Invoice Expense Entries_ is also sent to FleetGuru.

## Sending General Ledger Entries

You can send the _Vehicle Expense G/L Entries_ to FleetGuru manually on the _FleetGuru Setup_ page or create _Job Queue Entries_ that automate the sending of the _G/L Entries_.

## Contact information
For more information and pricing please contact BCS Itera:  
<a href="https://www.itera.ee/en/about-us/" target="_blank">https://www.itera.ee/en/about-us/</a>