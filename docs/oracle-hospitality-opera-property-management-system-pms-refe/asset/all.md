![](Images/cover00493.jpeg)

Index of contents.

[Issuance of vouchers, Invoices and Ballots from Opera PMS](#part0001.xhtml__mknjnz17a400)

[Closing of Day or Audit process with Opera PMS](#part0001.xhtml__psaycmhdm02k)

[Configuration of Rate Strategy in Opera PMS](#part0002.xhtml__zassrom8s1tk)

[Credit Notes by Credit Bill in Opera PMS](#part0003.xhtml__d0mv4ynwhkbh)

[Rate Strategy Configuration and demonstration in Opera PMS](#part0004.xhtml__bz8kwthb0vsb)

[Creation of reports with Opera PMS and Oracle Reports Developer.](#part0005.xhtml__u3d4iyvv56z6)

[Opera PMS - Oracle Data Dictionary](#part0006.xhtml__kq9ys8pxq1cp)

[Design and creation of Daily Payments report from Opera PMS](#part0007.xhtml__erweu9tmqsi2)

[Creation of ForeCast and History report in Opera PMS](#part0008.xhtml__wnalj156ssdj)

[Creation of Trial Balance Details By Transactions Report in Opera PMS](#part0009.xhtml__y2mm43l7vhef)

[Room Status and Housekeeping Status in Opera PMS , Online web consultation from Smartphone](#part0010.xhtml__yf4ubz2jr7m8)

[Accounting Accounts assigned to Transaction Codes in Opera PMS](#part0011.xhtml__lfycchvtlig3)

[Change Room Type Room Type in Opera PMS](#part0012.xhtml__8qrakg3pc9zn)

[Querys SQL Oracle useful for administration in Opera PMS](#part0013.xhtml__rwegg4mtuxwj)

[Creation of physical Kardex valued in Material Controls Micros Fidelio](#part0014.xhtml__cjij7kcv4eos)

# Issuance of vouchers, Invoices and Ballots from Opera PMS

In order to issue a Ballot, we must verify that the client has the "Tax Type" field as a TICKET in the Client's profile.

enter the menu "Front Desk" option "In House Guests" to list all clients who are staying at the Hotel.

![](Images/image00344.jpeg)

On the “In House Guest” screen, select the client for whom you want to verify the Tax Type of their profile and select the radio button “Profile”.

![](Images/image00345.jpeg)

The “Individual Profile” screen shows the most important customer data. on this screen select the option button “More Fields”.

![](Images/image00346.jpeg)

On the "More Fields" screen make sure the Tax Type field is marked with the TICKET option and select the OK option button.

![](Images/image00347.jpeg)

Upon returning to the “Individual Profile” screen, select the “Save” option button to save the changes made, then click on the Ok and Close button.

With this we make sure that the client has the Tax Type as TICKET, which will allow us to generate the receipt of payment type Ticket.

Enter the menu "Cashiering" option "Billing" to show the clients that are hosted for which it is possible to generate a proof of payment for any concept of stay, consumption or services.

Previously, the Login screen will be shown to request the ATM access credentials.

![](Images/image00348.jpeg)

On the In “House Guest Search” screen, filter the “Due Outs” records, which are the records of clients pending departure, clients who are staying and consume the services that the Hotel offers to which a payment receipt must be generated. , in this case a Ballot.

Select the "Due Outs" option and click on the "Search" option button.

![](Images/image00349.jpeg)

On the "House Guest Search" screen, select the customer record for which you want to generate the payment slip and then click on the "Select" button. ”, The“ Billing ”screen will be displayed.

![](Images/image00350.jpeg)

On the "Billing" screen the customer's account details are displayed. It is important to indicate that on this screen you can have up to 8 Windows, windows that will allow us to classify the customer's accounts and generate receipts for each Window.

Let's observe that Window (02) has an account of 140.80 USD that is not yet paid and that Window (03) has an account of 32.00 USD that is paid through the VISA payment method.

Select Windows (02) and click on the option button "Check Out", the "Payment" screen will be displayed.

![](Images/image00351.jpeg)

In the "Payment" screen, select the option "Payment Code" to "Cash Dollars", the Currency option to USD, in the Amount field indicate the amount 140.80 and in the Reference field indicate a description of the account, then click on the option button Post with this the payment is loaded into the system and the account is closed.

![](Images/image00352.jpeg)

On the next screen PoPup indicate No, to send the receipt to the digital tax document issuer program in your Country (or Electronic Invoicing of the Central Tax Administration)

![](Images/image00353.jpeg)  ![](Images/image00354.jpeg)

This process of sending the voucher data to the central tax administration of your country, printing the voucher with the data of the voucher number, QR code.

At the end of the process, a record for -140.80 (negative) is shown in the Account Window, indicating the closing of the account.

![](Images/image00355.jpeg)

# Closing of Day Process or Audit with Opera PMS

The closing of day allows updating the business date (Business Date) to the current operation date, in addition the closing process is very important for the generation of hotel management reports.

Enter the "End of Day" option menu and select the "Night Audit" menu.

![](Images/image00356.jpeg)

The "End of Day Login" form will be displayed and select the "Business Date" that we want to close.

![](Images/image00357.jpeg)

The "End of Day Routine" screen will be displayed, which will validate the conclusion of the processes that allow the proper closing of the day.

![](Images/image00358.jpeg)

Click the OK button and then click the Start button.

Opera shows you the pending arrivals or reservations for Check In not yet registered, which must be registered, this also alerts us about the status of pending arrivals.

![](Images/image00359.jpeg)

To continue with the closing of the day, it is important to check in all arrivals on the date that is closing in order to continue with the process.

After assigning the Room and Rate, click on the Check In option button.

If the Check In is successful, the registration must leave the check-in pending list. Continue with this process until the check in pending registration tray is left without records.

During the validation of the pending Check Out records, the "Guests At Home" screen is displayed, for which the corresponding Check Out must be generated before continuing with the closing process.

![](Images/image00360.jpeg)

Before proceeding with the Check out, it is important to configure the printtasks necessary for printing the CheckOut.

![](Images/image00361.jpeg)

Log in with the supervisor role, select the Configuration option, in the Configuration screen, select the Workstation menu option.

![](Images/image00362.jpeg)

Select the WorkStatons corresponding to the current work pc, which is usually highlighted in blue.

![](Images/image00363.jpeg)

Click on the Print Tasks option button to display the Print Task screen.

![](Images/image00364.jpeg)

Within this screen, click the New button.

![](Images/image00365.jpeg)

If the Printer Task is not displayed on the screen, it must be registered on the Printers screen, select the option menu Printers, the screen will be displayed, and click on New

![](Images/image00366.jpeg)

Create the required print task, then in the WorkStation add the necessary PrintTask.

![](Images/image00367.jpeg)

Opera will begin to close the day and complete all pending operations for a proper close.

![](Images/image00368.jpeg)

The closing process also prints the pending reports of the day's operations.

![](Images/image00369.jpeg)

At the end of the closing process for the day, the printing of the final report is requested.

![](Images/image00370.jpeg)

# Configuration of Rate Strategy in Opera PMS

The rate strategy allows us to control the price restrictions (discounts and surcharges) that we wish to apply to room reservations according to the occupancy or availability of the hotel rooms.

For example, if the rooms of a certain category are sold with a discount until they exceed 10% of occupancy, once this percentage of occupancy is exceeded, the discount is withdrawn and the remaining 90% is sold without any discount.

We wish this restriction to apply for check-ins from 05/01/2019 to 05/31/2019, we wish to control the restrictions during the month of March and the month of April, that is, from 03/01/2019 to 04/30/2019.

In Opera we enter the configuration module.

![](Images/image00371.jpeg)

Then we select the Rate Strategy option.

![](Images/image00372.jpeg)

On the Rate Strategy screen we will define the rate strategy according to the established conditions.

You should always define two strategy registers the rate strategy and its counterpart. In other words, the rates are defined for reservations greater than 10% occupancy and the registration of rate strategies for reservations less than 10% occupancy.

Rate strategy for a specific pricing code called CRESP.

![](Images/image00373.jpeg)

For check-ins or arrivals from May 1, 2019 to May 31, 2019

![](Images/image00374.jpeg)

whose sales or reservations are made from March 1 to April 30, we also define its counterpart of the restriction

![](Images/image00375.jpeg)

therefore in the Rate screen Strategy must have 2 records per rate restriction.

![](Images/image00376.jpeg)

Then we test the defined rate strategy at the time of booking.

# Credit Notes through Credit Bill in Opera PMS We will

make credit notes through CREDIT BILL, enter the Cashiering menu, Cashier Functions option The Cashier Functions

![](Images/image00377.jpeg)

form will be displayed

![](Images/image00378.jpeg)

Select the Folio History option the Flio History form will be displayed

![](Images/image00379.jpeg)

** Consider that only Credit Notes can be issued through CREDIT BILL to vouchers that have been issued one day in advance, otherwise Opera disables the Credit Bill option button, for example, as of today, March 12, only credit notes are allowed to be issued. credit through Credit Bill of vouchers issued until March 11.

** Another consideration to take into account is that the issuance of credit notes must correspond to the series category of the payment receipt, that is, if the series category is F010, credit notes must be issued with the F010 series. if the series category is B011, credit notes must be issued with the B011 series in that correlation. If this correlation does not occur, there is a risk that the central tax administration will reject the credit note issued.

** For this correlation to occur, it is very important that when issuing credit notes, the Tax Type field of the Client's Profile must be changed.

For example, for the issuance of credit notes for the invoice voucher of the client Liu, Fang

![](Images/image00380.jpeg)

Enter the Reservations Menu Profiles option, in the Profile Search screen find and select Client Profile.

![](Images/image00381.jpeg)

Click on the Edit option button to display the Individual Profile form with the customer's data,

![](Images/image00382.jpeg)

Select the More Fields option button to view the Tax Type options

![](Images/image00383.jpeg)

To properly generate the invoice credit note it is important to change the Tax Type of the Profile from the Client to INVOICE.

![](Images/image00384.jpeg)

After changing the Tax Type field, we proceed to generate the Credit Bill of the invoice from the Folio History screen.

![](Images/image00385.jpeg)

We will be asked for the credentials of the cashier, you

![](Images/image00386.jpeg)

must indicate the Marked Code and Source Code values ​​and then click on the Post option button.

![](Images/image00387.jpeg)

We post the credit note for the same value but negative.

![](Images/image00388.jpeg)

Consider that to carry out the CREDIT BILL, you must use the same market code and the same source that you used to make the reservation.

![](Images/image00389.jpeg)  ![](Images/image00390.jpeg)

# Rate Strategy Configuration and demo in Opera PMS

This guide configures pricing strategies and demonstrates the application of their restrictions.

1. USER PROFILES

Consider the following permissions for the reception and reservation profiles:

Reception Profile

Permissions for profiles whose users must respect the restrictions of the pricing strategies. This is applicable for cashier or receptionist users.

You must not have the following permissions:

RESERVATIONS \ OVERRIDE RATECODE

BLOCKS \ OVERRIDE BLOCK RATE RESTRICTIONS You

must have the following permissions:

RESERVATION \ RATE CODE CHANGE

Profile Reservations

Permissions for the profiles whose users can authorize the breaking of price strategy restrictions. This is applicable for supervisory users, senior tellers, or senior reservation staff.

You must have the following permissions:

RESERVATION \ OVERRIDE RATECODE

BLOCKS \ OVERRIDE BLOCK RATE RESTRICTIONS

RESERVATION \ RATE CODE CHANGE

2. SYSTEM PARAMETERS You

must indicate the following parameters in the "Application Settings" screen with the values ​​"Y".

Parameter

Value

RATES \ SET RATE CATEGORY RESTRICTIONS

AND

RATES \ SET RATE CODE RESTRICTIONS

AND

3. PRICE STRATEGY DEFINITION

To configure the pricing strategies, enter the “Configuration” main menu, the “Configuration” screen will be displayed. screen enter the “Rate Management” menu option, “Rate Strategy” option, the “Rate Strategy” screen will be displayed.

![](Images/image00391.jpeg)

Click on the "New" button.

Define the direct pricing strategy (<10% occupancy OPEN)

![](Images/image00392.jpeg)

Also define the reverse pricing strategy (> 10% occupancy CLOSED)

![](Images/image00393.jpeg)

The dates in the "Restriction Dates" field correspond to the "Arrival" dates of the reservation in which pricing strategies are applied.

The dates in the "Control Dates" field correspond to the dates on which the reservation is registered.

4. OCCUPANCY LEVEL AND FORECAST PROCESSORoccupancy

Enter thelevel screen using the Shift + F1 key combination and note that on May 2 there are no reserved rooms.

![](Images/image00394.jpeg)

The proper execution of the pricing strategy considers the level of occupancy to apply or not the price restrictions. This level of occupancy requires that the reserved rooms be deducted (Deduct) from the room inventory.

To activate room inventory deductions it is important that the forecast processor is running.

![](Images/image00395.jpeg)

To activate it, enter the main menu "Utilities", the "Utilities" screen will be displayed. On this screen, enter the “Processors” menu, “Forecast Processor” submenu, the “Forecast Processor Status” screen will be displayed.

![](Images/image00396.jpeg) ´

On the “Forecast Processor Status” screen, the running process should be shown “Running”, otherwise click on the "Start" button.

![](Images/image00397.jpeg)

5. RATE CODE CONFIGURATION

We must verify the “Rate Code” configuration, enter the “Rate Management” menu, “Rate Classifications” menu option, “Rate Codes” option. Select the "Rate Code" involved in the "Rate Strategy" and click on the "Edit" button.

![](Images/image00398.jpeg)

In the form "Rate Header" make sure that the field "Room Types" has the type of room ST to which we are establishing the pricing strategy, also verify that the date range "Begin Sell Date" and "End Sell Date" is a Date range according to the execution dates and control dates of the pricing strategy.

![](Images/image00399.jpeg)

In the “Rate Detail” form, select the record corresponding to the “Room Types” ST considered in the pricing strategy, make sure that the “Start Date” and “End Date” date range is in accordance with the execution dates and the control dates defined in the pricing strategies.

![](Images/image00400.jpeg)

We leave the records of the “Negotiated” form blank.

![](Images/image00401.jpeg)

We leave the fields of the “More” form blank.

![](Images/image00402.jpeg)

6. CONFIGURATION OF THE RESERVATION TYPES

We must verify the reservation types "Reservation Types" and take into account those types of reservation that Deduct from the physical inventory of rooms, that is, they make a reservation is confirmed and cannot be canceled.

This is very important because the Rate Strategy only counts the rooms reserved and deducted from the room inventory to verify the level of occupancy.

![](Images/image00403.jpeg)

In the “Reservation Type” screen we must have at least one record as the “Deduct” reservation type.

![](Images/image00404.jpeg)  ![](Images/image00405.jpeg)

7. MAKING RESERVATIONS

After the adequate verification of the configuration of the preliminary parameters, we enter the option menu "Reservations", select the option button "New Reservation"

In the "Profile Search" screen, we search for a specific client.

![](Images/image00406.jpeg)

On the "Reservation" screen, the date in the "Arrival" field must be within the execution range of the price strategy, select the "Room Type" and the "Rate Code" defined in the price strategy.

** important ** you must select in the "Res Type" field a type of reservation with Deduct.

![](Images/image00407.jpeg)

As long as the restriction rule does not reach the limit of the direct pricing strategy (<10% occupancy OPEN), reservations are made on a daily basis.

![](Images/image00408.jpeg)

Once the reservation is made on the occupancy screen (Shift + F1) on the date May 2, we observe that there is 01 room reserved and deducted from the inventory (Deduct).

![](Images/image00409.jpeg)

We make reservations with the Cashier profile for the number of rooms required to cover 10% occupancy (limit of the pricing strategy).

![](Images/image00410.jpeg)  ![](Images/image00411.jpeg)

In the next reservation intention, the “Rate Query Details” screen will be displayed with the price in the “Close” status, which confirms that the pricing strategy restricts the allocation of the price.

![](Images/image00412.jpeg)  ![](Images/image00413.jpeg)

If you want to proceed with the assignment, the price assignment permission request screen will be displayed. This authorization is provided by a Supervisor user.

![](Images/image00414.jpeg)

8. REPORTS ASSOCIATED WITH RATE STRATEGY

If you want to review the behavior of pricing strategies, use the following reports: Report

name

.rep File

Restrictions Detail

raterest.rep

Reservation Rate Check

res_rate_check.rep

Reservations made On by Ratecode

paris_reservationsmadeonbyratecode.rep

# Creation of reports with Opera PMS and Oracle Reports Developer.

To create custom reports in Opera, you must first create the SQL statement that will obtain the report data from the Oracle database of Opera, then design the report in the Oracle Reports Developer tool and at the end assign an option in the reports list available from Opera.

It is very important to use the correct version of Oracle Reports Developer, usually this tool is installed by the Opera PMS provider.

Opera | Oracle Reports Developer

v 5.0 | v 10.1.2.0.2

v 5.5 | v 11.1.2.2.0

In this blog we will make a report that lists the list of hosted clients.

We carry out the SQL statement that extracts the data from the Oracle database of Opera.

SQL

SELECT a.room, trim (initcap (a.guest_first_name)) || ' '|| trim (initcap (a.sname)) As Name,

trim (a.company_name) ||' '|| a.travel_agent_name As Company,

a.resv_status, a.arrival, a.departure

FROM reservation_general_view to

WHERE (a.resv_status =' CHECKED IN 'OR a.resv_status =' DUE OUT ')

ORDER BY a.room We will

use the view "reservation_general_view", this view has the necessary query to extract the data of all the reservations of the clients, in their different states:

CHECKED IN

PROSPECT

CANCELLED

NO SHOW

CHECKED OUT

RESERVED

We execute this query in the development environment Oracle SQL Developer to validate that the query works properly

![](Images/image00415.jpeg)

We execute the design program Oracle Reports Developer

![](Images/image00416.jpeg)

The Builder will be shown

![](Images/image00417.jpeg)

We connect the builder to the database, for this we select the "File" menu option "Connect ...",

![](Images/image00418.jpeg)

The connection wizard will be displayed to the database where you must put the User, Password and the instance name of the Oracle database. then click on the radio button "Connect" to connect to the database.

![](Images/image00419.jpeg)

Select the “File” Menu, “New” / “Report…” menu option, the “New Report” wizard will be displayed. select the option “Use the Report Wizard” and click on the option button OK

![](Images/image00420.jpeg)

The wizard “Report Wizard!” will be displayed, click on the option button “Next>”

![](Images/image00421.jpeg)

Keep the option “Create both Web and Paper Layout” selected by default and click on the "Next>" button.

![](Images/image00422.jpeg)

We place the name of the report "Report guests in property" and click on the "Next>" button.

![](Images/image00423.jpeg)

Select the option "SQL Query" and click on the option "Next>".

![](Images/image00424.jpeg)

In the Data Source definition screen we place the SQL Query that allows the extraction of data from the reservations and we click on the “Next>” option.

![](Images/image00425.jpeg)

We select all the fields of the Query that will be shown in the report and we click on the “Next>” option.

![](Images/image00426.jpeg)

On the screen for calculating totalized fields, it is not necessary to totalize by a certain field, we click on the “Next>” option.

![](Images/image00427.jpeg)

On this screen we keep the width of the labels and click on the option "Next>"

![](Images/image00428.jpeg)

Select a report template and click on the option "Next>"

![](Images/image00429.jpeg)

We click on finish and then preview the report designdesign of the report

![](Images/image00430.jpeg)

The pre-will be displayed report as follows We

![](Images/image00431.jpeg)

compile the report by clicking on the "Compile" menu, "All .." menu option.

![](Images/image00432.jpeg)

Click on Ok to confirm the compilation process.

![](Images/image00433.jpeg)

After compiling the report it is important to export the report file in .rep format, a format that can be used from Opera.

![](Images/image00434.jpeg)  ![](Images/image00435.jpeg)

The .rep report files must be placed in the runtimes \ folder located at the following address: D: \ MICROS \ OPERA \ production \ runtimes \ We

enter the Opera Configuration module.

![](Images/image00436.jpeg)

Select the menu options "Setup", menu option "Report Setup" option "Reports"

![](Images/image00437.jpeg)

The "Reports - Configuration" screen will be displayed, click on the "New" button.

![](Images/image00438.jpeg)

On the "Reports - New" screen, place the name of the report and select a specific "Report Group".

![](Images/image00439.jpeg)

We click on the list selections button associated with “File Name”. in the “File List” screen we look for the report file .rep.

![](Images/image00440.jpeg)  ![](Images/image00441.jpeg)

We make sure that the report custom_report_huespedes.rep is in the "Reports - Configuration" screen.

![](Images/image00442.jpeg)

To show the new report, we select the option button "Miscelaneous", option "Reports", the "Reports" screen will be shown.

![](Images/image00443.jpeg)

In the "Reports" screen find the report "Custom Guest Report" and click on the Ok button.

![](Images/image00444.jpeg)

The "Report Parameters" screen will be displayed and click on the "Preview" button.

![](Images/image00445.jpeg)

The customized report will be displayed.

![](Images/image00446.jpeg)

# Opera PMS - Oracle Data

Dictionary. data from an information system is very important to start the entire information system development and maintenance process.

In order to access the Opera data dictionary, you must have access to the Oracle database from Oracle SQL Developer or another development environment for Oracle.

Use the following SQL statement to extract the Opera data dictionary:

select cc.table_name, tc.column_name, tc.nullable, tc.data_type ||

case

when tc.data_type = 'NUMBER' and tc.data_precision is not null

then '(' || tc.data_precision || ',' || tc.data_scale || ')'

when tc.data_type like '% CHAR%'

then '(' || tc.data_length || ')'

else null

end type

, cc.comments

from user_col_comments cc

join user_tab_columns tc

on (cc.column_name = tc.column_name and cc.table_name = tc.table_name)

order by cc. table_name ASC, tc.column_name ASC

For those who could not have access to the Oracle database of Opera I leave the Data Dictionary in Excel format and the description of the fields in English and their translation in Spanish.

Due to the fact that Opera has more than 4800 tables, this blog will describe the most important tables and fields for a maintenance and development process.

[Opera PMS Data Dictionary - Oracle](https://docs.google.com/spreadsheets/d/19lfAxMjt29iqhjeux8wn6DuMa9-cgiTC/export?format=xlsx)

# Design and creation of report of Daily Payments from Opera PMS We will

make a report that shows the list of payments made per day, payments from the various forms of payment; cash, cards, etc. This type of report allows us to view and validate the charges made by the ATMs per transaction day.

The report will show the following columns:

● - Transaction Date - Transaction

● Code

● - Description of the Transaction Code

● - Reservation

● NumberRoom Number

● -- Guest Name

● - Voucher Number

● - Total Billed in Dollars

● - Currency Code

● - User Cashier

SELECT TO_CHAR (fi.TRX_DATE,'DD / MM / RR') TRX_FECHA, --Date of Transaction

  fi.TRX_CODE TRX_CODE, -Transaction Code

  UPPER(trc.DESCRIPTION) TRX_DESCRIPTION, - Transaction Code Description

  fi.RESV_NAME_ID NR_RESERVA, --Reservation Number

  fi.ROOM NR_HAB, --NVL Room

  Number (n.SNAME||','||n.SFIRST,''), GUEST--Guest Name

  fi.fiscal_bill_no NR_DOCUMENTO, - Voucher Number

  DECODE (fi.bill_no,NULL,0, decode (fi.trx_no, fol.bill_payment_trx_no, fol.total_gross,0)) BILLED_USD, --Total Billed in Dollars

  fi.CURRENCY CURRENCY, --RPAD Currency

  Code (UPPER (au.APP_USER),5) USER --User

FROM 

  FINANCIAL_TRANSACTIONS fi

 INNER  JOIN FOLIO_TAX fol ON (fol.BILL_NO = fi.BILL_NO AND fol.NAME_ID = fi.NAME_ID)

 INNER  JOIN  NAME n ON (n.NAME_ID = fi.NAME_ID)

 INNER  JOIN TRX$_CODES trc ON (trc.TRX_CODE = fi.TRX_CODE)

 INNER  JOIN APPLICATION$_USER au ON (au.APP_USER_ID = fi.INSERT_USER)

WHERE

--- TO_CHAR (fol.BUSINESS_DATE, 'DD / MM / RRRR') = '11 / 03/2019 '

fol.BUSINESS_DATE =  : P_BUSDATE

AND fi.BILL_NO IS  NOT  NULL

AND (fi.TRX_CODE BETWEEN  9000  AND  9999)

AND fi.DISPLAY_YN ='Y'

AND fi.RECPT_TYPE ! =  'CUX'

AND fi.PACKAGE_CREDIT IS  NULL

AND fi.PACKAGE_DEBIT IS  NULL

AND fi.PRICE_PER_UNIT <>  0

ORDER  BY

TRX_FECHA, NR_DOCUMENTO, TRX_CODE, TRX_FECHA;

To make this report, the tables related to financial transactions, customer folio and other associated tables will be used:

FINANCIAL_TRANSACTIONS: This table stores all the transactions related to the cashier service, transactions for each reservation (guest book, deposit book, accounts receivable book and package book).

FOLIO_TAX: This table stores a summary of the income information by invoice.

NAME: This table stores the profile information of guests, companies, travel agencies, sources and groups.

TRX $ _CODES: This table stores all the transaction codes of the system, these transactions are the concepts that are selected at the time of POST.

APPLICATION $ _USER: This table stores all the user information that operates the system.

We validate the SQL statement by executing the query in the "Oracle SQL Developer" development environment.

![](Images/image00447.jpeg)

We execute the report design program "Oracle Reports Builder" and create a new report using the "Report Wizard".

In the "Report Style" screen we indicate the title of the report and select the format "Group Left", this format will allow us to create groupings in the report.

![](Images/image00448.jpeg)

In the “Data Source Definition” screen of the Report Wizard, the confirmation for the creation of the P_BUSDATE report parameter will be presented. This parameter will allow us to select from Opera the date for which we want the payment report to be generated.

![](Images/image00449.jpeg)

We click on the OK button and continue with the default values ​​of the other screens of the wizard.

In the "Grouping of Fields" screen we select the fields that will allow us to group the report records and calculate the subtotals for these groups. In our case, we select the TRX_CODE and TRX_DESCRIPTION fields, which will allow us to group and totalize by payment method.

![](Images/image00450.jpeg)

In the "Select Fields to Display" screen we select all the fields of the Query that will be part of the report.

![](Images/image00451.jpeg)

In the "Calculate Totals" screen, select the fields to be totaled and the form of totalization, in our case we will make a sum of the invoiced amount and a count of the amount of receipts.

Sum (FACTURADO_USD)

Count (NR_DOCUMENTO)

![](Images/image00452.jpeg)

we click on the "Next>" button and continue with the default values ​​of the other screens of the wizard.

At the end of the wizard, the report will be displayed with the groupings and totalized fields:

![](Images/image00453.jpeg)

The "Oracle Reports Builder" design tool allows changing the original report design, allowing a much more aesthetic design of the report.

Once the report is compiled, the file must be exported in .rep format "custom_reporte_pagos.rep", this format will allow the report to be created from the "Reports - New" configuration screen of Opera.

From the "Configuration" screen select the menu option "Setup", Sub Menu "Report Setup" option Reports.

![](Images/image00454.jpeg)

On the "Reports - Configuration" screen, select the "New" option button.

![](Images/image00455.jpeg)

On the "Reports - New" screen we indicate the name of the report, in this case "Custom Payment Report", in the "Report Group" field select the option "Utilities" and leave the other options as shown in the image.

![](Images/image00456.jpeg)

In the “File Name” field we click on the List button, the “File List” screen will be displayed, on this screen we select the .rep file that we have created from the “Oracle Reports Builder” in previous steps.

We select the report "custom_reporte_pagos.rep" and click on the "OK" button to select this file.

![](Images/image00457.jpeg)

In the "Reports New" screen we select the "Parameter" button, the "Parameters" screen will be displayed to create the "P_BUSDATE" parameter that the payment report requires.

![](Images/image00456.jpeg)

In the “Parameters” screen enter the following data for the P_BUSDATE parameter and click on the “OK” button.

![](Images/image00458.jpeg)

To display the report asuser on the "PMS" screen click the radio button "Miscellaneous" option "Reports"

![](Images/image00459.jpeg)

in the "Reports" screen locate the report payments created and click the "OK" button

![](Images/image00460.jpeg)

will display the "Report Parameters" screen, on this screen indicate a certain date and click on the "Preview" button.

![](Images/image00461.jpeg)

The payment report designed in the "Oracle Reports Builder" will be displayed.

![](Images/image00462.jpeg)

# Creation of ForeCast and History report in Opera PMS

Revenue Management is a technique that consists of selling the right product, to the right customer, at the right time and at the right price, it is about predicting consumer behavior in order to maximize revenue and minimize costs.

Forecasting consists of estimating and analyzing future demand for a product or service using different variables such as historical data.

One of the main variables on which hotel forecasting is based is the analysis of statistical data of the property in previous periods, with this we can predict future income and make the appropriate business decisions to correct deviations in order to maximize income and minimize costs.

Being clear about the importance of a forecast tool, especially online, in real time and from a smartphone that queries data directly from Opera PMS, it would be a very useful tool for the efficient management of the Property.

It is important to consider that the online forecast tool must include the following data, the descriptions of which are kept from the original Opera documentation:

Date. Date to which the statistics apply.

Total Occupancy. Total occupied rooms (non-deduct, deduct, individual and group).

Arrival Rooms. Rooms with guests arriving this date. For arrivals, component rooms count as 1 and not the number of physical rooms making up the component room.

Comp Rooms. Complementary rooms (rooms attached to reservations having a rate code that is flagged Complimentary).

House Use. House use rooms (rooms attached to reservations having a rate code that is flagged House Use).

Individual Deduct. Individual reservations having a reservation type that is flagged Deduct from inventory.

Non-Deduct Individual. Individual reservations having a reservation type that is not flagged Deduct from inventory.

Deduct Group. Group reservations having a reservation type that is flagged Deduct from inventory.

Non-Deduct Group. Group reservations having a reservation type that is not flagged Deduct from inventory.

Occupancy%. (Total Occupied Rooms / Number of Rooms in Property) x 100).

Room Revenue. Total revenue for this date associated with Lodging transaction codes for deduct, non-deduct, individual, and group reservations.

Average Rate. Total Room Revenue / Number of Occupied rooms.

Departure Rooms. Rooms due out this date. For departures, component rooms count as 1 and not the number of physical rooms making up the component room.

Day Use Rooms. Day Use Rooms for the date.

No Show Rooms. No Show Rooms for the date.

For this purpose, the following SQL Query is built for Oracle that obtains the forecast with the income of the current month (HISTORY) towards the estimated annual income (FORECAST).

![](Images/image00463.jpeg)

This Query will be the basis to start building the forecast online tool for smartphones.

SELECT rec_type rec_type,

       DECODE (rec_type,'A_STAT', f_message ('REP_HISTORY','History'), f_message ('REP_FORECAST','Forecast')) rec_type_desc,

       TO_CHAR (considered_date,'DD / MM / RRRR') considered_date,

SUM (no_rooms * count_resv_01) no_rooms,

SUM (ind_deduct_rooms * count_resv_01) ind_deduct_rooms,

SUM (ind_non_deduct_rooms * count_resv_01) ind_non_deduct_rooms,

SUM (grp_deduct_rooms * count_resv_01) grp_deduct_rooms,

SUM (grp_non_deduct_rooms * count_resv_01) grp_non_deduct_rooms,

SUM (no_persons * count_resv_01) no_persons,

SUM ( arrival_rooms * count_resv_01) arrival_rooms,

SUM (departure_rooms * count_resv_01) departure_rooms,

SUM (complimentary_rooms * count_resv_01) complimentary_rooms,

SUM (house_use_rooms * count_resv_01) house_use_rooms,

SUM (day_use_rooms * count_resv_01) day_use_rooms,

SUM (no_show_rooms * count_resv_01) no_show_rooms,

SUM (revenue * count_revenue_01) revenue,

       SUM (DECODE (group_yn,'N', DECODE (deduct_yn,'Y', revenue,0),0) * count_revenue_01) ind_deduct_revenue,

       SU M (DECODE (group_yn,'N', DECODE (deduct_yn,'N', revenue,0),0) * count_revenue_01) ind_non_deduct_revenue,

       SUM (DECODE (group_yn,'Y', DECODE (deduct_yn,'Y', revenue,0),0) * count_revenue_01) grp_deduct_revenue,

       SUM (DECODE (group_yn,'Y', DECODE (deduct_yn,'N', revenue,0),0) * count_revenue_01) grp_non_deduct_revenue,

SUM (owner_rooms * count_resv_01) owner_rooms,

SUM ( ff_rooms * count_resv_01) ff_rooms

 FROM (

 SELECT SUBSTR (rsf.Rec_type,1,6) rec_type,

               rsf.considered_date considered_date,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, rsf.no_rooms) no_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, DECODE (rsf.group_yn,'N', DECODE (deduct_yn,'Y', rsf.no_rooms,0),0)) ind_deduct_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, DECODE (rsf.group_yn,'N', DECODE (deduct_yn,'N', rsf.no_rooms,0),0)) ind_non_deduct_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, DECODE (rsf.group_yn ,'Y', DECODE (deduct_yn,'Y', rsf.No_rooms,0),0)) grp_deduct_rooms,

               DECODE (nvl (rsf.Owner_rental_flag,'H'),'O',0, DECODE (rsf.Group_yn,'Y', DECODE (deduct_yn,'N', rsf.No_rooms,0),0)) grp_non_deduct_rooms,

               DECODE (nvl (rsf.Owner_rental_flag,'H'),'O',0, rsf.No_persons) no_persons,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, rsf.arrival_rooms) arrival_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, rsf.departure_rooms) departure_rooms,

               DECODE (nvl (rsf.owner_rental_f lag,'H'),'O',0, rsf.complimentary_rooms) complimentary_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, rsf.house_use_rooms) house_use_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, rsf.day_use_rooms) day_use_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0, rsf.no_show_rooms) no_show_rooms,

               DECODE (nvl (rsf.owner_rental_flag,'H'),'O',0,

 CASE  'RN'

 WHEN  'RN'  THEN rsf.net_room_revenue - net room revenue

 WHEN  'RG'  THEN rsf.net_room_revenue + rsf.room_revenue_tax - net total revenue

 WHEN  'TN'  THEN rsf.total_revenue - gross room revenue

 WHEN  'TG'  THEN rsf.total_revenue + rsf.total_revenue_tax - gross total revenue

 ELSE rsf.net_room_revenue

 END

               ) revenue, 

               (CASE  WHEN SUBSTR (rsf.Room_category,1,1) <>  '-'  THEN  1  - this is not a PM resv, count it

 WHEN SUBSTR (rsf.Rec_type,1,6) =  'A_STAT'  THEN  0 - for statistics we never count PM reservations (rooms)

 WHEN NVL ('N','N') =  'AND'  THEN  1 - for forecast look at parameter whether to count PM rooms

 ELSE  0

 END ) count_resv_01,

               (CASE  WHEN SUBSTR (rsf.Room_category,1,1) <>  '-'  THEN  1  - this is not a PM resv, count the revenue

 WHEN SUBSTR (rsf.Rec_type,1,6) =  'A_STAT'  THEN  1 - for statistics we count all revenue, even from PM resv

 WHEN NVL ('N','N') =  'AND'  THEN  1 - for forecast look at parameter whether to count PM rooms

 ELSE  0

 END ) count_revenue_01,

               rsf.owner_rooms owner_rooms,

               rsf.ff_rooms ff_rooms,

               rsf.deduct_yn,

               rsf.group_yn 

 FROM rep_res_stati_forecast_hld rsf

 where rsf.considered_date between TO_DATE (('01'||to_char (sysdate,'MMRRRR')),'DDMMRRRR') and TO_DATE (TO_CHAR (LAST_DAY (to_date (to_char (ADD_MONTHS (SYSDATE, 11),'YYYYMM'),'YYYYMM')),'DDMMRRRR'),'DDMMRRRR')

 and rsf.deduct_yn='Y'

 - make sure that we have at least one record per day

 UNION  ALL

 SELECT (CASE  WHEN (TO_DATE (('01'||to_char (sysdate,'MMRRRR')),'DDMMRRRR') + ns.N -  1) < pms_p.business_date THEN

 'A_STAT'

 ELSE  'B_FORE'

 END) rec_type,

               (TO_DATE (('01'||to_char (sysdate,'MMRRRR')),'DDMMRRRR') + ns.N -  1) considered_date,

 0 no_rooms,

 0 ind_deduct_rooms,

 0 ind_non_deduct_rooms,

 0 grp_deduct_rooms,

 0 grp_non_deduct_rooms,

 0 no_persons,

 0 arrival_rooms,

 0 departure_rooms,

 0 complimentary_rooms,

 0 house_use_rooms,

 0 day_use_rooms,

 CASE  WHEN (TO_DATE (('01'||to_char (sysdate,'MMRRRR')),'DDMMRRRR') + ns.N -  1) < pms_p.business_date THEN

 0

 ELSE TO_NUMBER (NULL)

 END no_show_rooms, - for the forecasting section the No Show rooms should be NULL since we cannot predict how many rooms will be no-show

 0 revenue,

 0 count_resv_01,

 0 count_revenue_01,

 0 owner_rooms,

 0 ff_rooms,

 'N' deduct_yn,

 'N' group_yn

 FROM number_scale ns

 WHERE ns.n <= TO_DATE (TO_CHAR (LAST_DAY (to_date (to_char (ADD_MONTHS (SYSDATE, 11),'YYYYMM'),'YYYYMM')),'DDMMRRRR'),'DDMMRRRR') - TO_DATE (('01'||to_char (sysdate,'MMRRRR')),'DDMMRRRR') +  1

        )

 group  by rec_type,

           considered_date

 ORDER  BY rec_type,

       TO_DATE (considered_date,'DD / MM / RRRR')

# Creation of Trial Balance Details By Transactions Report in Opera PMS

It is important to tell you that just as we did in HouseKeeping to show the status of the rooms from the smartphone you can develop analytical reports based on the Trial Balance to have the income statement online.

This report shows the details of all the transactions posted to the guest and the classification of these transactions.

Because the terms of the Balance cannot be directly translated into Spanish without distorting their meaning, I will keep the definitions in English in this blog.

The Trial Balance reprt includes all transactions posted, and then a breakdown of business within each of the five Ledgers (Guest Ledger, AR Ledger, Deposit Ledger, Package Ledger, and Inter Hotel Ledger). The Trial Balance may be used to assist in ensuring your property's accounts are balanced and in good standing.

Summary of others Reports That May Be Used For Balancing

| Report Title | .REP Filename | Additional Information |
| Aging Summary by Types | araging | May be run for a specific date. |
| Detailed Aging Report | aragingdet | May be run for a specific date. |
| AR Ledger | arledger | Continually updating |
| Deposit Activity Report | deposit_activity | May be run for a specific date but should be run by Activity Date if used for balancing. |
| NA Deposit Ledger | deposit_ledger | Continually updating. |
| Financial Payments and Revenue Postings | findeptcodes | May be run for a specific date but should always be run for NET revenue if used for balancing. |
| Journal by Cashier and Transaction Code | finjrnlbytrans | May be run for a specific date but should always be run for NET revenue if used for balancing. |
| Financial Transactions with Generates | finjrnlbytrans2 | May be run for a specific date but should always be run for NET revenue if used for balancing. |
| Package Postings | finpkgposting | Captures data for the current business date, must be attached to Night Audit Report Group if used for balancing. |
| Guest Trial Balance | gl_trial_balance | May be run for a specific date. |
| Manager Report | manager_report | May be run for a specific date. |
| Deposits Transferred at C / I | nadeptransci | Captures data for the current business date, must be run with the Night Audit if used for balancing to trial_balance. |
| Package Ledger Detail | napkgledger | Captures data for the current business date, must be run with the Night Audit if used for balancing to trial_balance. |
| Trial Balance | trial_balance | May be run for a specific date. |

The Trial Balance Detail has the following structure:

![](Images/image00464.jpeg)

Room. Room number of the reservation.

Guest Name. Name of the guest.

Arragement Desc. Name of transaction classification.

Trx Code. Code Transaction

Trx No. Sequential Transaction number.

Description. Transaction description.

Old Balance (Opening Balance). Total balance of the guest account for the date in which the report was ran.

Credits. Total Amount that has been paid against the account by the guest.

Debits. Total Amount that has been charged to the guests account.

Transferred Credits. Any amounts that have been transferred to the guests account and that is considered a credit.

Transferred Debits. Any amounts charged to the guest account as a result of a transfer.

New Balance (Closing Balance). Closing balance for the account. This column is calculated by the following formula: Opening Balance + Debits + Transfer Debit - Credits - Transfer Credits.

The SQL query for Oracle:

SELECT t.room, t.guest_name, t.arrangement_desc,

t.trx_code, t.trx_no,

t.description,

t.old_balance, t.credit, t.debit, t.transfer_credit, t.transfer_debit, t.new_balance

FROM(

 SELECT

        fs.trx_no,

        ar.arrangement_desc,

        fs.resv_name_id,

                  fs.name_id,

                  fs.resort,

                  rv.room,

                  rv.guest_name,

                  co.trx_code,

                  co.description,

 - all GL postings from days prior to p_from_date

                  DECODE (abs (trunc (to_date (to_char (to_date (to_char (pms_p.business_date))))) - trunc (fs.trx_date)),

 0,0,

 -1,0,

                          (NVL (fs.Guest_account_debit,0))- (NVL (fs.Guest_account_credit,0))) old_balance,

 - all GL credits posted on p_from_date

                  DECODE (fs.from_resv_id,NULL, decode (pms_p.business_date - trunc (fs.trx_date),

 0, nvl (fs.Guest_account_credit,0),

 0),

 0) credit,

 - all GL debits posted on p_from_date

                  DECODE (fs.from_resv_id,NULL, decode (pms_p.business_date - trunc (fs.trx_date),

 0, nvl (fs.Guest_account_debit,0),

 0),

 0) debit,

 - all GL transfer credits from other reservations posted on p_from_date

                  DECODE (fs.from_resv_id,NULL,0,

                                      decode (pms_p.business_date - trunc (fs.trx_date),

 0, nvl (fs.Guest_account_credit,0),

 0)) transfer_credit,

 - all GL transfer debits from other reservations posted on p_from_date

                  DECODE (fs.from_resv_id,NULL,0,

                                      decode (pms_p.business_date - trunc (fs.trx_date),

 0, nvl (fs.Guest_account_debit,0),

 0)) transfer_debit,

 - all GL postings posted on p_from_date or before

                 DECODE (abs (pms_p.business_date - trunc (fs.trx_date)),

 -1,0,

                          NVL (fs.Guest_account_debit,0) - NVL (fs.Guest_account_credit,0)) new_balance

 FROM financial_transactions_view fs

 inner  join rep_reservation_all_view rv on (fs.resv_name_id = rv.resv_name_id)

 inner  join trx$_codes co on  (co.trx_code=fs.trx_code)

 inner  join trx$_code_arrangementar on  (ar.arrangement_id=co.arrange_code)

 where fs.resv_name_id IN

              (- all resv_name_ids that had a posting today

 SELECT resv_name_id

 FROM financial_transactions ftx

 WHERE ftx.resort = : RESORT

 AND ftx.trx_date = pms_p.business_date

 AND ftx.resv_name_id IS  NOT  Null

 UNION  ALL

 - all reservations that were (supposed to be) in-house today

 SELECT resv_name_id

 FROM reservation_daily_elements rde,

                      reservation_daily_element_name rdn

 WHERE rde.resort =  : RESORT

 AND rde.reservation_date = pms_p.business_date

 AND rdn.resort = rde.resort

 AND rdn.reservation_date = rde.reservation_date

 AND rdn.resv_daily_el_seq = rde.resv_daily_el_seq

 UNION  ALL

 SELECT resv_name_id

 FROM reservation_name rn

 WHERE rn.resort =  : RESORT

 AND rn.post_co_flag =  'O'

     )

 AND fs.trx_date <= pms_p.business_date

 AND (fs.Guest_account_credit IS  NOT  Null  OR fs.guest_account_debit IS  NOT  NULL)

 and fs.resv_name_id=3142559  and rv.room='0206'

) t

ORDER  BY t.room, t.arrangement_desc, t.trx_code, t.trx_no

It is important to tell you that just as we did in HouseKeeping to show the status of the rooms from the smartphone, analytical reports can be developed based on the Trial Balance to have the income status online.

# Room Status and Housekeeping Status in Opera PMS, Online web query from Smartphone

In this blog we show the development of a responsive web system that shows the status of the rooms of a property, this web system is very important for the agile operation of the supervisors of rooms, supervisors constantly check the status of the rooms online from their cell phones and avoid having to go to a desktop PC to consult the opera report on the status of the rooms.

The states of the rooms to consider are the following:

SELECT ROOM_STATUS_ID, ROOM_STATUS_CODE, ROOM_STATUS_DESC FROM OPERA.ROOM_STATUS_CODES_ALL

| ROOM_STATUS_ID | ROOM_STATUS_CODE | ROOM_STATUS_DESC |
| 1 | CL | Clean |
| 2 | DI | Dirty |
| 3 | IP | Inspected |
| 4 | OS | Out of Service |
| 5 | OO | Out of Order |

SELECT  DISTINCT HK_STATUS FROM OPERA.ROOM

OCC: occupied

VAC: vacant

SELECT  DISTINCT HK_STATUS FROM OPERA.ROOM

OCC: occupied

VAC: vacant

Use the following Query to display the current status of the rooms of a certain Floor:

SELECT r.room, r.room_status, r.hk_status, c.label, c.short_description,

CASE  WHEN  NVL (v.Resv_status,'F')='CHECKED IN'  THEN  'CI'  WHEN NVL (v.Resv_status,'F')='CHECKED OUT'  THEN  'CO'  ELSE  ''  END resv_status,

TO_CHAR (v.Arrival,'DD / MM') arrival,

TO_CHAR (v.Departure,'DD / MM') departure, TO_CHAR (v.Departure_time) departure_time

,CASE  WHEN r.hk_status<>r.fo_status THEN  'AND'  ELSE  'N'  END isdiscrepancy

FROM OPERA.ROOM r 

INNER  JOIN OPERA.ROOM_CATEGORY_TEMPLATE c ON (r.Room_category=c.Room_category) 

LEFT  JOIN (

SELECT r.room, MIN (r.resv_status) resv_status, min (r.arrival) arrival, max (r.departure) departure, max (r.departure_time) departure_time

FROM reservation_general_view r

WHERE r.trunc_departure> =pms_p.business_date and r.room is  not  null

AND r.resv_status IN ('CHECKED IN','CHECKED OUT')

GROUP  BY r.room

) v ON (v.room=r.room)

WHERE SUITE_TYPE<>'PSUEDO' 

AND to_number (r.Floor)=4--FLOOR

ORDER  BY to_number (r.Floor) ASC, to_number (r.Room) ASC

![](Images/image00465.jpeg)

The screens of the web system that queries the status of the rooms that are displayed from a smartphone device are shown as follows:

![](Images/image00466.jpeg)  ![](Images/image00467.jpeg)

Discrepancies:

Discrepancies can be observed in Opera's “Room Discrepancy” report:

in the PMS module, enter the “Miscellaneous” menu, “Reports” submenu, look for the “Room Discrepancy” report and click “OK”.

![](Images/image00468.jpeg)

The “Report Parameters” screen will be displayed, on this screen select the “Room Status” you want to view.

![](Images/image00469.jpeg)

In the “Room Status” selections, observe the 2 different discrepancy states:

![](Images/image00470.jpeg)

“Skip / Sleep Discrepant”: Discrepancies based on room status.

"Persons Discrepant": Discrepancies based on number of guests per room.

In this example we select the option "ALL Rooms", it will show us all the discrepancies of the property.

![](Images/image00471.jpeg)

Note that the Skip or Sleep discrepancies appear if the FO Status field is different from the HK Status field.

The discrepancies in the status of the rooms occur for the following reasons:

Sleep.-

FO_STATUS Indicates VAC (front office registers the guest check out)

HK_STATUS indicates OCC (hk indicates that someone is still in the room)

Skip.-

FO_STATUS Indicates OCC (guest leaves the room without checking out officially)

HK_STATUS Indicates VAC (HK indicates that the room is vacant)

To resolve the discrepancies, enter the Rooms Management menu, select the item “Housekeeping”, the Housekeeping screen will be displayed with the options to be made. we select the option “Rm. Discrepancies "

![](Images/image00472.jpeg)

In the" Room Discrepancies "screen, you can see the discrepancy of states between the fields" FO Status "(Front Office Status) and" HK Status "(HouseKeeping Status), to resolve the discrepancy both states must match.

![](Images/image00473.jpeg)

# Accounting Accounts assigned to Transaction Codes in Opera PMS

It is important to know that the “Transaction Codes” that we use during the “Post” in “Billing” are associated with certain accounting accounts that the tax administration of the country of residence requires of us.

![](Images/image00474.jpeg)  ![](Images/image00475.jpeg)

To show the correspondence or mapping between the “Transaction Codes” and the Accounting Accounts, they are shown in the “BackOffice Interface Transaction Codes Mapping” report. In the "Miscellaneous" menu, enter the option "Reports".

![](Images/image00476.jpeg)

In the "Reports" screen, look for the report "BackOffice Interface Transaction Codes Mapping" and then click OK, the report is previewed with the correspondence between the "Transaction Codes" and the Accounts Accountants

![](Images/image00477.jpeg)  ![](Images/image00478.jpeg)

If you need to assign a certain Accounting Account to a “Transaction Code”, enter Configuration in the “External” menu, “Back Office” submenu, “Configuration” option

![](Images/image00479.jpeg)

In the “Back Office Configuration” screen, select the “Transaction codes” option and click on OK

![](Images/image00480.jpeg)

The screen "Transaction Codes" will be shown, we will select a certain Code and click on the "Edit" button.

![](Images/image00481.jpeg)

The screen for assigning Accounting Accounts will be displayed, assign the appropriate accounting account and click on Ok.

![](Images/image00482.jpeg)

# Change Room Type Room Type in Opera PMS

This Post will show the procedure to change the Room Type of a room in Opera PMS.

We list the rooms of the property with their respective states, from this list we filter only the rooms with Empty "VAC" and Inspected "IP" status, we can only change the Room Type of rooms that are not reserved and are not occupied.

SELECT r.room, r.room_status, r.suite_type, r.fo_status, r.hk_status, r.description, c.label, c.short_description

FROM OPERA.ROOM r

INNER  JOIN OPERA.ROOM_CATEGORY_TEMPLATE c ON (r.Room_category=c.Room_category)

WHERE r.fo_status='VAC'  AND r.room_status='IP

In the Configuration module, enter the menu option “Reservations” submenu “Room Classifications” item “Rooms”

![](Images/image00483.jpeg)

In the “Room List” form, locate the room to which we want to change the Room Type “Room Type”

![](Images/image00484.jpeg)

In this screen we can verify the status and characteristics of each of the rooms and select the rooms that we want to change state.

In “Utilities”, enter the “Utilies” menu, “Property Config” submenu, “Change Rooms” submenu item “Change Room Type for a Room Number”

![](Images/image00485.jpeg)

The “Change Room Type”

![](Images/image00486.jpeg)

screen appears. On this screen select the Room Number, to which you want to change the “Room Type”, it is important to consider that the rooms can be changed only if they are in the following states:

FO_STATUS: VAC (Empty)

ROOM_STATUS: IP (Inspected)

we indicate the room number and select the new one type of room to assign.

![](Images/image00487.jpeg)

If the room is occupied or reserved, the following error message will be displayed, thereby preventing the reassignment of the room type.

![](Images/image00488.jpeg)

We review the reservation of the room in the Room Plan, to display the Room Plan screen press the Ctrl + F3 key, if we place the mouse pointer over the icon >> you will see a summary.

![](Images/image00489.jpeg)

We await the release of the room reservation.

To continue with the example we locate a room not reserved and not occupied through the Room Plan, in our case room 1018.

![](Images/image00490.jpeg)

We click on the "Yes" button. the change of the Room Type will be made.

![](Images/image00491.jpeg)  ![](Images/image00492.jpeg)

# Querys SQL Oracle useful for administration in Opera PMS

--Production byevent

SELECT a.room, a.resv_name_id, a.passerby_name, a.trx_code, a.trx_date, a.guest_account_debit

FROM financial_transactions_view to

WHERE to_char (a.trx_date,'RRRR') =  2019  and

  a.guest_account_debit <>  0.00  and

      a.trx_code IN (2580,2503)

--Habitaciones blocked

SELECT  distinct a.room, a.description, b.begin_date, b.end_date,

   b.repair_remarks, b.reason_code, a.room_status, b.completed_date

FROM room a, room_repairs b

WHERE substr (a.room_status,1,1)='O'

 and a.room=b.room

 and b.end_date> =TO_CHAR (pms_p.business_date)

 and b.begin_date<=TO_CHAR (pms_p.business_date)

 and b.completed_date is  NULL

ORDER  BY room, BEGIN_DATE

--Habitaciones reserved

SELECT  distinct a.share_id, a.room, a.room_category_label, a.company_name, a.sguest_name, a.guest_country_desc,

       a.trunc_arrival, a.trunc_departure, a.currency_code, a.share_amount,

       a.market_desc, a.confirmation_no, a.market_code, a.effective_rate_amount, a.fixed_charge

FROM reservation_general_view to

WHERE substr (a.ARRIVAL,1,11)=TO_CHAR (SYSDATE)

 and  (A.RESV_STATUS='RESERVED'OR  A.RESV_STATUS='PROSPECT')

and  a.share_amount<>0.00

--Income by company and market

SELECT  distinct a.share_id, a.room, a.room_category_label, a.company_name, a.sguest_name, a.guest_country_desc,

       a.trunc_arrival, a.trunc_departure, a.currency_code, a.share_amount,

       a.market_desc, a.confirmation_no, a.market_code, a.effective_rate_amount, a.fixed_charge

 FROM reservation_general_view_hld to

 WHERE a.resv_status='CHECKED IN'

 and a.share_amount>0.00

UNION  ALL

SELECT  distinct a.share_id, a.room, a.room_category_label, a.company_name, a.sguest_name, a.guest_country_desc,

       a.trunc_arrival, a.trunc_departure, a.currency_code, a.share_amount,

       a.market_desc, a.confirmation_no, a.market_code, a.effective_rate_amount, a.fixed_charge

 FROM reservation_general_view_hld to

 WHERE a.resv_status='CHECKED IN'

 and  substr (a.market_code,1,2)='80'  and a.financially_responsible_yn is  null

--Rooms per day

SELECT a.considered_date, sum (a.no_rooms), sum (a.arrival_rooms), sum (a.departure_rooms), sum (a.complimentary_rooms),

       sum (a.net_room_revenue)

FROM rep_res_statistics_forecast to

WHERE (a.CONSIDERED_DATE BETWEEN TO_CHAR (SYSDATE -TO_CHAR (sysdate-1,'DD')) and TO_CHAR (SYSDATE+366)) and a.ROOM_CATEGORY<>'-1'

 AND ((a.Deduct_yn='N'  AND  a.market_code=  '50A') or a.deduct_yn='Y')

GROUP  BY a.CONSIDERED_DATE

--Forecast by Marked Code Monthly

SELECT

    CONSIDERED_MONTH,

    CONSIDERED_YEAR,

    MARKET_GROUP,

    MARKET_GROUP_DESC,

    SUM (no_rooms) NO_ROOMS,

    SUM (room_revenue) ROOM_REVENUE,

    market_code

FROM(

 SELECT

            CONSIDERED_MONTH,

            CONSIDERED_YEAR,

            CONSIDERED_DATE,

            MARKET_GROUP,

            MARKET_GROUP_DESC,

            MARKET_CODE,

            SUM (no_rooms) NO_ROOMS,

            SUM (room_revenue) ROOM_REVENUE

 FROM(

 SELECT

                to_char (rsf.Considered_date,'MONTH') CONSIDERED_MONTH,

                to_char (rsf.Considered_date,'RRRR') CONSIDERED_YEAR,

                mc.parent_market_code MARKET_GROUP,

                mg.description MARKET_GROUP_DESC,

                rsf.market_code MARKET_CODE,

                rsf.considered_date CONSIDERED_DATE,

                decode (rsf.room_category,-1,0, rsf.no_rooms) NO_ROOMS,

                rsf.net_room_revenue ROOM_REVENUE

 FROM

                rep_res_statistics_forecast rsf, markets mc, market_groups mg

 WHERE

                (rsf.CONSIDERED_DATE BETWEEN TO_CHAR (SYSDATE -TO_CHAR (sysdate-1,'DD')) and TO_CHAR (SYSDATE+135))

 AND (mc.Parent_market_code = mg.Market_group AND rsf.Market_code (+) = mc.Market_code)

 AND rsf.deduct_yn='Y'

        )

 GROUP  BY

            CONSIDERED_MONTH,

            CONSIDERED_YEAR,

            CONSIDERED_DATE,

            MARKET_GROUP,

            MARKET_GROUP_DESC,

            MARKET_CODE

 ORDER  BY

            CONSIDERED_MONTH,

            CONSIDERED_YEAR,

            CONSIDERED_DATE,

            MARKET_GROUP,

            MARKET_GROUP_DESC,

            MARKET_CODE

)

GROUP  BY

    CONSIDERED_MONTH, CONSIDERED_YEAR, MARKET_GROUP, MARKET_GROUP_DESC, market_code

ORDER  BY

    CONSIDERED_MONTH,

    CONSIDERED_YEAR,

    MARKET_GROUP,

    MARKET_Code

--Bookings per day

SELECT a.business_date_created as Fch_Reserva, a.trunc_arrival as Arrival, a.trunc_departure as Output, a.nights,

       a.room_category_label as Room, a.share_amount as rate, a.rate_code, a.guarantee_code,

   a.sfirst_guest_name as names, a.guest_name as last name, a.company_name, a.travel_agent_name,

   b.srep_code as Executive, a.share_amount

FROM reservation_general_view a, name_view b

WHERE a.room_category_label<>'PM' and

     a.resv_status<>'CANCELLED'  and

     a.share_amount >  0.00  and

     b.name_id (+)= decode (a.company_id,null, a.travel_agent_id, a.company_id) and

     a.business_date_created =TO_CHAR (pms_p.business_date)

ORDER  BY a.trunc_arrival    

--Production by sales executive

 SELECT  a.room_revenue, a.share_amount, b.srep_code, a.rate_code,

        a.sfirst_guest_name ||  ''  || a.guest_name as names,

        a.trunc_arrival, a.trunc_departure, a.company_name, a.origin_of_booking, a.guarantee_code

 FROM reservation_general_view a, name_view b

 WHERE a.guarantee_code not  in ('G01', 'G02') and

          a.resv_status<>'CANCELLED'  and

          a.share_amount >  0.00  and

          b.name_id = decode (a.company_id,null, a.travel_agent_id, a.company_id) and

         (a.trunc_departure > = TO_CHAR (SYSDATE))

UNION  ALL

 SELECT a.available_revenue, a.avg_rate, a.owner_code, a.rate_code,

 'BLK'  || a.description,

        a.begin_date, a.end_date, a.acc_name, a.source, a.guarantee_code

 FROM   sc_busblock_info to     

 WHERE  a.status<>'C' and

           a.available_rooms>0  and

           a.avg_rate >0  and a.guarantee_code not  in ('G01', 'G02')

--Production per room

SELECT  'F' HF, to_char (a.Trunc_arrival,'DD') DD, to_char (a.Trunc_arrival,'MM') MM, to_char (a.Trunc_arrival,'YYYY') YY,

       a.nights Nights, a.room_category CRoom, a.share_amount Rate, b.srep_code Owner,

       a.trunc_arrival Arrival, a.trunc_departure Departure, a.company_name Company

 FROM  reservation_general_view a, name_view b

 WHERE a.resv_status<>'CANCELLED'  and a.share_amount >  0.00  and

             b.name_id = decode (a.company_id,null, a.travel_agent_id, a.company_id) and

            (a.trunc_departure > = TO_CHAR (SYSDATE))

UNION  ALL

SELECT  'F', to_char (a.Begin_date,'DD') DD, to_char (a.Begin_date,'MM') MM, to_char (a.Begin_date,'YYYY') AA,

       round (a.Available_revenue/a.Avg_rate,0),

 'BLOCK' CRoom, a.avg_rate, a.owner_code, a.begin_date, a.end_date, a.acc_name

 FROM  sc_busblock_info to     

 WHERE a.status<>'C'  and a.available_rooms>0  and a.avg_rate >0

UNION  ALL

SELECT  'H', to_char (rsd.Business_date,'DD') DD, to_char (rsd.Business_date,'MM') MM, to_char (rsd.Business_date,'YYYY') YY,

 1 nights, rsd.room_category CRoom, rsd.room_revenue ROOM_REVENUE, au.app_user CIA_OWNER, rsd.trunc_begin_date,

       rsd.business_date BUSINESS_DATE, n2.company

 FROMreservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

 WHERE  no.name_id = rsd.company_id and  no.primary_yn =  'AND'

 and au.person_name_id =  no.user_id and rsd.market_code<>'80C'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id (+) = rsd.name_id and n2.name_id (+) = rsd.company_id

 and rsd.room_revenue>0

UNION  ALL

SELECT  'H', to_char (rsd.Business_date,'DD') DD, to_char (rsd.Business_date,'MM') MM, to_char (rsd.Business_date,'YYYY') YY,

 1 nights, rsd.room_category CRoom, rsd.room_revenue ROOM_REVENUE, au.app_user CIA_OWNER, rsd.trunc_begin_date,

       rsd.business_date BUSINESS_DATE, n2.company

 FROMreservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

 WHERE rsd.company_id is  null and  no.name_id = rsd.agent_id

 and  no.primary_yn =  'AND' and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW' and rsd.resv_status <>  'CHECKED OUT')

 and n1.name_id (+) = rsd.name_id and n2.name_id (+) = rsd.agent_id

 and rsd.room_revenue<>0

 ORDER  BY AA, MM, DD, CRoom

--Production by sales executive

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

    au.app_user CIA_OWNER,

    rsd.rate_code RATE_CODE,

    initcap (n1.sname||','||n1.sfirst) GUEST_NAME,

    to_char (rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char (rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n2.company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

 no.name_id = rsd.company_id

 and  no.primary_yn =  'AND'

 and au.person_name_id =  no.user_id

 and rsd.market_code<>'80C'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id (+) = rsd.name_id

 and n2.name_id (+) = rsd.company_id

 and rsd.room_revenue>0

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

    au.app_user CIA_OWNER,

    rsd.rate_code RATE_CODE,

    initcap (n1.sname||','||n1.sfirst) GUEST_NAME,

    to_char (rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char (rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n2.company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

 no.name_id = rsd.company_id

 and  no.primary_yn =  'AND'

 and au.person_name_id =  no.user_id

 and rsd.market_code<>'80C'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id (+) = rsd.name_id

 and n2.name_id (+) = rsd.company_id

 and rsd.room_revenue<0

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

    au.app_user CIA_OWNER,

    rsd.rate_code RATE_CODE,

    initcap(n1.sname||','||n1.sfirst) GUEST_NAME,

    to_char(rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char(rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n2.company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

    rsd.company_id is  null

 and  no.name_id = rsd.agent_id

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW'  and rsd.resv_status <>  'CHECKED OUT')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.agent_id

 and rsd.room_revenue<>0

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

 'SUPERVISOR' CIA_OWNER,

    rsd.rate_code RATE_CODE,

 '*** NO DISPONIBLE ***' GUEST_NAME,

    to_char(rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char(rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n1.display_name company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

    reservation_stat_daily rsd,name_view n1

WHERE

    n1.name_id(+) = rsd.name_id

 and rsd.market_main_group='900'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and rsd.company_id is  NULL

 and rsd.room_revenue>0

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

 'SUPERVISOR'  CIA_OWNER,

    rsd.rate_code RATE_CODE,

 '*** NO DISPONIBLE ***' GUEST_NAME,

    to_char(rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char(rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n1.display_name company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

    reservation_stat_daily rsd,name_view n1

WHERE

    n1.name_id(+) = rsd.name_id

 and rsd.market_main_group='900'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and rsd.company_id is  NULL

 and rsd.room_revenue<0

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

    au.app_user CIA_OWNER,

    rsd.rate_code RATE_CODE,

    initcap(n1.sname||','||n1.sfirst) GUEST_NAME,

    to_char(rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char(rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n2.company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

    to_char(rsd.business_date,'RRRR') =  2018

 and to_char(rsd.business_date,'MM') =  '12'

 and  no.name_id = rsd.company_id

 and  no.primary_yn =  'Y'

 and rsd.nights>0

 and au.person_name_id =  no.user_id

 and substr(rsd.market_code,1,2)='80'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.company_id

 and rsd.room_revenue=0

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    rsd.room_revenue ROOM_REVENUE,

    alh.rms_owner_code CIA_OWNER,

    rsd.rate_code RATE_CODE,

    initcap(n1.sname||','||n1.sfirst) GUEST_NAME,

    to_char(rsd.trunc_begin_date,'DD-MM-RR') ARRIVAL,

    to_char(rsd.trunc_end_date,'DD-MM-RR') DEPARTURE,

    n2.company,

    rsd.source_code,

    rsd.market_code,

    rsd.room,

    rsd.room_category

FROM

reservation_stat_daily rsd, name n1, name n2, allotment$header alh

WHERE

    rsd.company_id is  NULL

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and rsd.room_revenue>0

 and n1.name_id = rsd.name_id

 and alh.allotment_header_id = rsd.allotment_header_id

 and n2.name_id =  alh.company_name_id

ORDER  BY arrival,departure

--Producción por ejecutivo detallado

SELECT

    rsd.business_date BUSINESS_DATE,

    to_char(rsd.business_date,'MM') MONTH,

    to_char(rsd.business_date,'RRRR') YEAR,

    rsd.stay_rooms STAY_ROOMS,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname) CIA_NAME,

    au.app_user CIA_OWNER,

    rsd.rate_code RATE_CODE,

    rsd.room_revenue ROOM_REVENUE,

    n2.industry_code,

    rsd.source_code

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

    rsd.business_date>=TO_CHAR(pms_p.business_date-30)

 and  no.name_id = rsd.company_id

 and rsd.room_revenue<>0

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.company_id

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    to_char(rsd.business_date,'MM') MONTH,

    to_char(rsd.business_date,'RRRR') YEAR,

    rsd.stay_rooms STAY_ROOMS,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname) CIA_NAME,

    au.app_user CIA_OWNER,

    rsd.rate_code RATE_CODE,

    rsd.room_revenue ROOM_REVENUE,

    n2.industry_code,

    rsd.source_code

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

    rsd.business_date>=TO_CHAR(pms_p.business_date-30)

 and  rsd.company_id is  null

 and  no.name_id = rsd.agent_id

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW'  and rsd.resv_status <>  'CHECKED OUT')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.agent_id

 and rsd.room_revenue<>0

--Producción por ejecutivo agrupado

SELECT

  au.app_user ,sum(rsd.room_revenue)

FROM

reservation_stat_daily rsd, name_owner no, application$_user au

WHERE

 no.name_id = rsd.company_id

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and rsd.market_code<>'80C'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and rsd.room_revenue<>0

 group  by au.app_user

UNION  ALL

SELECT

  au.app_user,sum(rsd.room_revenue)

 FROM

reservation_stat_daily rsd, name_owner no, application$_user au

 WHERE

  rsd.company_id is  null

 and  no.name_id = rsd.agent_id

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW'  and rsd.resv_status <>  'CHECKED OUT')

 and rsd.room_revenue<>0

 group  by au.app_user

--Forecast agrupado por fecha

 SELECT a.considered_date,sum(a.no_rooms), sum(a.arrival_rooms),sum(a.departure_rooms),sum(a.complimentary_rooms),

       sum(a.net_room_revenue)

 FROM rep_res_statistics_forecast a

 WHERE ( EXTRACT(YEAR  FROM a.CONSIDERED_DATE) =  2019 ) and a.ROOM_CATEGORY IS  NOT  NULL

 GROUP  BY a.CONSIDERED_DATE

UNION  ALL

 SELECT a.considered_date,sum(a.no_rooms), sum(a.arrival_rooms),sum(a.departure_rooms),sum(a.complimentary_rooms),

       sum(a.net_room_revenue)

 FROM rep_res_statistics_forecast a

 WHERE ( EXTRACT(YEAR  FROM a.CONSIDERED_DATE) =  2019 ) and a.ROOM_CATEGORY IS  NOT  NULL

 and (a.group_yn='N'  or (a.group_yn='Y'  and a.deduct_yn='Y'))

 GROUP  BY a.CONSIDERED_DATE

--Producción por empresa y por tipo de habitación

SELECT to_char(rsd.business_date,'RRRR'),to_char(rsd.business_date,'MM'),rsd.company_id,rsd.room,rsd.room_category,sum(rsd.room_revenue),sum(rsd.room_adults)

FROM

  reservation_stat_daily rsd

WHERE

  to_char(rsd.business_date,'RRRR') >=  2010

 AND Rsd.market_code<>'80C'

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and rsd.room_revenue<>0

 group  by to_char(rsd.business_date,'RRRR'),to_char(rsd.business_date,'MM'),rsd.company_id,rsd.room,rsd.room_category

 order  by to_char(rsd.business_date,'RRRR'),to_char(rsd.business_date,'MM'),rsd.company_id,rsd.room

--Producción mensual por market y por ejecutivo

SELECT

    rsd.business_date BUSINESS_DATE,

    to_char(rsd.business_date,'MM') MONTH,

    to_char(rsd.business_date,'RRRR') YEAR,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname) CIA_NAME,

    rsd.market_main_group MARKET_GRP,

    rsd.market_code,

    n2.industry_code,

    au.app_user OWNER,

    rsd.rate_code RATE_CODE,

    sum(rsd.room_revenue) ROOM_REVENUE,sum(rsd.stay_rooms) ROOMS

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

    rsd.business_date=TO_CHAR(pms_p.business_date-2)

 and  no.name_id = rsd.company_id

 and rsd.room_revenue<>0

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.company_id

GROUP  BY

    rsd.business_date,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname),

    rsd.market_main_group,

    rsd.market_code,

    n2.industry_code,

    au.app_user,

    rsd.rate_code

UNION  ALL

SELECT

    rsd.business_date BUSINESS_DATE,

    to_char(rsd.business_date,'MM') MONTH,

    to_char(rsd.business_date,'RRRR') YEAR,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname) CIA_NAME,

    rsd.market_main_group MARKET_GRP,

    rsd.market_code,

    n2.industry_code,

    au.app_user OWNER,

    rsd.rate_code RATE_CODE,

    sum(rsd.room_revenue) ROOM_REVENUE,sum(rsd.stay_rooms) ROOMS

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE

    rsd.business_date=TO_CHAR(pms_p.business_date-2)

 and  rsd.company_id is  null

 and  no.name_id = rsd.agent_id

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW'  and rsd.resv_status <>  'CHECKED OUT')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.agent_id

 and rsd.room_revenue<>0

GROUP  BY

    rsd.business_date,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname),

    rsd.market_main_group,

    rsd.market_code,

    n2.industry_code,

    au.app_user,

    rsd.rate_code

--Producción por ejecutivo, habitación y empresa

SELECT

    rsd.room,n1.last,

    rsd.business_date BUSINESS_DATE,

    to_char(rsd.business_date,'MM') MONTH,

    to_char(rsd.business_date,'RRRR') YEAR,

    rsd.stay_rooms STAY_ROOMS,

    decode(n2.sname,NULL,'SIN COMPAÑIA',n2.sname) CIA_NAME,

    au.app_user CIA_OWNER,

    rsd.room_revenue ROOM_REVENUE,

    rsd.source_code

FROM

reservation_stat_daily rsd, name_owner no, application$_user au, name n1, name n2

WHERE  no.name_id = rsd.company_id

 and rsd.room_revenue<>0

 and  no.primary_yn =  'Y'

 and au.person_name_id =  no.user_id

 and (rsd.resv_status <>  'CANCELLED'  and rsd.resv_status <>  'NO SHOW')

 and n1.name_id(+) = rsd.name_id

 and n2.name_id(+) = rsd.company_id

order  by BUSINESS_DATE,room

--Forecast por Market Code Mensual Detallado

SELECT

    CONSIDERED_MONTH,

    CONSIDERED_YEAR,

    CONSIDERED_DATE,

    MARKET_GROUP,

    MARKET_GROUP_DESC,

    MARKET_CODE,

    NO_ROOMS,

    ROOM_REVENUE

FROM(

 SELECT

        to_char(rsf.considered_date,'MONTH') CONSIDERED_MONTH,

        to_char(rsf.considered_date,'RRRR') CONSIDERED_YEAR,

        mc.parent_market_code MARKET_GROUP,

        mg.description MARKET_GROUP_DESC,

        rsf.market_code MARKET_CODE,

        rsf.considered_date CONSIDERED_DATE,

        decode(rsf.room_category,-1,0,rsf.no_rooms) NO_ROOMS,

        rsf.net_room_revenue ROOM_REVENUE

 FROM

        rep_res_statistics_forecast rsf, markets mc, market_groups mg

 WHERE

        (year(rsf.CONSIDERED_DATE) =2019 )

 AND (mc.parent_market_code = mg.market_group AND rsf.market_code(+) = mc.market_code )

    )

--Activity Search - Notas por ejecutivo y huesped

SELECT a.salesrep,a.insert_date, a.act_type, a.purpose,a.acc_name, a.con_name, a.notes,a.problem_desc

 FROM activity_search a

 WHERE a.insert_date>= sysdate-1

 ORDER  BY a.insert_date

--Reservas canceladas

SELECT a.nights*a.share_amount as trevenue, a.nights,b.srep_code,a.rate_code,a.sfirst_guest_name ||  ' '  || a.guest_name as nombres, a.trunc_arrival, a.trunc_departure,

    b.name,a.cancellation_reason_desc

FROM reservation_general_view a, name_view b

WHERE a.resv_status='CANCELLED'

 and a.booked_room_category_label<>'PM'

 and substr(a.cancellation_date,1,11)>=TO_CHAR(SYSDATE-10)

 and b.name_id = decode(a.company_id,null,a.travel_agent_id,a.company_id)

ORDER  BY a.trunc_arrival

--Contactos por empresa

SELECT a.name  as Apellidos,a.first  as Nombre,a.udfc10 ,a.udfd11 as sexo,a.title as Trato,

   a.business_title as Cargo,a.email,a.name_id as Key_con_Cia,a.company Razon_Social,a.udfc12 as Nbr_Comercial,

   a.address1 as Direccion,a.city as Distrito, a.udfc13 as Rubro, a.srep_code as  Owner,a.phone_no as Telefono,

   a.mobile_phone_number as Celular,a.udfc14,a.udfc15,a.udfc16,a.udfc01 as DClub

FROM name_view a

WHERE a.tracecode='CON'  and a.active_yn='Y'  and a.country='PE'

ORDER  BY a.name

# Creación de Kardex físico valorado en Material Controls Micros Fidelio

create  or  replace  PROCEDURE SP_KARDEX_FISICO_VALORADO(

vn_kst_id IN MCDATA.KOSTST.KST_ID%TYPE,

vn_art_id IN MCDATA.ARTIKEL.ART_ID%TYPE,

vs_tipo IN  CHAR,

vs_fec_ini IN varchar2,

vs_fec_fin IN varchar2,

P_OUT_ID_GTT_KARDEX OUT NUMBER

)

IS

-----------------------------------------------------------------------------------------------

-- PROCEDIMIENTO DE GENERACION DE KARDEX FISICO VALORADO

-- VERSION : Micros Fidelio :: Materials Control v 8.6.5.10

-----------------------------------------------------------------------------------------------

CURSOR SC_ARTICULOS IS

--COMPRAS O DEVOLUCIONES (10)

SELECT K.KST_ID,

       K.KST_ADRESSE,

       K.KST_NAME,

       I.ART_ID,

       A.ART_NUMMER AS ART_COD,

       A.ART_NAME,

       unidad_code_sunat(A.VPK_NR) VPK_NR,

       VP.VPK_NAME,

       A.ART_INFO,

       I.WES_TYP,

 '01'  AS TIPO_OPE,

       I.WES_ID1,

       I.WES_ID2,

       L.lfs_datum WES_DOCDATE,

       DECODE(L.LFS_STATUS,42,

             (CASE  TRIM(SUBSTR(TRIM(MCDATA.F_FACT_NAME(L.LFS_ID)),1,3))

 WHEN  'F' THEN  '01'  --FACTURA

 WHEN  'B' THEN  '03'  --BOLETA DE VENTA

 WHEN  'LC' THEN  '04'  --LIQUIDACIÓN DE COMPRA

 WHEN  'NCP'  THEN  '07'  --NOTA DE CREDITO

 WHEN  'NDP'  THEN  '08'  --NOTA DE DEBITO             

 WHEN  'GRE'  THEN  '09'  --GUÍA DE REMISIÓN Remitente

 WHEN  'TK' THEN  '12'  --TICKET

 WHEN  'RET'  THEN  '20'  --Retencion

 WHEN  'GT' THEN  '31'  --GUÍA DE REMISIÓN Transportista

 WHEN  'OT' THEN  '99'  --Otros

 WHEN  'I' THEN  '16'  --INVEMTARIO

 ELSE  '01'

 END),

             (CASE  TRIM(SUBSTR(TRIM(L.LFS_NAME),1,3))

 WHEN  'F' THEN  '01'  --FACTURA

 WHEN  'B' THEN  '03'  --BOLETA DE VENTA

 WHEN  'LC' THEN  '04'  --LIQUIDACIÓN DE COMPRA

 WHEN  'NCP'  THEN  '07'  --NOTA DE CREDITO

 WHEN  'NDP'  THEN  '08'  --NOTA DE DEBITO             

 WHEN  'GRE'  THEN  '09'  --GUÍA DE REMISIÓN Remitente

 WHEN  'TK' THEN  '12'  --TICKET

 WHEN  'RET'  THEN  '20'  --Retencion

 WHEN  'GT' THEN  '31'  --GUÍA DE REMISIÓN Transportista

 WHEN  'OT' THEN  '99'  --Otros

 WHEN  'I' THEN  '16'  --INVEMTARIO

 ELSE  '01'

 END))AS TIPO_DOC,

       DECODE(L.LFS_STATUS,42,SUBSTR(MCDATA.F_FACT_NAME(L.LFS_ID),2,3),SUBSTR(L.LFS_NAME,2,3)) AS SERIE_DOC,

       DECODE(L.LFS_STATUS,42,SUBSTR(MCDATA.F_FACT_NAME(L.LFS_ID),6,LENGTH(MCDATA.F_FACT_NAME(L.LFS_ID))),SUBSTR(L.LFS_NAME,6,LENGTH(L.LFS_NAME))) AS NRO_DOC,

       ROUND(I.WES_MENGE,4) AS CANT_COMPRA,

       ROUND(I.WES_ESP,4) AS COST_UNI_COMPRA,

       ROUND(I.WES_MENGE * I.WES_ESP,4) AS COST_TOT_COMPRA,

 0.00  AS CANT_VENTA,

 0.00  AS COST_UNI_VENTA,

 0.00  AS COST_TOT_VENTA,

       I.WES_VKP,

       L.LFS_STATUS,

       (SELECT NVL(COUNT(1),0)

 FROM MCDATA.LIEFERPOS T

 WHERE T.LFP_MENGE <  0  AND T.LFP_STATUS <>  64

 AND T.LFS_ID = L.LFS_ID) AS LFP_STATUS

 FROM MCDATA.INVWES I,

       MCDATA.ARTIKEL A,

       MCDATA.VPCKEINH VP,

       MCDATA.KOSTST K,

       MCDATA.LIEFERSCHEIN L

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_ID1 = L.LFS_ID )

 AND ( I.WES_TYP =  10 )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ((L.lfs_datum >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (L.lfs_datum <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

UNION  ALL

-- COMPRAS EN CONTABILIDAD

SELECT K.KST_ID,

       K.KST_ADRESSE,

       K.KST_NAME,

       I.ART_ID,

       A.ART_NUMMER AS ART_COD,

       A.ART_NAME,

       unidad_code_sunat(A.VPK_NR) VPK_NR,

       VP.VPK_NAME,

       A.ART_INFO,

       I.WES_TYP,

 '02'AS TIPO_OPE,

       I.WES_ID1,

       I.WES_ID2,

       RE.RNG_DATUM WES_DOCDATE,

       (CASE  TRIM(SUBSTR(TRIM(RE.RNG_NAME) ,1,3))

 WHEN  'F' THEN  '01'  --FACTURA

 WHEN  'B' THEN  '03'  --BOLETA DE VENTA

 WHEN  'LC' THEN  '04'  --LIQUIDACIÓN DE COMPRA

 WHEN  'NCP'  THEN  '07'  --NOTA DE CREDITO

 WHEN  'NDP'  THEN  '08'  --NOTA DE DEBITO             

 WHEN  'GRE'  THEN  '09'  --GUÍA DE REMISIÓN Remitente

 WHEN  'TK' THEN  '12'  --TICKET

 WHEN  'RET'  THEN  '20'  --Retencion

 WHEN  'GT' THEN  '31'  --GUÍA DE REMISIÓN Transportista

 WHEN  'OT' THEN  '99'  --Otros

 WHEN  'I' THEN  '16'  --INVEMTARIO

 ELSE  '01'

 END)AS TIPO_DOC,

       SUBSTR(RE.RNG_NAME,INSTR(RE.RNG_NAME,' '),INSTR(RE.RNG_NAME,'-')-INSTR(RE.RNG_NAME,' ')) AS SERIE_DOC,

       SUBSTR(RE.RNG_NAME,INSTR(RE.RNG_NAME,'-')+1,LENGTH(RE.RNG_NAME)) AS NRO_DOC,

       ROUND(I.WES_MENGE,4) AS CANT_COMPRA,

       ROUND(I.WES_ESP,4) AS COST_UNI_COMPRA,

       ROUND(I.WES_MENGE * I.WES_ESP,4) AS COST_TOT_COMPRA,

 0.00  AS CANT_VENTA,

 0.00  AS COST_UNI_VENTA,

 0.00  AS COST_TOT_VENTA,

       I.WES_VKP,

       RE.RNG_STATUS,

       (SELECT NVL(COUNT(1),0)

 FROM MCDATA.LIEFERPOS T

 WHERE T.LFP_MENGE <  0  AND T.LFP_STATUS <>  64

 AND T.LFS_ID = I.WES_ID1) AS LFP_STATUS

 FROM MCDATA.INVWES I,

       MCDATA.ARTIKEL A,

       MCDATA.VPCKEINH VP,

       MCDATA.KOSTST K,

       MCDATA.RECHNUNG RE

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_TYP =  10 )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ( (RE.RNG_DATUM >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (RE.RNG_DATUM <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

UNION  ALL

--TRASFERENCIAS DE ALMACEN (2)

SELECT K.KST_ID,

       K.KST_ADRESSE,

       K.KST_NAME,

       I.ART_ID,

       A.ART_NUMMER AS ART_COD,

       A.ART_NAME,

       unidad_code_sunat(A.VPK_NR) VPK_NR,

       VP.VPK_NAME,

       A.ART_INFO,

       I.WES_TYP,

 '11'  AS TIPO_OPE,

       I.WES_ID1,

       I.WES_ID2,

       HL.LBW_DATUM WES_DOCDATE,

 '00'  AS TIPO_DOC,

 TRIM(SUBSTR(HL.LBW_NAME,1,6)) AS SERIE_DOC,

 TRIM(HL.LBW_NAME) AS NRO_DOC,

       ROUND(I.WES_MENGE,4) AS CANT_COMPRA,

       ROUND(I.WES_ESP,4) AS COST_UNI_COMPRA,

       ROUND(I.WES_MENGE * I.WES_ESP,4) AS COST_TOT_COMPRA,

 0.00  AS CANT_VENTA,

 0.00  AS COST_UNI_VENTA,

 0.00  AS COST_TOT_VENTA,

       I.WES_VKP,

       HL.LBW_STATUS AS LFS_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

       MCDATA.ARTIKEL A,

       MCDATA.VPCKEINH VP,

       MCDATA.KOSTST K,

       MCDATA.HIS_LAGERBEW HL

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_ID1 = HL.LBW_ID )

 AND ( I.WES_TYP=2 )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ((HL.LBW_DATUM >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (HL.LBW_DATUM <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

UNION  ALL

--SALIDAS (1)

SELECT K.KST_ID,

       K.KST_ADRESSE,

       K.KST_NAME,

       I.ART_ID,

       A.ART_NUMMER AS ART_COD,

       A.ART_NAME,

       unidad_code_sunat(A.VPK_NR) VPK_NR,

       VP.VPK_NAME,

       A.ART_INFO,

       I.WES_TYP,

 '11'  AS TIPO_OPE,

       I.WES_ID1,

       I.WES_ID2,

       HL.LBW_DATUM WES_DOCDATE,

 '00'  AS TIPO_DOC,

 TRIM(SUBSTR(HL.LBW_NAME,1,6)) AS SERIE_DOC,

 TRIM(HL.LBW_NAME) AS NRO_DOC,

 0.00  AS CANT_COMPRA,

 0.00  AS COST_UNI_COMPRA,

 0.00  AS COST_TOT_COMPRA,

       ROUND(I.WES_MENGE,4) AS CANT_VENTA,

       ROUND(I.WES_ESP,4) AS COST_UNI_VENTA,

       ROUND(I.WES_MENGE * I.WES_ESP,4) AS COST_TOT_VENTA,

       I.WES_VKP,

       HL.LBW_STATUS AS LFS_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

       MCDATA.ARTIKEL A,

       MCDATA.VPCKEINH VP,

       MCDATA.KOSTST K,

       MCDATA.HIS_LAGERBEW HL

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_ID1 = HL.LBW_ID )

 AND ( I.WES_TYP =1 )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ((HL.LBW_DATUM >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (HL.LBW_DATUM <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

UNION  ALL

-- MERMAS

SELECT K.KST_ID,

       K.KST_ADRESSE,

       K.KST_NAME,

       I.ART_ID,

       A.ART_NUMMER AS ART_COD,

       A.ART_NAME,

       unidad_code_sunat(A.VPK_NR) VPK_NR,

       VP.VPK_NAME,

       A.ART_INFO,

       I.WES_TYP,

 '05'  AS TIPO_OPE,

       I.WES_ID1,

       I.WES_ID2,

       HV.VBR_DATUM WES_DOCDATE,

 '00'  AS TIPO_DOC,

 TRIM(SUBSTR(VBR_NAME,1,7)) AS SERIE_DOC,

       HV.VBR_NAME AS NRO_DOC,

 0.00  AS CANT_COMPRA,

 0.00  AS COST_UNI_COMPRA,

 0.00  AS COST_TOT_COMPRA,

       ROUND(I.WES_MENGE,4) AS CANT_VENTA,

       ROUND(I.WES_ESP,4) AS COST_UNI_VENTA,

       ROUND(I.WES_MENGE * I.WES_ESP,4) AS COST_TOT_VENTA,

       I.WES_VKP,

       HV.VBR_STATUS AS LFS_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

       MCDATA.ARTIKEL A,

       MCDATA.VPCKEINH VP,

       MCDATA.KOSTST K,

       MCDATA.HIS_VERBRAUCH HV

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_TYP IN (30,31) )

 AND ( I.WES_ID1 = HV.VBR_ID )

 AND ( I.KST_ID = HV.KST_ID )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ( (HV.VBR_DATUM >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (HV.VBR_DATUM <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

UNION  ALL

--VENTAS

SELECT K.KST_ID,

       K.KST_ADRESSE,

       K.KST_NAME,

       I.ART_ID,

       A.ART_NUMMER AS ART_COD,

       A.ART_NAME,

       unidad_code_sunat(A.VPK_NR) VPK_NR,

       VP.VPK_NAME,

       A.ART_INFO,

       I.WES_TYP,

 '10'  AS TIPO_OPE,

       I.WES_ID1,

       I.WES_ID2,

       T.TAT_DATUM WES_DOCDATE,

 '00'  AS TIPO_DOC,

 TRIM(SUBSTR(T.TAT_NAME,1,6)) AS SERIE_DOC,

       T.TAT_NAME AS NRO_DOC,

 0.00  AS CANT_COMPRA,

 0.00  AS COST_UNI_COMPRA,

 0.00  AS COST_TOT_COMPRA,

       ROUND(I.WES_MENGE,4) AS CANT_VENTA,

       ROUND(I.WES_ESP,4) AS COST_UNI_VENTA,

       ROUND(I.WES_MENGE * I.WES_ESP,4) AS COST_TOT_VENTA,

       I.WES_VKP,

       AU.ATG_STATUS AS LFS_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

       MCDATA.ARTIKEL A,

       MCDATA.VPCKEINH VP,

       MCDATA.KOSTST K,

       MCDATA.TEILAUFTRAG T,

       MCDATA.AUFTRAG AU

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_TYP =  21 )

 AND ( I.WES_ID1 = T.TAT_ID )

 AND ( T.ATG_ID = AU.ATG_ID )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ( (T.TAT_DATUM >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (T.TAT_DATUM <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

UNION  ALL

-- AJUSTES DE INVENTARIO

 SELECT K.KST_ID,

           K.KST_ADRESSE,

           K.KST_NAME,

           I.ART_ID,

           A.ART_NUMMER AS ART_COD,

           A.ART_NAME,

           unidad_code_sunat(A.VPK_NR) VPK_NR,

           VP.VPK_NAME,

           A.ART_INFO,

           I.WES_TYP,

 '99'  AS TIPO_OPE,

           I.WES_ID1,

           I.WES_ID2,

           IV.INV_DATUM WES_DOCDATE,

 '00'  AS TIPO_DOC,

 TRIM(SUBSTR(INV_NAME,1,7)) AS SERIE_DOC,

           IV.INV_NAME AS NRO_DOC,

           DECODE(SIGN(I.WES_MENGE),1,ROUND(I.WES_MENGE,4),0.00) AS CANT_COMPRA,

           DECODE(SIGN(WES_MENGE),1,ROUND(I.WES_ESP,4),0.00) AS COST_UNI_COMPRA,

           DECODE(SIGN(ROUND(I.WES_MENGE * I.WES_ESP,4)),1,ROUND(I.WES_MENGE * I.WES_ESP,4),0.00) AS COST_TOT_COMPRA,

           DECODE(SIGN(I.WES_MENGE),-1,ROUND(I.WES_MENGE,4),0.00) AS CANT_VENTA,

           DECODE(SIGN(WES_MENGE),-1,ROUND(I.WES_ESP,4),0.00) AS COST_UNI_VENTA,

           DECODE(SIGN(ROUND(I.WES_MENGE * I.WES_ESP,4)),-1,ROUND(I.WES_MENGE * I.WES_ESP,4),0.00) AS COST_TOT_VENTA,

           I.WES_VKP,

           IV.INV_STATUS AS LFS_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

           MCDATA.INVENTUR IV,

           MCDATA.ARTIKEL A,

           MCDATA.VPCKEINH VP,

           MCDATA.KOSTST K

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_ID1 = IV.INV_ID )

 AND ( I.WES_TYP =  50 )

 AND ( IV.INV_TYP IN (1,22) )

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id )

 AND ((IV.INV_DATUM >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (IV.INV_DATUM <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

 UNION  ALL

 SELECT K.KST_ID,

                   K.KST_ADRESSE,

                   K.KST_NAME,

                   I.ART_ID,

                   A.ART_NUMMER AS ART_COD,

                   A.ART_NAME,

                   unidad_code_sunat(A.VPK_NR) VPK_NR,

                   VP.VPK_NAME,

                   A.ART_INFO,

                   I.WES_TYP,

 '10'AS TIPO_OPE,

                   I.WES_ID1,

                   I.WES_ID2,

                   I.wes_datum WES_DOCDATE,

 '00'  AS TIPO_DOC,

 'MNPR1'  AS SERIE_DOC,

 'MNPR'||TO_CHAR(I.wes_datum, 'YYYYMMDD') AS NRO_DOC,

                   ROUND(I.WES_MENGE,4) AS CANT_COMPRA,

                   NVL(ROUND(art_wes_esp(I.KST_ID,I.ART_ID,I.wes_datum),4),0.00) AS COST_UNI_COMPRA,

                   ROUND(I.WES_MENGE * art_wes_esp(I.KST_ID,I.ART_ID,I.wes_datum),4) AS COST_TOT_COMPRA,

 0.00  AS CANT_VENTA,

 0.00  AS COST_UNI_VENTA,

 0.00  AS COST_TOT_VENTA,

                   I.WES_VKP,

 0 RNG_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

                   MCDATA.ARTIKEL A,

                   MCDATA.VPCKEINH VP,

                   MCDATA.KOSTST K

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_TYP=62)

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id)

 AND ((I.wes_datum >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (I.wes_datum <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

 UNION  ALL

 SELECT K.KST_ID,

               K.KST_ADRESSE,

               K.KST_NAME,

               I.ART_ID,

               A.ART_NUMMER AS ART_COD,

               A.ART_NAME,

               unidad_code_sunat(A.VPK_NR) VPK_NR,

               VP.VPK_NAME,

               A.ART_INFO,

               I.WES_TYP,

 '10'AS TIPO_OPE,

               I.WES_ID1,

               I.WES_ID2,

               I.wes_datum WES_DOCDATE,

 '00'  AS TIPO_DOC,

 'MNPR2'  AS SERIE_DOC,

 'MNPR'||TO_CHAR(I.wes_datum, 'YYYYMMDD') AS NRO_DOC,

 0.00  AS CANT_COMPRA,

 0.00  AS COST_UNI_COMPRA,

 0.00  AS COST_TOT_COMPRA,

               ROUND(I.WES_MENGE,4) AS CANT_VENTA,

               NVL(ROUND(art_wes_esp(I.KST_ID,I.ART_ID,I.wes_datum),4),0.00) AS COST_UNI_VENTA,

               ROUND(I.WES_MENGE * art_wes_esp(I.KST_ID,I.ART_ID,I.wes_datum),4) AS COST_TOT_VENTA,

               I.WES_VKP,

 0 RNG_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

               MCDATA.ARTIKEL A,

               MCDATA.VPCKEINH VP,

               MCDATA.KOSTST K

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_TYP in (63))

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id)

 AND ((I.wes_datum >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (I.wes_datum <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

 UNION  ALL

 SELECT K.KST_ID,

               K.KST_ADRESSE,

               K.KST_NAME,

               I.ART_ID,

               A.ART_NUMMER AS ART_COD,

               A.ART_NAME,

               unidad_code_sunat(A.VPK_NR) VPK_NR,

               VP.VPK_NAME,

               A.ART_INFO,

               I.WES_TYP,

 '10'AS TIPO_OPE,

               I.WES_ID1,

               I.WES_ID2,

               I.wes_datum WES_DOCDATE,

 '00'  AS TIPO_DOC,

 'MNPR3'  AS SERIE_DOC,

 'MNPR'||TO_CHAR(I.wes_datum, 'YYYYMMDD') AS NRO_DOC,

 0.00  AS CANT_COMPRA,

 0.00  AS COST_UNI_COMPRA,

 0.00  AS COST_TOT_COMPRA,

               ROUND(I.WES_MENGE,4) AS CANT_VENTA,

               NVL(ROUND(art_wes_esp(I.KST_ID,I.ART_ID,I.wes_datum),4),0.00) AS COST_UNI_VENTA,

               ROUND(I.WES_MENGE * art_wes_esp(I.KST_ID,I.ART_ID,I.wes_datum),4) AS COST_TOT_VENTA,

               I.WES_VKP,

 0 RNG_STATUS,

 0  AS LFP_STATUS

 FROM MCDATA.INVWES I,

               MCDATA.ARTIKEL A,

               MCDATA.VPCKEINH VP,

               MCDATA.KOSTST K

 WHERE ( I.ART_ID = A.ART_ID )

 AND ( I.KST_ID = K.KST_ID )

 AND ( A.VPK_NR = VP.VPK_ID )

 AND ( I.WES_TYP in (64))

 AND ( I.ART_ID = vn_art_id OR vn_art_id=0 )

 AND ( K.KST_ID = vn_kst_id)

 AND ((I.wes_datum >= TO_DATE(vs_fec_ini||'00:00:00', 'DD/MM/YYYY HH24:MI:SS'))

 AND (I.wes_datum <= TO_DATE(vs_fec_fin||'23:59:59', 'DD/MM/YYYY HH24:MI:SS')))

 ORDER  BY ART_NAME,WES_DOCDATE, NRO_DOC ASC;

ln_cant_tota NUMBER(14,4);

ln_cost_tota NUMBER(14,4);

ln_cost_uni_tota NUMBER(14,4);

ld_inv_datum MCDATA.INVENTUR.INV_DATUM%TYPE;

ls_inv_name MCDATA.INVENTUR.INV_NAME%TYPE;

ln_inv_status MCDATA.INVENTUR.INV_STATUS%TYPE;

ln_inv_ist MCDATA.INVPOSART.INP_IST%TYPE;

ln_inv_esp MCDATA.INVPOSART.INP_ESP%TYPE;

ln_total NUMBER(14,2);

ln_inv_id NUMBER;

ln_nError NUMBER;

ln_art_id NUMBER;

ls_cError LONG;

ls_mensaje VARCHAR2(250);

ls_tipo_ope VARCHAR2(2);

V_QUANTITY NUMBER;

V_ID_GTT_KARDEX NUMBER;

V_SUM_LAST_CNT_SLD_FIN NUMBER(14,2);

V_SUM_LAST_CST_TOT_SLD_FIN NUMBER(14,2);

BEGIN

ln_inv_ist :=  0;

ln_inv_esp :=  0;

ln_total :=  0;

ln_art_id :=  0;

V_QUANTITY :=  0; 

 select gtt_kardex_seq.nextval into V_ID_GTT_KARDEX from dual;

 FOR VC_ARTICULO IN SC_ARTICULOS LOOP

 IF ln_art_id <> VC_ARTICULO.ART_ID THEN

ln_cant_tota :=  0.00;

ln_cost_uni_tota :=  0.00;

ln_cost_tota :=  0.00;

ln_art_id := VC_ARTICULO.ART_ID;

 -- Inventario Inicial del Artículo.

 SELECT MAX(I.INV_ID) INTO ln_inv_id

 FROM MCDATA.INVENTUR I,

             MCDATA.INVPOSART IA

 WHERE I.INV_ID = IA.INV_ID

 AND I.KST_ID = vn_kst_id

 AND IA.ART_ID = ln_art_id

 AND I.INV_DATUM < TO_DATE(vs_fec_ini, 'DD/MM/YYYY');

 IF ln_inv_id >  0  THEN

 SELECT IA.INP_IST,IA.INP_ESP into ln_cant_tota,ln_cost_uni_tota

 FROM MCDATA.INVENTUR I, MCDATA.INVPOSART IA

 WHERE I.INV_ID = IA.INV_ID

 AND I.INV_ID = ln_inv_id

 AND I.KST_ID = vn_kst_id

 AND IA.ART_ID = ln_art_id

 AND I.INV_STATUS =  8  -- CERRADO

 AND I.INV_TYP <>  22; -- DIFERENTE A AJUSTE DE INVENTARIO

            ln_cant_tota:=NVL(ln_cant_tota,0);

            ln_cost_tota:=ln_cant_tota*ln_cost_uni_tota;

            ln_inv_ist:=ln_cant_tota;

            ln_inv_esp:=ln_cost_uni_tota;

            ln_total:=ln_cost_tota;

 INSERT  INTO MCDATA.GTT_KARDEX_VALORIZADO

                  (KST_ID,

                   KST_ADRESSE,

                   KST_NAME,

                   FEC_INI_PER,

                   FEC_FIN_PER,

                   ART_ID,

                   WES_TYP,

                   ART_COD,

                   ART_NAME,

                   ART_INFO,

               VPK_NR,

               VPK_NAME,

               TIPO_OPE,

               LFS_STATUS,

               LFP_STATUS,

               WES_ID1,

               WES_ID2,

                    WES_DOCDATE,

                    TIPO_DOC,

                    SERIE_DOC,

                    NRO_DOC,

                    CNT_COM,

               CST_UNI_COM,

               CST_TOT_COM,

               CNT_VTA,

               CST_UNI_VTA,

               CST_TOT_VTA,

                   CNT_SLD_FIN,

                   CST_UNI_SLD_FIN,

                   CST_TOT_SLD_FIN,

                   ID_GTT_KARDEX,

                   ID_GTT_KARDEX_VALORIZADO)

 VALUES

                  (VC_ARTICULO.KST_ID,

                   VC_ARTICULO.KST_ADRESSE,

                   VC_ARTICULO.KST_NAME,

TO_DATE(vs_fec_ini, 'DD/MM/YYYY'),

TO_DATE(vs_fec_fin, 'DD/MM/YYYY'),

                   VC_ARTICULO.ART_ID,

 0,

                   VC_ARTICULO.ART_COD,

                   VC_ARTICULO.ART_NAME,

                   VC_ARTICULO.ART_INFO,

 TRIM(VC_ARTICULO.VPK_NR),

               VC_ARTICULO.VPK_NAME,

 '16',

 0,

 0,

 null,

 0,

TO_DATE(vs_fec_ini, 'DD/MM/YYYY'),

 '',

 '',

 'INV INICIAL',

 NULL,

 NULL,

 NULL,

 NULL,

 NULL,

 NULL,

                   ln_inv_ist,

                   ln_inv_esp,

                   ln_total,

                   V_ID_GTT_KARDEX,

                   ID_GTT_KARDEX_VALORIZADO_SEQ.nextval);

 COMMIT;

 --Actualizamos Saldo

ln_cant_tota := ln_inv_ist;

ln_cost_tota := ln_cost_tota;

 END  IF;

 END  IF;

        ln_cant_tota:= ln_cant_tota + ROUND(NVL(VC_ARTICULO.CANT_COMPRA,0),4) + ROUND(NVL(VC_ARTICULO.CANT_VENTA,0),4);

        ln_cant_tota:=NVL(ln_cant_tota,0);

 IF (VC_ARTICULO.CANT_COMPRA>0) THEN

ln_cost_uni_tota := ROUND(VC_ARTICULO.COST_UNI_COMPRA,4);

 ELSE

 IF (VC_ARTICULO.CANT_VENTA>0) THEN

ln_cost_uni_tota := ROUND(VC_ARTICULO.COST_UNI_VENTA,4);

 ELSE

ln_cost_uni_tota :=  CASE  WHEN VC_ARTICULO.COST_UNI_VENTA>0  THEN ROUND(VC_ARTICULO.COST_UNI_VENTA,4) ELSE ROUND(VC_ARTICULO.COST_UNI_COMPRA,4) END;

 END  IF;

 END  IF;

ln_cost_tota := ln_cost_uni_tota*ln_cant_tota;

 --Tipo Operacion

 IF VC_ARTICULO.WES_TYP =  10  THEN

 IF VC_ARTICULO.LFP_STATUS =  0  THEN

ls_tipo_ope :=  '02'; -- COMPRA

 ELSE

ls_tipo_ope :=  '05'; -- DEVOLUCION

 END  IF;

 ELSE

ls_tipo_ope := VC_ARTICULO.TIPO_OPE;

 END  IF;

 INSERT  INTO MCDATA.GTT_KARDEX_VALORIZADO

              (KST_ID,

               KST_ADRESSE,

               KST_NAME,

               FEC_INI_PER,

               FEC_FIN_PER,

               ART_ID,

               WES_TYP,

               ART_COD,

               ART_NAME,

               ART_INFO,

           VPK_NR,

           VPK_NAME,

           TIPO_OPE,

           LFS_STATUS,

           LFP_STATUS,

           WES_ID1,

           WES_ID2,

           WES_DOCDATE,

           TIPO_DOC,

           SERIE_DOC,

           NRO_DOC,

           CNT_COM,

           CST_UNI_COM,

           CST_TOT_COM,

           CNT_VTA,

           CST_UNI_VTA,

           CST_TOT_VTA,

           CNT_SLD_FIN,

           CST_UNI_SLD_FIN,

           CST_TOT_SLD_FIN,

           ID_GTT_KARDEX,

           ID_GTT_KARDEX_VALORIZADO)

 VALUES

              (VC_ARTICULO.KST_ID,

               VC_ARTICULO.KST_ADRESSE,

               VC_ARTICULO.KST_NAME,

TO_DATE(vs_fec_ini, 'DD/MM/RRRR'),

TO_DATE(vs_fec_fin, 'DD/MM/RRRR'),

               VC_ARTICULO.ART_ID,

               VC_ARTICULO.WES_TYP,

               VC_ARTICULO.ART_COD,

               VC_ARTICULO.ART_NAME,

               VC_ARTICULO.ART_INFO,

 TRIM(VC_ARTICULO.VPK_NR),

           VC_ARTICULO.VPK_NAME,

           ls_tipo_ope,

           VC_ARTICULO.LFS_STATUS,

           VC_ARTICULO.LFP_STATUS,

           VC_ARTICULO.WES_ID1,

           VC_ARTICULO.WES_ID2,

           VC_ARTICULO.WES_DOCDATE,

           VC_ARTICULO.TIPO_DOC,

           VC_ARTICULO.SERIE_DOC,

           VC_ARTICULO.NRO_DOC,

           VC_ARTICULO.CANT_COMPRA,

           VC_ARTICULO.COST_UNI_COMPRA,

           VC_ARTICULO.COST_TOT_COMPRA,

           VC_ARTICULO.CANT_VENTA*(-1),

           VC_ARTICULO.COST_UNI_VENTA,

           VC_ARTICULO.COST_TOT_VENTA*(-1),

           ln_cant_tota,

           ln_cost_uni_tota,

           ln_cost_tota,

           V_ID_GTT_KARDEX,

           ID_GTT_KARDEX_VALORIZADO_SEQ.nextval);

 COMMIT;

 END  LOOP;

 select sum(LAST_CNT_SLD_FIN),sum(LAST_CST_TOT_SLD_FIN) INTO V_SUM_LAST_CNT_SLD_FIN, V_SUM_LAST_CST_TOT_SLD_FIN from (

 SELECT ART_ID,max(LAST_CNT_SLD_FIN) LAST_CNT_SLD_FIN,max(LAST_CST_TOT_SLD_FIN) LAST_CST_TOT_SLD_FIN FROM (

 SELECT ART_ID,

LAST_VALUE(CNT_SLD_FIN) OVER (PARTITION  BY ART_ID ORDER  BY ID_GTT_KARDEX_VALORIZADO ASC  ROWS  BETWEEN  UNBOUNDED  PRECEDING  AND  UNBOUNDED  FOLLOWING) AS LAST_CNT_SLD_FIN,

LAST_VALUE(CST_TOT_SLD_FIN) OVER (PARTITION  BY ART_ID ORDER  BY ID_GTT_KARDEX_VALORIZADO ASC  ROWS  BETWEEN  UNBOUNDED  PRECEDING  AND  UNBOUNDED  FOLLOWING) AS LAST_CST_TOT_SLD_FIN

 FROM MCDATA.GTT_KARDEX_VALORIZADO

 WHERE id_gtt_kardex=V_ID_GTT_KARDEX

            )

 group  by ART_ID

  );

 SELECT COUNT(1) INTO V_QUANTITY FROM MCDATA.GTT_KARDEX_VALORIZADO WHERE ID_GTT_KARDEX=V_ID_GTT_KARDEX;

 INSERT  INTO MCDATA.GTT_KARDEX(ID_GTT_KARDEX,INSERT_DATE,QUANTITY_RECORDS,STATUS_REG,P_FECHA_INICIO,P_FECHA_FIN,P_ID_ESTABLECIMIENTO,SUM_LAST_CNT_SLD_FIN,SUM_LAST_CST_TOT_SLD_FIN)

 VALUES(V_ID_GTT_KARDEX,CURRENT_TIMESTAMP,V_QUANTITY,1,vs_fec_ini,vs_fec_fin,vn_kst_id,V_SUM_LAST_CNT_SLD_FIN,V_SUM_LAST_CST_TOT_SLD_FIN);

 COMMIT;

 SELECT V_ID_GTT_KARDEX INTO P_OUT_ID_GTT_KARDEX FROM DUAL;

EXCEPTION

 WHEN OTHERS THEN

ln_nError := SQLCODE;

ls_cError := SQLERRM(ln_nError);

      RAISE_APPLICATION_ERROR(-20001,

ls_mensaje || TO_CHAR(ln_nError) ||  ', '  ||

                              ls_cError);

END;