![](OEBPS/image_rsrc8PK.jpg)

Preface

CA IdentityMinder Volume I: Java Developer's Guide will guide you java programming to extend the functionality of CA IdentityMinder. You will learn basic administration concept, CA IdentityMinder’s APIs, how to create custom workflow, and examples.

My CA IdentityMinder (formerly CA Identity Manager) Programming is a series of three books:

*   CA Identity Manager Volume I: Java Developer's Guide, for beginning level.
*   CA Identity Manager Volume II: Learn by Example Code, for advanced level.
*   CA Identity Manager: Custom Connectors Guide, for the custom connector developer.

Please visit book’s web site for more details.

About This Book

You will learn:

*   CA IdentityMinder Administration Concepts
*   CA IdentityMinder Programming Concepts
*   How to develop Business Logic Task Handler and example codes.
*   How to create Custom Workflows and Workflow API example codes.
*   How to implement Participant Resolver API and example code.
*   How to implement Event Listener API and example code.
*   How to implement Logical Attribute API and example code.
*   How to implement Validation Rules and example code.
*   How to implement Email Notification and example code.
*   How to implement Notification Rule API and example code.
*   How to implement Task Execution Web Service (TEWS) and example code.

Who this book for

This book is intended for beginners who know a little about Java programming and would like to learn how to implement CA IdentityMinder requirements by API.

![](OEBPS/image_rsrc8PM.jpg)

Convention

The following text conventions are used in this document:

| Convention | Meaning |
| Boldface | Boldface type indicates book titles |
| Italic | Italic type indicates emphasis, or placeholder variables |
| monospace | Monospace type indicates language and syntax elements |

Customer Support

Feedback from our readers is always welcome. Let us know what you think about this book. Please visit web site for more details:

*   The web site for books: [http://www.caidentitymanagerbook.com](http://www.caidentitymanagerbook.com)
*   Blog and updated contents: [http://caidentitymanager.blogspot.com](http://caidentitymanager.blogspot.com)

To send us general feedback or any questions, simply send an e-mail. Please check my email from web site.

Download Source Code

Please visit our web site: [http://www.caidentitymanagerbook.com](http://www.identitymanagerbook.com)

Trademarks

CA IdentityMinder, CA Identity Manager and CA SiteMinder are registered trademark of CA Technologies.

| ![](OEBPS/image_rsrc8PN.jpg)Please accept my apologies:DELAY: I expected to release this book September 2013 but I delay almost one year.GRAMMAR: Please accept my apology for grammar mistake. Reviewing process may require up to 3 months. Hopefully, my next release will fix this issue.NO POLICY XPRESS: Policy Xpress is easy to learn. We may not need beginning level book.EXAMPLES: I knew some examples can implement by Policy Xpress but I implement all examples by programming because I want to show how to use APIs.NO BASIC LEVEL: I apologize for some readers may complain this book is not for beginner. I will fix by adding bonus chapters & VDO demo. Please visit my blog.SUPPORT: I am full time programmer. I may not response your email immediately. Please allow 24 hours for a response. My time zone is New York EST.Regard,Kosakarika |

| About AuthorI am Java Developer and live in New York.Experience: 
*   Front End: ExtJS, JQuery, Content Management(WebSphere Portal), and Portlet (WebSphere/Weblogic/SUN Portal)

*   SOA: Rule JBoss Drools/Guvnor, ESB(ServiceMix/Camel) and BPEL(WebSphere Process Server)

*   IDM and SSO: CA IdentityMinder, CA SiteMinder, and SUN Access Manager.

*   Implemented multi-threading, high transaction real-time brokerage projects.

Certification:

*   Sun Certified Java Programmer 1.2

*   Sun Certified Business Component Developer 1.3

*   IBM Certified Developer - IBM WebSphere Portal Developer V6.1

*   IBM Certified Developer - Web Services Development for WebSphere V6.1

*   IBM System Administrator - WebSphere Application Server V6.1

*   IBM Enterprise Developer - IBM WebSphere Studio V5.0

 |

Copyright © 2014 W. Kosakarika

All rights reserved. No part of this book may be reproduced, stored in a retrieval system, or transmitted in any form or by any means, without the prior written permission of the author, except in the case of brief quotations embedded in critical articles or reviews.

Every effort has been made in the preparation of this book to ensure the accuracy of the information presented. However, the information contained in this book is sold without warranty, either express or implied. The author will be held liable for any damages caused or alleged to be caused directly or indirectly by this book.

Author has endeavored to provide trademark information about all of the companies and products mentioned in this book by the appropriate use of capitals. However, author cannot guarantee the accuracy of this information.

First published: September 2014

# Contents

[Chapter 1 Introduction](#part0007.xhtml)

[1.1 Why we need custom code](#part0007.xhtml_a8F4)

[1.2 What this book covers](#part0008.xhtml_a8F5)

[1.3 Technical Terms](#part0008.xhtml_a8F6)

[1.4 CA IdentityMinder Components](#part0008.xhtml_a8F7)

[1.5 Server Configuration](#part0008.xhtml_a8F8)

[1.6 Conclusions](#part0009.xhtml_a8F9)

[Chapter 2 Administration Concepts](#part0010.xhtml)

[2.1 Requirement](#part0010.xhtml_a8FB)

[2.2 Create Admin Task](#part0012.xhtml)

[2.2.1 Profile Tab](#part0012.xhtml_a8FD)

[2.2.2 Search Tab](#part0013.xhtml_a8FE)

[2.2.3 Tabs Tab](#part0013.xhtml_a8FF)

[2.2.4 Fields Tab](#part0013.xhtml_a8FG)

[2.2.5 Event Tab](#part0013.xhtml_a8FH)

[2.2.6 Role Use Tab](#part0014.xhtml_a8FJ)

[2.3 Provisioning](#part0015.xhtml)

[2.3.1 Account Template and Attribute Mapping](#part0015.xhtml_a8FM)

[2.3.2 Provisioning Directory](#part0015.xhtml_a8FN)

[2.3.3 Attribute mapping: User- Global User - Account](#part0015.xhtml_a8FP)

[2.3.4 Synchronization](#part0015.xhtml_a8FR)

[2.4 Identity Policy Set and Policy Xpress](#part0016.xhtml)

[2.4.1 Identity Policy Set](#part0016.xhtml_a8FT)

[2.4.2 Policy Xpress](#part0016.xhtml_a8FU)

[2.5 How it works](#part0017.xhtml_a8FV)

[2.5.1 How UI works](#part0017.xhtml_a8FW)

[2.5.2 View Submitted Task](#part0017.xhtml_a8FX)

[2.6 Conclusion](#part0017.xhtml_a8FY)

[Chapter 3 Programming Concepts and Configuring IDE](#part0018.xhtml)

[3.1 CA IdentityMinder APIs Overview](#part0018.xhtml_a8G0)

[3.1.1 Business Logic Task Handler API (BLTH)](#part0018.xhtml_a8G1)

[3.1.2 Workflow API](#part0018.xhtml_a8G2)

[3.1.3 Participant Resolver API](#part0018.xhtml_a8G3)

[3.1.4 Event Listener API](#part0018.xhtml_a8G4)

[3.1.5 Logical Attribute API](#part0018.xhtml_a8G5)

[3.1.6 Validation Rules](#part0018.xhtml_a8G6)

[3.1.7 Email Template](#part0018.xhtml_a8G7)

[3.1.8 Notification Rule](#part0018.xhtml_a8G8)

[3.1.9 Task Execution Web Service (TEWS)](#part0018.xhtml_a8G9)

[3.2 Task Phases](#part0018.xhtml_a8GA)

[3.2.1 Synchronous Phase Operations](#part0018.xhtml_a8GB)

[3.2.2 Asynchronous Phase Operations](#part0018.xhtml_a8GC)

[3.3 Configuring IDE](#part0018.xhtml_a8GD)

[3.4 Conclusions](#part0018.xhtml_a8GE)

[Chapter 4 Business Logic Task Handler](#part0019.xhtml)

[4.1 Programming and Configuration Concepts](#part0019.xhtml_a8GG)

[4.1.1 Programming](#part0019.xhtml_a8GH)

[4.1.2 Configuration](#part0019.xhtml_a8GJ)

[4.2 Task Session](#part0020.xhtml_a8GK)

[4.3 Access to Managed Objects](#part0020.xhtml_a8GM)

[4.4 Code Examples](#part0021.xhtml)

[4.4.1 Basic programming: BLTHAdapter and life cycle](#part0021.xhtml_a8GP)

[4.4.2 Modify user’s attributes by BLTHContext](#part0022.xhtml_a8GR)

[4.4.3 Modify user’s attribute by ProviderAccessor](#part0023.xhtml_a8GS)

[4.4.4 BLTHContext and ProviderAccessor](#part0025.xhtml)

[4.4.5 Business Logic Task Handler and screen.](#part0026.xhtml_a8GU)

[4.5 Use cases examples](#part0027.xhtml_a8GV)

[4.6 Conclusion](#part0029.xhtml)

[Chapter 5 Workflow](#part0030.xhtml)

[5.1 Workflow Concepts](#part0030.xhtml_a8GY)

[5.1.1 Default Workflow Features](#part0031.xhtml)

[5.1.2 Workpoint Designer Concept](#part0031.xhtml_a8H0)

[5.2 Custom Workflow](#part0031.xhtml_a8H1)

[5.2.1 Workflow and CA IdentityMinder](#part0031.xhtml_a8H2)

[5.2.2 Workpoint Component](#part0031.xhtml_a8H3)

[5.3 Code Examples](#part0032.xhtml)

[5.3.1 Workflow:  One Approver](#part0032.xhtml_a8H5)

[5.3.2 Workflow: Delay by city](#part0033.xhtml_a8H6)

[5.3.3 Category](#part0036.xhtml_a8H7)

[5.4 WorkPoint Programming](#part0036.xhtml_a8H8)

[5.4.1 Activity, Server Automated and Automated](#part0036.xhtml_a8H9)

[5.4.2 Script for Server Automated and Automated](#part0036.xhtml_a8HA)

[5.4.3 Agent scripts can be designated Synchronous or Asynchronous.](#part0036.xhtml_a8HB)

[5.4.4 Saving Job Objects](#part0036.xhtml_a8HC)

[5.4.5 Search reference](#part0036.xhtml_a8HD)

[5.5 Use cases examples](#part0036.xhtml_a8HE)

[5.6 Conclusion](#part0037.xhtml_a8HF)

[Chapter 6: Additional APIs](#part0037.xhtml_a8HG)

[6.1 Participant Resolver API](#part0037.xhtml_a8HH)

[6.1.1 Programming](#part0037.xhtml_a8HJ)

[6.1.2 Code Example: Participant Resolver API](#part0037.xhtml_a8HK)

[6.1.3 Use Case Example](#part0040.xhtml_a8HM)

[6.2 Event Listener API](#part0041.xhtml)

[6.2.1 Programming](#part0041.xhtml_a8HP)

[6.2.2 Code Example: Event Listener API](#part0041.xhtml_a8HR)

[6.2.3 Code Example: Event Generating](#part0044.xhtml)

[6.2.4 Use Case Examples](#part0046.xhtml_a8HT)

[6.3 Logical Attribute API](#part0048.xhtml)

[6.3.1 Programming](#part0048.xhtml_a8HV)

[6.3.2 Code Example](#part0048.xhtml_a8HW)

[6.3.3 Use Case](#part0048.xhtml_a8HX)

[6.4 Validation Rules](#part0049.xhtml)

[6.4.1 Programming](#part0049.xhtml_a8HZ)

[6.4.2 Code Example: Task-level validation](#part0049.xhtml_a8J0)

[6.4.3 Code Example: Directory-level validation](#part0051.xhtml)

[6.5 Email Notification](#part0053.xhtml)

[6.5.1 How to implement email notification](#part0053.xhtml_a8J3)

[6.5.2 Code Example: Email Template](#part0053.xhtml_a8J4)

[6.5.3 Code Example: Email notification by Service API](#part0053.xhtml_a8J5)

[6.6 Notification Rule API](#part0054.xhtml)

[6.6.1 Programming](#part0054.xhtml_a8J7)

[6.6.2 Code Example](#part0054.xhtml_a8J8)

[6.6.3 Use Case](#part0055.xhtml_a8J9)

[6.6.3 Notification Rule and Email Template Limitation and Service API](#part0056.xhtml_a8JA)

[6.7 Task Execution Web Service (TEWS)](#part0056.xhtml_a8JB)

[6.7.1 Code Example](#part0056.xhtml_a8JC)

[6.8 Additional Concept](#part0057.xhtml_a8JD)

[6.9 Conclusion](#part0058.xhtml)

[Appendix A: Import Workflow](#part0059.xhtml)

[Appendix B: Hot Deployment](#part0059.xhtml_a8JG)

# Chapter 1 Introduction

The key feature of CA IdentityMinder is customization without custom code but in this book we are talking about custom code. There are 2 main reasons why I wrote this book:

*   Some requirements need programming. (some can implement by programming only)
*   The lack of programming document, while as we have a lot of installation, configuration, and administration document. This book describe both concept and example steps by step.

## 1.1 Why we need custom code

My advice is let implement by powerful features such as ConfigXpress, PolicyXpress, and ConnectorXpress as the first choice. If there are some limitations, goes custom code.             

Calculation logic

If you have a lot of calculation logic, programming may better than PolicyXpress.

Performance

If you implement 30-40 PolicyXpress for one requirement, it may impact performance.  Custom code can reduce number of PolicyXpress.

Custom workflow

PolicyXpress cannot create custom workflow. You feel free to create workflow dynamically by programming. You can take advantages of workflow API such as create routing path in workflow, delay process, define approver, etc.

Exception handling

Handling exception by programming is easier. We can write java code try/catch, implement workflow path for error or use Listener to capture event failure.

Integration

Some requirements, we need custom code call web services or database inside CA IdentityMinder.

Complex requirement

Some requirements have many steps and long process, programing is good helper. We can do programing for validation, business logic under both synchronous and asynchronous phase.

No Limitation

You can use programming generate event, generate workflow, call other admin tasks ,etc. These advanced examples are in book volume II.

## 1.2 What this book covers

Chapter 1: Introduction or this one you are reading. We explain big picture of CA IdentityMinder component, server configuration.

Chapter 2: Administration Concepts. This chapter is written for beginner or programmer who has a few administrator experiences.

Chapter 3: Programming Concepts. We will introduce each type of API and concept of synchronous and asynchronous phase.

Chapter 4: Business Logic Task Handlers. This chapter will cover concepts of Business Logic Task Handlers API. 

Chapter 5: Workflows. You will learn how to customize workflow and Workpoint features.

Chapter 6: Additional APIs. We will cover other APIs and example code such as; TEWS, Notification Rule, Event Listener, Participation Resolver, Logical Attribute API, etc.

## 1.3 Technical Terms

There are some technical terms for new comer, avoid confusing.

Endpoint

It  is destination of user data after provisioning. Examples of endpoints can be Microsoft Active Directory, SAP, Database, UNIX workstation, Windows PC, or an application.

| ![](OEBPS/image_rsrc8PP.jpg) |
| Figure 1-1 Example of Endpoints |

User vs. Global User vs. Account

In CA IdentityMinder, there are 2 major server inside are CA IdentityMinder Server and CA IdentityMinder Provisioning Server (We will call “Provisioning Server” for short)

User means user information maintained by CA IdentityMinder Server. User is stored in CA IdentityMinder User Store.

Global User means user information maintained by the Provisioning Server. It is stored in Provisioning Director.

Account means user information in Endpoint.  For example account in Active Directory 

In figure below shows relationship between user, global user and accounts. Some users have a corresponding global user. When a user receives a provisioning role, the Provisioning Server will creates a global user. When server start provisioning process, some attributes from global user will been provisioned to accounts in endpoints.

| ![](OEBPS/image_rsrc8PR.jpg) |
| Figure 1-2 User vs. Global User vs. Account |

## 1.4 CA IdentityMinder Components

We will explain only some components that relate to custom code.

Servers

There are 2 required servers when you install CA IdentityMinder:

CA IdentityMinder Server executes tasks within CA IdentityMinder. CA IdentityMinder is the Java EE application includes the Management Console and the User Console.

CA Provisioning Server manages accounts on endpoint systems. This server is required if the CA IdentityMinder installation will support account provisioning.

User Store and Provisioning Directory

CA IdentityMinder User Store is the user store maintained by CA IdentityMinder Server. Typically, this is an existing store that contains the user identities that a company needs to manage.

Provisioning Directory, the user store maintained by the Provisioning Server. It is an instance of CA Directory and includes global users, which associate users in the Provisioning Directory with accounts on endpoints such as Microsoft Exchange, Active Directory, and SAP.

| ![](OEBPS/image_rsrc8PS.jpg) |
| Figure 1-3 display relationship between CA IdentityMinder Server, Provisioning Server, User Store and Provisioning Directory |

Connector

A connector is the software interface to an endpoint. The Provisioning Server uses the connector to communicate with the endpoint. It translates Provisioning Server actions into changes on the endpoint, such as “Create a new email account on a Microsoft Exchange endpoint.”             

Connector Servers is a Server component that manages connectors. There are two types of connector servers:

*   CA IAM Connector Server (CA IAM CS) manages connectors written in Java
*   C++ Connector Server (CCS) manages connectors written in C++

Connectors and Agents, some connectors require an agent on the systems they manage in order to complete the communication cycle.

Connector Xpress is CA IdentityMinder utility for managing dynamic connectors, mapping dynamic connectors to endpoints, and establishing routing rules for endpoints. You can use it to configure dynamic connectors to allow provisioning and management of SQL databases and LDAP directories.

Additional Components

WorkPoint workflow engine and WorkPoint Designer are installed automatically when you install CA IdentityMinder. These components enable you to place a CA IdentityMinder task under workflow control, and to modify existing workflow process definitions or create new definitions.

Provisioning Manager is a graphical interface to manage global user and provisioning server options. You may also use the Provisioning Manager to manage endpoint or account.

## 1.5 Server Configuration

This book assumes you should have already installed and configure:

*   CA IdentityMinder and user store.
*   Provisioning Server, provisioning manager and provisioning directory.
*   Connector server
*   Wokpoint designer

My suggestion is to configure one endpoint Microsoft Active Directory, account template and provisioning role is a plus. You should have some users and account in IDM system.

User Store attributes

In this book, we require attribute City and telephone number as the main, but other chapters require additional. We will create 3 admin tasks:

*   Update Location and Ext Number used in almost every chapter.

    *   Requires attribute:  L (or City)
    *   Requires attribute:  telephoneNumber.
    *   In chapter 2, our policy Express example requires state.
*   Update office, used in chapter 6: Logical Attribute API only

    *   Requires attribute: L (or City same as previous)
*   Update Employee Number used in chapter 6: Validation Rule only

    *   Requires attribute: employee number

Please check the Management Console, select Directory > User Store (Cooperate Store) > User and check attributes.

| ![](OEBPS/image_rsrc8PT.jpg) |
| Figure 1-4 shows display name |

Global user attributes

In the Management Console, select Directory > Provisioning Store > Global User and check attribute, Physical Name eTCity.

| ![](OEBPS/image_rsrc8PU.jpg) |
| Figure 1-5 shows display name of eTCity |

Attributes mapping

In the Management Console, select Environment > your environment > Advanced Settings > Provisioning and check attributes mapping: User Attribute l maps to Provisioning Attribute eTCity.

| ![](OEBPS/image_rsrc8PV.jpg) |
| Figure 1-6 shows attribute mapping |

## 1.6 Conclusions

We introduced the benefit of custom code and server configuration. The next chapter you will learn the basic concepts of CA IdentityMinder administration.

# Chapter 2 Administration Concepts

If you familiar with CA IdentityMinder, you can pass this chapter quickly. This chapter, you will learn:

*   How to create admin task
*   How provisioning works
*   How Identity Policy Set and Policy Xpress works
*   Understand submitted task and events

It is difficult to explain all administration features in one chapter. We will focus only some part that relate to programming.  If you are new to CA IdentityMinder, you may easily to get lost because of many features. We will use admin task as major topic.

## 2.1 Requirement

This chapter, we will implement requirement by administrator’s tools.

Requirement

Our requirement need screen to modify city and extension telephone number. The requirements can be written as steps below:

*   Step1: log into the Identity Manager User Console as administrator, and select form “Update location and Ext Number”

    *   Select city from dropdown
    *   Put extension number
    *   Click submit
*   Step 2:  System updates user attributes:

    *   Update city attribute and set country by city value.
    *   Concatenate office number and extension number.

*   Step 3:  System updates account attributes; city and telephone number

Design

We will implement each requirement’s step by:

*   Step 1: Provide screen

    *   Create admin tasks and screen with 2 attributes; city and extension number
*   Step 2: Processing

    *   We use Policy Set maps city to country.
    *   We use Policy Xpress to concatenate office number and extension number.
*   Step 3: Provisioning

    *   Configure attribute mapping
    *   Execute account synchronization

| ![](OEBPS/image_rsrc8PW.jpg) |
| Figure 2-1 shows how to implement requirement. |

## 2.2 Create Admin Task

Admin tasks are the one of main feature. Almost of all requirements start from the admin tasks. Admin task is an administrative function that a user can perform in CA IdentityMinder.  Admin Tasks can be Create User, View User, Modify User, Reset User Password, etc. We can see admin tasks under menu home or users > tasks. 

| ![](OEBPS/image_rsrc8PX.jpg) |
| Figure 2-2 displays admin tasks in console |

We will start from create Admin Tasks.

*   Log in Admin Console as administrator.
*   Click tab Roles and Tasks > Admin Tasks > Create Admin Task.
*   Then select “Create a new Admin Task” and click OK

| ![](OEBPS/image_rsrc8PY.jpg) |
| Figure 2-3 shows menu create admin task |

When you select create admin task, screen will display in 5 tabs (see figure below):

1.  Profile tab contains general information (name), how to display in menu, what is primary object and action, when Synchronization work and extension programming.
2.  Search tab, relates to primary object in profile tab; how do you search primary object.
3.  Tabs tab used for adding tab and screen.
4.  Fields tab shows how many fields in this admin task. These fields came from screens in tabs tab.
5.  Events tab shows how many events will be generated after submit admin tasks.

| ![](OEBPS/image_rsrc8PZ.jpg) |
| Figure 2-4 shows 5 tabs when create admin task |

### 2.2.1 Profile Tab

In profile tab, there are 5 sections:

1.  General Information

There are 3 fields

| Field Name | Value | Description |
| Name | Update Location and Ext Number | Task name  will show on menu |
| Tag | BookBasicUpdateLocAndExtNo | It is unique value of the task. |
| Description | Example for Basic Administrative | It is description |

| ![](OEBPS/image_rsrc8R0.jpg) |
| Figure 2-5 shows name on menu. |

2.  How to display in menu?

Admin Task has screen, so we have to decide where screen is.  There are 3 fields

| Field Name | Value | Description |
| Task Order | 1 | Specifies the display order in menu.![](OEBPS/image_rsrc8R1.jpg) |
| Category | Book Example | Categories are displayed as tabs at the top of the screen, order by number descending.![](OEBPS/image_rsrc8R2.jpg) |
| Category Order | 11 |
| Category 2 | Tasks | Specifies the second/third level category, which appears as a link below the list of category tabs.![](OEBPS/image_rsrc8R3.jpg) |
| Category 2 Order | 0 |
| Category 3 | Basic |
| Category 3 Order | 0 |

| ![](OEBPS/image_rsrc8R4.jpg) |
| Figure 2-6 shows category value. |

3.  What is primary object and action?

It is very important. It is kind of questions: what you want to do? I want to modify user information. So primary object should be “user” and action should be “modify”.

| Field Name | Value | Description |
| Primary Object | User | Specifies the object that the task operates on. |
| Action | Modify | Specifies the operation to perform on the object. |

4.  Synchronization

This section describes synchronization behavior after submitted this task. There are 2 type of synchronization:

*   User Synchronization means task will synchronize users with “identity policies set”.
*   Account Synchronization means any modification in this task will synchronizes with global user and accounts.

There are 3 choices to tell when we want synchronization execute:

*   None: do nothing, do not synchronization.
*   On Task completion: means when task complete, it will trigger synchronization.
*   On Every Event: when task has been submitted, many events will be generated. Synchronization will occur on every event complete.  This option may impact performance because synchronization may occur more than one time.

| Field Name | Value | Description |
| User Synchronization | On Task completion | It will synchronize users with “identity policies” after task complete |
| Account Synchronization | On Task completion | It will synchronize account in endpoint after task complete |

| ![](OEBPS/image_rsrc8R5.jpg) |
| Figure 2-7 shows value on screen |

5.  Additional features

All these attributes in this section are useful when we do programming. We will cover more details in next chapter.

| Field Name | Value | Description |
| Hide In Menus | Do not check | If check, this task does not show in menus. |
| Public Task | Do not check | If check, this task can call without login. |
| Enable Auditing | check | If check, records this task in an auditing database |
| Enable Workflow | check | If check, enables workflow at event level. |
| Enable Web Services | check | If check, this task can call by web services |
| Workflow Process | Do not thing | If select, support workflow at task level. |
| Task Priority | Medium | Determines the order in which executes tasks. |
| Business Logic Task Handlers | Do not thing | Associates a business logic task handler. |

| ![](OEBPS/image_rsrc8R6.jpg) |
| Figure 2-8 shows value on screen |

Do not submit, select “Search” tab.

### 2.2.2 Search Tab

Some tasks need Search screen depending on your primary object. In profile tab, we selected primary object is “User” and action is “Modify”. So before we modify user, we need to search user to modify. If your primary object is “NONE”, search is not necessary.

| ![](OEBPS/image_rsrc8R7.jpg) |
| Figure 2-9 shows example screen: Search User |

On tab Search, click browse, select screen Name: “Default Search Screen”, Type: “Standard Search Screen”

| ![](OEBPS/image_rsrc8R8.jpg) |
| Figure 2-10 select screen “Default User Search” |

Do not submit, click “Tabs” tab move on to next section.

### 2.2.3 Tabs Tab

On user screen, one admin task can have many tabs. Each tab has difference purposes. The figure below shows example of admin task “Modify User” has 5 tabs. Each tab has own screen.

| ![](OEBPS/image_rsrc8R9.jpg) |
| Figure 2-11 shows example of tabs in admin Modify User |

This section, you have to answer 3 things:

*   What type of tab?
*   How many tabs inside this admin task?
*   What’s screen inside each tab?

Type of tab

There are 3 types of Tab Controller:

*   Standard Tab Controller, every tabs will be displayed in top on admin task. We can pick any tabs from top.
*   Wizard Tab Controller, it will show as step by steps and button will be “Next”. Users have to review every screen.
*   Sequence Tab Controller, we don’t see any tab on screen but user will see button “next”.

| ![](OEBPS/image_rsrc8RA.jpg) |
| Figure 2-12 shows type of tab comparison |

In our code, we select Standard Tab Controller.

How many tabs inside this admin task?

Add tab from drop down below. In Our example we want to modify user, so we pick Profile. (UserProfile)

| ![](OEBPS/image_rsrc8RB.jpg) |
| Figure 2-13 show how to add tab |

What’s screen inside each tab

Each tab must have one screen, we click Pencil icon to add screen.

| ![](OEBPS/image_rsrc8RC.jpg) |
| Figure 2-14 show icon “Pencil” to add screen. |

Then click Browse to select screen

| ![](OEBPS/image_rsrc8RD.jpg) |
| Figure 2-15 shows Browse button to select screen |

Our prototype requires 2 attributes, so we need to create new screen. So we select button “New”.

| ![](OEBPS/image_rsrc8RE.jpg) |
| Figure 2-16 shows our prototype |

| ![](OEBPS/image_rsrc8RF.jpg) |
| Figure 2-17 shows how to create new screen |

Then we add name of screen and tag:

| Field Name | Value |
| Name | Update Location and Ext Number |
| Tag | UpdateLocationandExtNumber |

So we need 2 attributes on screens, click Pencil Icon to add attribute.

| ![](OEBPS/image_rsrc8RG.jpg) |
| Figure 2-18 show Pencil icon to add attribute |

The first one is City Name that link to user attribute: city

| Field Name | Value | Description |
| Attribute Name | City | Select from user’s attribute |
| Style | Dropdown | Display’s style |
| Name | City | This field will display as label on screen |
| Source of selection options | Simple List | Initial data for dropdown |

| ![](OEBPS/image_rsrc8RH.jpg) |
| Figure 2-19 shows value of city attribute |

Inside text area “Source of selection options” put value in the table below. Then click apply

| Toronto;TorontoBuenos Aires;Buenos AiresTokyo;TokyoLondon;LondonSao Paulo;Sao PauloNew York;New YorkDubai;DubaiMelbourne;Melbourne |

Click Pencil on next line. The second one is Extension Number. We will append extension number to office number and update user attribute: telephone number. So this attribute is not actual user attribute. We define as Screen Logical Attribute.

| Field Name | Value | Description |
| Attribute Name | Screen Logical Attribute&#124;ExtNumber&#124; | We don’t use user’s attribute, we have to create Screen Logical Attribute and use character “&#124;” show it is logical attribute not user’s attribute. |
| Style | Text | Display style on screen |
| Name | Ext Number | Display as label on screen |

| ![](OEBPS/image_rsrc8RJ.jpg) |
| Figure 2-20 shows value for Ext Number attribute |

Click “Apply” and then click “OK”, it will go back to previous screen, and click select.

| ![](OEBPS/image_rsrc8RK.jpg) |
| Figure 2-21 shows select the screen |

It will go back to previous screen and click OK to confirm.

| ![](OEBPS/image_rsrc8RM.jpg) |
| Figure 2-22 shows confirmation screen again |

You have done with long step. Then click  tab “Fields”

### 2.2.4 Fields Tab

The good news for this tab, you don’t need to do anything. You just review fields. You will see 2 fields that you used in screen “Update Location and Ext Number”: |ExtNumber| and City. Other attributes are required for primary object User.

| ![](OEBPS/image_rsrc8RN.jpg) |
| Figure 2-23 shows fields tab |

Then click “submit”

### 2.2.5 Event Tab

Events list in tab Events will not show immediately when we create admin task. It will show after we submit to create admin task.

Go to menu Modify Admin Task. Select Category from dropdown and type “book*”. Select task “Update Location and Ext Number” and click Select button.

| ![](OEBPS/image_rsrc8RP.jpg) |
| Figure 2-24 shows search admin task screen |

Select tab “Events”, you will see event list . In this chapter, we do nothing with events tab.

| ![](OEBPS/image_rsrc8RR.jpg) |
| Figure 2-25  show tab Events |

How many events will be generated?

Number and type of events will be generated depending on Primary Object, Action and Tab.

| ![](OEBPS/image_rsrc8RS.jpg) |
| Figure 2-26 shows relationship of event generation |

### 2.2.6 Role Use Tab

This tab will show who can use this admin task. Now you see nothing. 

| ![](OEBPS/image_rsrc8RT.jpg) |
| Figure 2-27 shows Role Use Tab |

We add admin role “System Manager” to this admin task. Select tab Roles and Tasks > Admin Roles > Modify Admin role > Select Admin Role “System Manager” and click Tasks tab.

| ![](OEBPS/image_rsrc8RU.jpg) |
| Figure 2-28 shows Admin Role Screen |

Scroll down to bottom of screen, select Filter by category “Book Example” and Add Task “Update Location and Ext Number (BookBasicUpdateLocAndExtNo)”

| ![](OEBPS/image_rsrc8RV.jpg) |
| Figure 2-29 shows selecting our task. |

## 2.3 Provisioning

The goal of this topic is understand how provisioning works. To implement provisioning requires 4 configuration steps:

*   Step1: Acquire Endpoint

    *   Endpoint can be Microsoft Active Directory or database.
*   Step2: Create Account Template

    *   Link to endpoint.
    *   Account template defines attribute mapping between global user and account.
*   Step3: Create Provisioning Role

    *   Link to account templates.
    *   One provisioning role can have many account templates.
*   Step4: Add user to Provisioning Role

The whole steps show in the picture below.

| ![](OEBPS/image_rsrc8RW.jpg) |
| Figure 2-30 shows all steps and related screen. |

### 2.3.1 Account Template and Attribute Mapping

Account templates define how a (global) user is represented in a managed endpoint. By default, account templates define mapping using Rule String, for example, %USA% or %UC%. You can see in official document Administration Guide for more details. There are 2 ways to define mapping:

1.  Rule String, the official document defines Rule String for some attributes, not all.
2.  Global User attributes, you can use this one if there is no Rule String mapping. The format will be %#<attribute name>%

For example, city attribute in account template, you can put:

*   Rule String: %UC%
*   Global User attributes: %#eTCity%

Both give the same result. The picture below shows global user’s attribute city value in account template.

| ![](OEBPS/image_rsrc8RX.jpg) |
| Figure 2-31 shows global user’s attribute in account template. |

Another example that uses global user attributes is account container in picture below. For example, if eTGlobalUser has eTLocation=northamerica , then container will be  eTADSOrgUnitName=Users, eTADSOrgUnitName=NorthAmerica. All these values is global user attributes.

| ![](OEBPS/image_rsrc8RY.jpg) |
| Figure 2.32 shows screen Account Template and Global User attribute |

### 2.3.2 Provisioning Directory

You can get Global User attributes from provisioning directory. You have to use Client LDAP, such as JXplorer, connect provisioning directory.  You can get provisioning store information from Management Console. Select Provisioning store and check URL.

| ![](OEBPS/image_rsrc8RZ.jpg) |
| Figure 2-33 shows provisioning directory connectivity. |

Global User (Class: eTGlobalUser)

Inside the provisioning directory, browse to path eTGlobalUserContainerName=Global Users, eTNamespaceName=CommonObjects, dc=im, dc=eta is location keeps all global users.

Select one user, you can see attribute name and value. (You can use this attribute name in account template)

| ![](OEBPS/image_rsrc8S0.jpg) |
| Figure 2-34 shows path and attribute eTCity of global user. |

Account (Class: eTADAccount)

If you already have some account in endpoint: Active Directory, then let browse path eTADSDirectoryName=<Endpoint Name>, eTNamespaceName=ActiveDirectory, dc=im, dc=eta. It represents Endpoint (Active Directory). 

| ![](OEBPS/image_rsrc8S1.jpg) |
| Figure 2-35show attributes of account object |

The object eTADAccount under eTADSDirectory path represent Account. If you modify some values directly in account object (eTADAccount), it will reflect value in Active Directory immediately.  For Example, we change value of “eTADSl” (it means City) from “New York” to be “New York Test” and look at Active Directory, value will be changed also.

| ![](OEBPS/image_rsrc8S2.jpg) |
| Figure 2-36 shows relationship between eTADAccount and AD Account |

We do not suggest change any value directly inside account object (eTADAccount) because CA IdentityMinder keeps it as internal process. It may useful for debug when you do programming and try to modify the value and get error. You may print the value and put into Account object directly. Let see it allowed or not.

Another choice to access Global user or account, you use Provisioning Manager but you cannot see attribute name from screen.

### 2.3.3 Attribute mapping: User- Global User - Account

To understand better, this section describes attribute mapping from user to global user and from global user to account.

User Store

Check user store connectivity information from Management Console, and login to User Store by any LDAP client such as JXplorer.

| ![](OEBPS/image_rsrc8S3.jpg) |
| Figure 2.-37 shows user store connectivity |

We can see attribute mapping: User attributes to Global user attributes in Management Console. In the Management Console, select Environment > your environment > Advanced Settings > Provisioning > Attribute Mappings

| ![](OEBPS/image_rsrc8S4.jpg) |
| Figure 2-38 shows attribute mappings in Management Console |

The picture below show how attribute city mapping from user to account. The user’s attribute “l” map to Global user’s attribute “eTCity” by Attribute Mappings in Management Console. The Global user’s attribute maps to account by Account Template.

| ![](OEBPS/image_rsrc8S5.jpg) |
| Figure 2-39 shows attribute mappings from user to account |

### 2.3.4 Synchronization

We learned how attribute mapping from user, the next thing we have to learn when it works.

When Global User created?

Global user will be created when user has provisioning role. If you just create user, Global user will not be created.

| ![](OEBPS/image_rsrc8S6.jpg) |
| Figure 2-40 shows when global user created |

When attributes synchronization?

It will start synchronization, if you select option “Account Synchronization” in admin task: on task complete or on every event complete.

| ![](OEBPS/image_rsrc8S7.jpg) |
| Figure 2-41 shows dropdown Account Synchronization |

What is User Synchronization?

The User Synchronization drop down in admin task will trigger Identity Policy Set. We will talk about Identity Policy Set in next topic.

| ![](OEBPS/image_rsrc8S8.jpg) |
| Figure 2-42 shows dropdown User Synchronization |

## 2.4 Identity Policy Set and Policy Xpress

Go back to our example‘s requirement, we create:

*   Policy Set maps city to country
*   Policy Xpress concatenate office number and extension number.

| ![](OEBPS/image_rsrc8S9.jpg) |
| Figure 2-43 show how to implement requirement. |

### 2.4.1 Identity Policy Set

An Identity policy is a set of business changes that occurs when a user meets a certain condition. To Open CA IdentityMinder Admin Console and select tab Polices, and click sub menu manage Identity Policies > Create Identity Policy Set             

| ![](OEBPS/image_rsrc8SA.jpg) |
| Figure 2-44 shows menu “Create Identity Policy Set” |

Profile Tab

The first tab Profile, put value below:

| Field Name | Value | Description |
| Name | Set Office Address | Name of policy set |
| Category | Book Example | Category name |
| Description | Set Office Address |  |

Do not click submit, click Policies Tab.

| ![](OEBPS/image_rsrc8SB.jpg) |
| Figure 2-45 shows value in tab “Profile” |

Policies Tab

In this tab has 2 parts: Policy Set Member Rule and Identity Policies.  The Policy Set Member Rule tells who is the identity policy applies to? In our example we use default value = all that means all users meet this member rule.

| ![](OEBPS/image_rsrc8SC.jpg) |
| Figure 2-46 shows Member Rule == all users |

Next, we have to create Identity policy: when city = “New York” then set address. To click button Add, put values:

| Field Name | Value |
| Policy Name | New York Address |
| Policy Condition |
| City | New York |
| Action on Apply Policy |
| Country | United States |
|  |  |

| ![](OEBPS/image_rsrc8SH.jpg) |
| Figure 2-47 shows screen defines Identity Policy |

And click “OK”, it will be back to screen Policies.

| ![](OEBPS/image_rsrc8SJ.jpg) |
| Figure 2-48 shows complete task of Policies |

Click add button for other cities

| Policy Name | Policy Condition | Action on Apply PolicySelect “Set <single-value-user-attribute> to <value>” |
| Toronto Address | City =Toronto | Country =Canada |
| Buenos Aires Office | City=Buenos Aires | Country =Argentina |
| Tokyo Office | City=Tokyo | Country =Japan |
| London Office | City=London | Country =United Kingdom |
| Sao Paulo Office | City=Sao Paulo | Country =Brazil |
| Dubai Office | City=Dubai | Country =UAE |
| Melbourne Office | City=Melbourne | Country =Australia |

And click the last tab “Owners”

Owners Tab

This tab tells who can manage this Identity Policy Set. We want to add admin role “System Manager” to manage this policy.

| ![](OEBPS/image_rsrc8SK.jpg) |
| Figure 2-49 shows screen that add “System Manager” to be owner |

When user change city and submit admin task, Identity Policy Set will evaluate Member Rule and Policy Set.

| ![](OEBPS/image_rsrc8SM.jpg) |
| Figure 2-50 shows how Identity Policy Set works. |

Identity Policy Set has some limitation because condition base on user’s attribute or role membership. The next, we will create Policy Xpress provide more features.   

### 2.4.2 Policy Xpress

Policy Xpress allows you to create complex business logic (policies) in CA IdentityMinder without the need to develop custom code. Policy Xpress is more flexible than Identity Policy Set. It can access logical attributes and capture events. This section, we will create Policy Xpress to solve the requirement. When user put extension number then we will update phone number in format <phone number>x<extension number>.

Select tab “Policies” and sub menu “Create Policy Xpress Policy”. Select “Create a new object of type Policy Xpress”

| ![](OEBPS/image_rsrc8SN.jpg) |
| Figure 2-51 shows menu Create Policy Xpress Policy |

Profile Tab

We put value of Policy Xpress as below table:

| Field Name | Value | Description |
| Name | Set Telephone Number | Name of policy |
| Policy Type | Submitted Task | Defines the listeners that trigger the policy. Our Policy Xpress will execute when task submitted. |
| Category | Book Example | Category name |
| Priority | 0 | The lower the number, the higher the priority |
| Enable | Check | This policy is active in CA IdentityMinder |
| Run Once | Do not Check | Specifies if the policy runs only once. For our policies do not check and run every time they meet criteria. |

| ![](OEBPS/image_rsrc8SP.jpg) |
| Figure 2.52 shows the values of profile’s screen |

Click tab “Events”.

Events Tab

Policy Xpress can capture events of Admin Task include UI and task submitted. This tab tells when this policy Xpress will be executed. We want this Policy Xpress execute when our task complete, so we put value below:

| Field Name | Value | Description |
| State | Task completed | Tells when this Policy Xpress execute |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | Select task name from dropdown |

| ![](OEBPS/image_rsrc8SR.jpg) |
| Figure 2-53 displays event of Policy Xpress |

Data Tab

This tab is designed for getting data. We have to capture some value before set it back. We plan to create condition like:

| If city == “New York” then set Telephone number + “x” + extension number from screen |

So we need to get data: City, Telephone number and extension number (Logical attribute). Click “Add Data Element” to add data. For city attribute, select value as below table:

| Field Name | Value | Description |
| Name | City | Name of data |
| Category | Attributes | Group of data elements. |
| Type | User Attribute | Specifies the data element type based on the category selected. |
| Function | Get | Defines possible variations of the same data. Most data elements only support the Get function. |
| Attribute Name | City (l) | Required attribute |

| ![](OEBPS/image_rsrc8SS.jpg) |
| Figure 2-54 shows screen, getting data: City |

For Telephone Number, select value as below table:

| Field Name | Value | Description |
| Name | TelephoneNumber | Name of data |
| Category | Attributes | Group of data elements. |
| Type | User Attribute | Specifies the data element type |
| Function | Get | Get function. |
| Attribute Name | Business Phone (Telephone Number) | Required attribute |

For Extension Number, select value as below table:

| Field Name | Value | Description |
| Name | ExtensionNumber | Name of data |
| Category | Attributes | Group of data elements. |
| Type | User Attribute | Specifies the data element type |
| Function | Get | Get function. |
| Attribute Name | &#124;ExtNumber&#124; | Our logical attribute |

| ![](OEBPS/image_rsrc8ST.jpg) |
| Figure 2-55 shows screen get data: Telephone and Logical Attribute &#124;ExtNumber&#124; |

When you complete this step, click tab Entry Rule.

Entry Rules Tab

Entry Rules are main condition. It tells what we are interested. Our example is interested city value not blank.

| ![](OEBPS/image_rsrc8SU.jpg) |
| Figure 2-56 shows screen Entry Rule Condition |

Complete this step and click tab Action Rules

Action Rules Tab

This tab, we will create condition:

| IF city == “New York” THEN set Telephone number + “x” + extension number from screen |

We define IF in Action Rule Conditions and define THEN in Add Action.

| ![](OEBPS/image_rsrc8SV.jpg) |
| Figure 2-57 shows condition when city == New York |

Click on Add Action Rule button to create Action Rule.

| Field Name | Value | Description |
| Name | Set New York Telephone Number | Name of action rule |
| Action Rule Conditions |  |
| City | New York | Kind of If condition |
|  |  |  |

To click “Add Action When Match” button, put value as below table:

| Field Name | Value | Description |
| Name | Set Telephone and Ext | Name of data |
| Category | Attributes | Group of data elements |
| Type | Set User Values | Specifies the data element type |
| Function | Set | Set function |
| Attribute Name | Business Phone (telephoneNumber) | Our attribute |
| Value | 111-111-1111 x {'ExtensionNumber'} | Expected value |

Add condition for other cities in table below:

| Action Rule Conditions | Set Business Phone (telephoneNumber) |
| City =Toronto | 222-111-1111 x {'ExtensionNumber'} |
| City=Buenos Aires | 333-111-1111 x {'ExtensionNumber'} |
| City=Tokyo | 444-111-1111 x {'ExtensionNumber'} |
| City=London | 555-111-1111 x {'ExtensionNumber'} |
| City=Sao Paulo | 666-111-1111 x {'ExtensionNumber'} |
| City=Dubai | 777-111-1111 x {'ExtensionNumber'} |
| City=Melbourne | 888-111-1111 x {'ExtensionNumber'} |

| ![](OEBPS/image_rsrc8SW.jpg) |
| Figure 2-58 shows conditions of Action Rules |

Click submit button to create Policy Xpress. We left Advanced Tab as default value.

## 2.5 How it works

We can test our admin task as step below:

*   Log in Admin Console as administrator.
*   Click tab Book Example and menu Basic > Update Location and Ext Number.
*   Search User

    *   My suggestion, please select user that have provisioning role and AD account.
*   Update city, put extension number and click submit.

After task run completely, please go check result in user store, provisioning directory and active directory.

### 2.5.1 How UI works

We have 2 screens: Search screen and Form.

Search Screen

We define Search screen when we create admin task:

*   In profile tab, we select primary object as User and action is Modify.
*   In search tab, we select default search screen “Default User Search”.

| ![](OEBPS/image_rsrc8SX.jpg) |
| Figure 2-59 shows screen of Default User Search. |

The number of result is depending on your scope of Admin Role. You can check from Tab “Roles and Tasks”, and select Menu “Modify Admin Role Members/Administrators” and select Tab “Members”. Look at item “Which User objects does this role manage?”

Form

This form came from Admin Task in “Tabs” tab. We create on tab “Profile” (Tab name does not display because we have only one tab) and we add screen name “Update Location and Ext Number”

*   Field City, this field will populate current attribute of users.
*   Field Ext Number, this field is the logical attribute value

Modify City and Ext value and click submit.

| ![](OEBPS/image_rsrc8SY.jpg) |
| Figure 2-60 shows form |

### 2.5.2 View Submitted Task

View Submitted Task is very important for developer to understand CA IdentityMinder behavior. After admin task was submitted, you can go check status in View Submitted Task. Select tab “System”, select menu “View Submit Task” and select “Search”

| ![](OEBPS/image_rsrc8SZ.jpg) |
| Figure 2-61 shows View Submitted Tasks screen |

Find your summited task, it should be the latest one. And click icon “![](OEBPS/image_rsrc8T0.jpg)” to see detail inside.

| ![](OEBPS/image_rsrc8T1.jpg) |
| Figure 2-62 shows our submitted task. |

There are 2 interesting thing inside submitted task details.

*   Task History tells how many Identity Policy Set or Policy Xpress are matched.
*   Included Event tells how many events are generated

| ![](OEBPS/image_rsrc8T2.jpg) |
| Figure 2-63 shows Task History and Included Events |

There are 7 events were generated in sequence order:

1.  Event No 1: Modify user

This event Modify user was generated because we modify user’s attribute: city. It was generated after we submitted task (that primary object is “User” and action “Modify”). Select icon “pencil” to see more detail. It will show new value and old value after submit task.

| ![](OEBPS/image_rsrc8T3.jpg) |
| Figure 2-64 shows Event No 1: Modify user was generated because we modify city attribute. |

After this event finish, city attributes in User Store will be changed.

| ![](OEBPS/image_rsrc8T4.jpg) |
| Figure 2-65 after Event No 1: Modify user finished, city attribute was changed. |

2.  Event No 2 : Synchronize user

This event was generated because when we select drop down User Synchronization: On task completion in admin task. When this event generate, it will trigger our Policy Set: Set Office Address.

| ![](OEBPS/image_rsrc8T5.jpg) |
| Figure 2-66 shows event No.2 was generated by option User Synchronization. |

3.  Event No 3: Modify user

This event was generated by Policy Xpress. Policy Xpress set value of Business Phone. After this event finished, the telephone number attribute value in User Store has been changed.

| ![](OEBPS/image_rsrc8T6.jpg) |
| Figure 2-67 shows event No.3 was generated by policy Xpress to modify telephone number. |

4.  Event No 4: Modify user

This event was generated by Identity Policy Set. Identity Policy set attribute country. After this event finished, the country attribute value in User Store has been changed.

| ![](OEBPS/image_rsrc8T7.jpg) |
| Figure 2-68 shows event No.4 was generated by Identity Policy Set modify attribute country. |

5.  Event No 5: Synchronized provisioning role and add accounts for user.

This event was generated because User has provisioning role and select option User Synchronization.

This event is used for create account in Endpoint. If you have already had account in Endpoint, this event does nothing. You can see detail in TASK SESSION accounts create: 0 update: 0 re-create:0 and failure: 0.

| ![](OEBPS/image_rsrc8T8.jpg) |
| Figure 2-69 shows event No.5 details. |

6.  Event No 6: Synchronize User

This event was generated by Policy Xpress after modify user event. We know because the value in “Attribute Changed” is value from Policy Xpress.

| ![](OEBPS/image_rsrc8T9.jpg) |
| Figure 2.70 shows event No.6 details. |

7.  Event No. 7 Synchronize user attributes with accounts Event Details

This event was generated because we select option in admin task screen Account Synchronization: On Task Complete. This event will update the global users’ and accounts’ attributes.

| ![](OEBPS/image_rsrc8TA.jpg) |
| Figure 2-71 shows event No.7 details. |

After all events are complete, go check user’s attribute in CA IdentityMinder User Store, Provisioning Directory and Endpoint (Active Directory).

| ![](OEBPS/image_rsrc8TB.jpg) |
| Figure 2-72 shows attributes of user, global user and account |

When admin task submitted, you have to know:

*   How many events will be generated?
*   Which component generate event?
*   What expected outcome of event?

| ![](OEBPS/image_rsrc8TC.jpg) |
| Figure 2-73 shows all events from our example. |

Limitation

Our admin task has some limitations:

*   It cannot show the current value of extension number.
*   There no validation for extension number
*   If we change only extension number and do not change city value, the CA IdentityMinder assumes there are nothing changes in this task.

We can fix these limitations easily by programming.

| ![](OEBPS/image_rsrc8TD.jpg) |
| Figure 2.-74 shows message when we update only extension number, not city attribute |

## 2.6 Conclusion

This chapter we create admin task and use administrator’s tool to implement requirement. We learn:

*   How to create admin task
*   How provisioning works
*   How Identity Policy Set and Policy Xpress works
*   Understand submitted task and events

The next chapter, we will learn programming concept.

# Chapter 3 Programming Concepts and Configuring IDE

This chapter, we will learn:

*   Concept of Synchronous and Asynchronous phase
*   Overview of 9 APIs.
*   Configuring IDE.

## 3.1 CA IdentityMinder APIs Overview

There are 2 types of CA IdentityMinder programming:

*   Java Programming: performs the logics and integration.
*   Connector Programming: for custom connector connect endpoint

We separate book for connector in another book. We will focus on the java programming first. This chapter introduces functional and purpose of each APIs.

Synchronous vs. Asynchronous Phase

Before we start any API concepts, you need to understand Synchronous vs. Asynchronous Phase. Admin task execution has the following two phases:

*   Synchronous Phase is processing during the task is submitted and response to user on screen. The task has not yet been broken down into its component events.
*   Asynchronous Phase is process after response display on screen to user. The task has been broken down into its component events. It may take time up to an hour or a month.

| ![](OEBPS/image_rsrc8TE.jpg) |
| Figure 3-1 shows Synchronous and Asynchronous phase |

### 3.1.1 Business Logic Task Handler API (BLTH)

Business Logic Task Handler or BLTH API can perform logic at admin task level. The BLTH run in synchronous phase, it can execute before admin task render and execute after admin task is submitted. (but before any events create)

| ![](OEBPS/image_rsrc8TF.jpg) |
| Figure 3-2 shows Business Logic Task Handler API works before and after admin task. |

This API is very useful, we will use frequency. We can access user store from BLTH.

Examples of BLTH:

*   Administrator executes the admin task; BLTH can initial some values on screen.
*   Administrator submits the admin task; BLTH validates the fields on screen.
*   Administrator submits the admin task; BLTH performs the logic or modify user’s attributes in user store.

### 3.1.2 Workflow API

The workflow API is very important in the real world requirements. The workflow can work at admin task level or event level.

| ![](OEBPS/image_rsrc8TG.jpg) |
| Figure 3-3 shows workflow can specific at admin task level or event level |

The workflow is required when:

*   Your requirement needs approval
*   Business logic requires a long processing time. We can use workflow implement business logic in event level. It will run in asynchronous phase. Compare to BLTH runs in synchronous phase, it does not fit for long processing time.

This book, we will learn how to create custom workflow by software WorkPoint.

Examples of workflow:

*   If users’ office is New York, this task requires 2 approvers. If users’ office is London, this task requires one additional approver.
*   The requirement requires enable an account on hiring date.

### 3.1.3 Participant Resolver API

This API is used as part of workflow. Participant Resolver API answers to the question; who is approver. We can implement conditions for looking approver.

Example:

*   We want manager of manager is approver.

| ![](OEBPS/image_rsrc8TH.jpg) |
| Figure 3-4 shows the workflow has approver that require Participant Resolver API |

### 3.1.4 Event Listener API

We can implement custom listener to listen event. When the event occurs, the event listener performs business logic during particular states of execution: before, after, fail, approve, reject. Event Listener runs under asynchronous phase.

Examples:

*   After user is created successfully, send message to MQ.
*   If administrator rejects on any modify user event, listener writes log file.

| ![](OEBPS/image_rsrc8TJ.jpg) |
| Figure 3-5 shows Event Listener API can listen to the event. |

### 3.1.5 Logical Attribute API

Logical Attribute API displays an attribute differently than how it is stored physically in a user directory. This API should be used when you have the attribute share in many screens and you do not want to do translation logic the value on every screen.

Example:

*   You have physical attribute “BusinessCategory” keeps values as code: 1001, 2001, or3001 but on screen display as Advertising, Retail, or Telecommunications.

| ![](OEBPS/image_rsrc8TK.jpg) |
| Figure 3-6 shows Logical Attribute API convert physical value to logical on screen. |

### 3.1.6 Validation Rules

It is used validate field’s value on screen. You can write rule at:

*   Task-level, it will validate on specific screen.
*   Directory-level, it will validate that field every time on any screen.

Example:

*   The employee number must be number only.

### 3.1.7 Email Template

There are 2 ways to sending email from CA IdentityMinder.

*   Email Notification Policies.
*   Email templates

The email template API is the one of them. We can implement by writing template file.

### 3.1.8 Notification Rule

The notification rule determines who receive an email.  The notification rule use within email template only.

Example:

*   Sending email to HR manager after task update location complete.

    *   The email template is used for generating email content and when email should send.
    *   The notification rule is used for getting HR manager’s email.

### 3.1.9 Task Execution Web Service (TEWS)

We want to the third party system execute our admin task, we have to enable TEWS feature.  The TEWS enables the admin task as web services’ provider.             

Examples:

*   A user uses a web portal to modify address. The portal calls the enterprise service bus (ESB) and then ESB calls web services of admin task to update address. 

## 3.2 Task Phases

We already talked about overview Synchronous and Asynchronous Phase. This section will explain phase details of admin task execution and when each APIs will be executed.

You do not need to memorize the whole things right now, when you practice example in this book, you will memorize them automatically.

### 3.2.1 Synchronous Phase Operations

1.  The user selects an admin task to perform.

*   Business Logic Task Handler API: call handleStart() method.

2.  The admin task subject is selected but not yet displayed.

*   Business Logic Task Handler API: call handleSetSubject() method.
*   Default values for fields can be initialized with JavaScript or hard-code.
*   Fields associated with physical attributes are automatically populated with the corresponding data from the data store.

3.  CA IdentityMinder displays and populates the task screen.

*   Logical Attribute: call method toLogical(); to convert physical attributes.

4.  CA IdentityMinder invokes Validation Rules during data entry when user click validate button (if you have) or user change tab or you have logic to validate on change.
5.  User submits the task screen.

*   Invoke Validation Rules.
*   Logical Attribute API: call method validate() to performs field-level validation.
*   Logical Attribute API: call method toPhysical() to converts logical attributes back to their corresponding physical attributes
*   Business Logic Task Handler API: call method handleValidation() to perform task-level validation

6.  User submits the task screen.

If validation errors occur, the errors are reported to the user immediately. The user is allowed to correct the errors and resubmit the task.

7.  CA IdentityMinder instantiates events for the task.

After all validation is performed successfully, CA IdentityMinder creates events. Each transaction is represented by an event.

8.  The task enters the asynchronous phase for processing.

There are 3 major APIs: Business Logic Task Handler, Validation Rules and Logical Attribute execute under synchronous phase.  The picture below shows the screen after submit admin task. The message “Task pending” means there are event processing behind this task or asynchronous phase is starting from now on.

| ![](OEBPS/image_rsrc8TM.jpg) |
| Figure 3-7 shows screen display Task pending |

### 3.2.2 Asynchronous Phase Operations

1.  CA IdentityMinder posts the events.
2.  Event Listeners Perform Pre-Approval Attribute Updates

    *   Event Listener API: call method before();
3.  Custom Objects Perform Operations During Workflow Processing

    *   Participant Resolver API: If workflow specify the participants (approvers) for a workflow activity, call method resolve() to return list of participants.
    *   Workflow API: start. If workflow is enabled, and an event is mapped to a workflow process, the activities in the workflow process must be completed before the event can be completed.
4.  Event Listeners Perform Pre-Execution Attribute Updates

*   A workflow process results in either the approval or rejection of the associated event.
*   When a workflow process is approved, CA IdentityMinder executes the associated event.

    *   Event Listener API: call method approve() or reject()

5.  CA IdentityMinder Executes the Event
6.  Event Listeners Perform Post-Execution Operations

    *   Event Listener API: call method after()

7.  CA IdentityMinder Generates Email Notifications

    *   Email Template API, Notification Rule API are called.

There are 5 APIs: Event Listener, Workflow, Participant Resolver, Email Template, and Notification Rule are used under asynchronous phase.

## 3.3 Configuring IDE

We use Eclipse as IDE to develop code. Please download from book’s web site.

Class path

Please check Project Properties > Java Build Path.

If you use version 12.6,

*   Create class path variable: IDM_LIB

    *   Select windows> preference> class path variable > new
    *   Set to path <server>\IdentityMinder.ear/library

        *   If you use WebLogic, all jars locate at APP-INF\lib

| ![](OEBPS/image_rsrc8TN.jpg) |
| Figure 3-8 shows class path variable |

If you use version 12.5, remove all my jars

*   Add all jar from deploy folder <server>\IdentityMinder.ear\library

    *   If you use WebLogic, all jars locate at APP-INF\lib
*   Add indentitymanager.jar from <server>IdentityMinder.ear\user_console.war\WEB-INF\lib

Import projects

*   Run Eclipse and select import > Existing projects into Workspace.
*   Browse archive file, select a project, and click finish.

| ![](OEBPS/image_rsrc8TP.jpg) |
| Figure 3-9 shows import project |

## 3.4 Conclusions

This chapter introduces 9 APIs of CA IdentityMinder: what they are and when they execute. We have already explained about task phase: synchronous and asynchronous phase.

*   Synchronous phase: Business Logic Task Handler, Validation Rules and Logical Attribute.
*   Asynchronous phase: Event Listener, Workflow, Participant Resolver, Email Template, and Notification Rule.
*   The Task Execution Web Service enables the admin task as web services’ provider

CA provides java doc of each APIs through bookshelf > CA IdentityMinder > programming > Javadoc Programming Reference. The next chapter will go in details of Business Logic Task Handler API.

# Chapter 4 Business Logic Task Handler

Business Logic Task Handler API or BLTH is the API to perform business logic at admin task level. There are the unique characters of Business Logic Task Handler:

*   Business Logic Task Handler API works at admin task session level.
*   Business Logic Task Handler API executes under synchronized phase

    *   It means users have to wait until the logic complete.
*   Business Logic Task Handler API must be complete before any events created.

    *   Business Logic Task Handler API is good for:
*   Validating and formatting task screen fields.
*   Enforcing custom business logic that require response immediately (synchronous)

## 4.1 Programming and Configuration Concepts

Business Logic Task Handler API can implement by Java or server side Java script. Our book use only Java language. For server side Java script, you can see in the details official document. We will use java as the one language for every APIs and we can gain benefit from java utility library also. 

### 4.1.1 Programming

Implementation Business Logic Task Handler API, we just create java class and extend BLTHAdapter class and override the methods.  Each methods is call-back method will be execute during admin task‘s life cycle.  You can choose implement some or all of the methods depending on your requirement:

*   handleStart(): will execute at the beginning of the task.
*   handleSetSubject(): will execute after selecting the subject (for example select user) from the search result. It uses set initial value on screen.
*   handleValidation():will execute after the user has submitted the task. It is validation.
*   handleSubmission(): will execute after handleValidation(). It uses to perform logic.

Development Steps

1.  Writing java code which extends BLTHAdapter.
2.  Compiling and make sure there is no error and use JDK version same as server version.
3.  Copy class file (include package folder) to folder “\IdentityMinder.ear\custom”

### 4.1.2 Configuration

Business logic task handlers can be configured by 2 ways of scope:

*   Global business logic task handlers: This level means it will be applied to all admin tasks. Our java code will be executed every time when any admin tasks are called.
*   Task-specific business logic task handlers: this java code will be executed with specific admin tasks that are configured. This scope will be used frequency in this book.

Global business logic task handlers

They are configured in the Management Console and select Home > Environments > <your server> > Advanced Settings > Business Logic Task Handlers

| ![](OEBPS/image_rsrc8TR.jpg) |
| Figure 4-1 shows screen for global business logic task handlers |

You can click button “New” configure Business Logic Task Handler. The each field on configuration screen is same as the task-specific business logic task handlers.

Task-specific business logic task handlers

This level will apply to on specific admin tasks. There are steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Search admin task name
3.  To click button “Business Logic Task Handlers”, then click “Add” button to specific java class name.

| ![](OEBPS/image_rsrc8TS.jpg) |
| Figure 4-2 shows button “Business Logic Task Handlers” for task specific |

## 4.2 Task Session

A task session is an instance of an executing task. During task execution, business logic task handlers can access to the information in the current task session. Task session information is available through the BLTHContext. The Interface provides methods for retrieving the run-time instances of managed objects in the current task session, for example:

*   Method getUser()*: retrieves the User object involved in the current task.

    *   Please note, getUser() will work, if admin task has primary object is User, for example modify user. If your admin task is modify endpoint, it does not make sense to call getUser().
*   Get any relationship objects (such as roles and groups).

BLTHContext inherit from many parent interfaces:

*   TaskInfo: information about the current task for examples: getSubject() return primary object.
*   IMContext: provides method about session that uses to share session between APIs. This interface provides method getAuxDataRoot() to access the root of the auxiliary data tree also.
*   ProviderAccessor: provides direct access to any managed objects in the data store. We will talk about the managed object in next section.

## 4.3 Access to Managed Objects

Managed object means object in the data store such as user or account. A business logic task handler can access a managed object in the following 2 ways:

By ProviderAccessor

The Provider Accessor is parent class of BLTHContext:

*   Can access any managed object.
*   Can access any attributes in managed object.
*   When call modifyObject(), any changes made to a managed object are immediately persist to the data store.

    *   No events are generated, and no workflow approvals, auditing, or security checks are performed.

By Context

The Context in this chapter means BLTHContext but other chapters mean WorkflowContext, EventContext etc.

*   Limit access to the task session includes the subject (primary object) of the task and the subject’s relationships.

    *   For example admin task: Modify User. The context can access only User object is the managed objects of this task.
*   Limit access the attributes

    *   For example if admin task defines only city attributes of user object, you cannot access attribute country of user object.
*   Any changes will commit when event is complete. 

    *   For example you use BLTHContext to modify city attribute, but user modify event fail or workflow (inside event) are rejected. The city attribute will not commit.
    *   CA IdentityMinder generates events for the task, and workflow approvals, auditing, and security checks can be performed.

| ![](OEBPS/image_rsrc8TT.jpg) |
| Figure 4-3 shows 2 ways to access managed object. |

The below table compare the different between BLTHContext and ProvideAccessor.

| Topic | ProviderAccessor | BLTHContext |
| Access Object | Can access any managed objects. | Access only objects that are related in task session. |
| Access Attributes | Can access any attributes. | Limit access, depending when you define admin task. |
| Modify values | When call modifyObject(),  modified values are immediately committed in the data store. | The values are not committed, until the event has been complete. |
| Events | No additional events are generated. | Relate to event associated with the task |

We will cover more details of managed object by example in next section and next chapters.

## 4.4 Code Examples

CA IdentityMinder programming part, we use java project named: “IdmCode”. We reuse admin task from previous chapter. We will execute admin task with Business Logic Task Handler API only, so we need to disable Identity Policy Set and policy Xpress from previous chapter.

| ![](OEBPS/image_rsrc8TU.jpg) |
| Figure 4-4 shows disable Identity Policy Set and Policy Xpress by uncheck enable check box |

### 4.4.1 Basic programming: BLTHAdapter and life cycle

This example shows step by step the basic programming of Business Logic Task Handler.  The CA IdentityMinder programming always requires 2 parts: coding and configuration. This example just show Business Logic Task Handler API life cycle. We will print in log file.

Code

1.  Run the eclipse and select java class:

*   Package:  com.book.idm.blth
*   Class: BasicLifeCycle
*   Extend BLTHAdapter

The list below show our code

| package com.book.idm.blth;import com.netegrity.imapi.BLTHAdapter;import com.netegrity.imapi.BLTHContext;public class BasicLifeCycle extends BLTHAdapter{@Overridepublic void handleStart(BLTHContext blthContext) throws Exception {System.out.println("UpdateLocationExtNumber:handleStart");}@Overridepublic void handleSetSubject(BLTHContext blthContext)throws Exception {System.out.println("UpdateLocationExtNumber:handleSetSubject");}@Overridepublic void handleValidation(BLTHContext blthContext)throws Exception {System.out.println("UpdateLocationExtNumber:handleValidation");}@Overridepublic void handleSubmission(BLTHContext blthContext)throws Exception {System.out.println("UpdateLocationExtNumber:handleSubmission");}} |

2.  Compile and copy class (include package folder ” com.book.idm.blth” ) to folder “\IdentityMinder.ear\custom”

Configuration

There are 2 type of configuration: global business logic task handlers and task-specific business logic task handlers. We choose task-specific business logic task handlers for all our examples.

1.  Search our admin task name: Update Location and Ext Number
2.  To click button “Business Logic Task Handlers”, then click “Add” button to specific java class name.
3.  Put value as below

| Field Name | Value | Description |
| Name | BLTHExample | Name of business logic task handler |
| Java Class | com.book.idm.blth.BasicLifeCycle | Our java class name that we put in custom folder |

| ![](OEBPS/image_rsrc8TV.jpg) |
| Figure 4-5 shows screen Business Logic Task Handler Details |

4.  Click ok and submit this admin task.

How it works

We can execute our code by admin task following these steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select menu: Basic.
3.  Select Admin Task: “Update Location and Ext Number”.

| ![](OEBPS/image_rsrc8TW.jpg) |
| Figure 4-6 shows select admin task |

The Log file shows:

| INFO [STDOUT]UpdateLocationExtNumber:handleStart |

4.  Then search and select some users. When admin Task was displayed, Log file will show:

| INFO  [STDOUT]  UpdateLocationExtNumber:handleSetSubject” |

| ![](OEBPS/image_rsrc8TX.jpg) |
| Figure 4-7 shows admin task screen display |

5.  Modify city’s attribute (you have to modify city value) and submit admin task, log will display:

| INFO [STDOUT] UpdateLocationExtNumber:handleValidationINFO [STDOUT] UpdateLocationExtNumber:handleSubmission |

You will see the business logic task handlers’ life cycle, when each method of BLTHAdapter executes.             

### 4.4.2 Modify user’s attributes by BLTHContext

This example will demo how to use BLTHContext:

*   Modify city attribute to be “New City”.
*   Get information about the current task from parent interface: TaskInfo

Code

1.  Compile our java code: com.book.idm.blth. ModifyUserByBLTHContext.
2.  Copy class (include package folder ” com.book.idm.blth” ) to folder “\IdentityMinder.ear\custom”.

Configuration

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu modify admin task.
3.  Search and select our admin task name: Update Location and Ext Number
4.  Click button “Business Logic Task Handlers”, then icon “pencil”.

| ![](OEBPS/image_rsrc8TY.jpg) |
| Figure 4-8 shows icon “pencil” to modify java class |

5.  Modify value as below

| Field Name | Value | Description |
| Java Class | com.book.idm.blth.ModifyUserByBLTHContext | Our java class that we put in custom folder |

| ![](OEBPS/image_rsrc8TZ.jpg) |
| Figure 4-9 put value of new java class |

How it works

We can execute our code by admin task following these steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select menu: Basic.
3.  Select Admin Task: “Update Location and Ext Number”.
4.  Then search and select some users.
5.  Modify city’s attribute (you have to modify city value) and submit admin task.

Access user object

The result of city’s attribute will be “New City”. They do not care whatever value you select on screen because our code set the value. We set city attribute in method handleSubmission().

| //Access User ObjectUser user = blthContext.getUser();user.setAttribute("l", "New City"); |

In code, we access user object through BLTHContext.getUser() and we set attribute: city. There is one interesting thing is attribute name. The user object use attribute name that represent in user store. The lower case of L means city. You can use any LDAP client to connect user store and see user’s attribute name.

| ![](OEBPS/image_rsrc8U0.jpg) |
| Figure 4-10 shows attribute name “l” in user store |

Access task information

We have another part of code that accesses some information from admin task.

| //Get information about the current task from TaskInfoSystem.out.println("Admin task name: "+blthContext.getTaskFriendlyName());System.out.println("Who execute this task: " +blthContext.getAdminFriendlyName());System.out.println("Managed Object: "+blthContext.getSubject());System.out.println("Action type: "+blthContext.getActionType().getFriendlyName()); |

When admin task is submitted, log file will display as below:

| INFO  [STDOUT] Admin task name: Update Location and Ext NumberINFO  [STDOUT] Who execute this task: superuserINFO  [STDOUT] Managed Object: [allmi01] uid=allmi01, ou=users,                                 ou=northamerica,dc=ForwardInc,dc=caINFO  [STDOUT] Action type: Modify |

View submitted task

View submitted task is useful information for debug our code. When task complete, select “View submitted task” under tab “System”. Select our task, it should display as the first one.

| ![](OEBPS/image_rsrc8U1.jpg) |
| Figure 4-11 show our task |

After task submitted, CA IdentityMinder will create the events. Select event name “Modify user”.

| ![](OEBPS/image_rsrc8U2.jpg) |
| Figure 4-12 displays events in our task |

In Modify user event, we will see city value has been changed. The attributes change following our java code, not on screen.

| ![](OEBPS/image_rsrc8U3.jpg) |
| Figure 4-13 displays changed attribute in event |

Subject of admin task

When we create admin task, you have to specific what is primary object and what is action. In our admin task choose primary object is “user” and action is “modify”.

| ![](OEBPS/image_rsrc8U4.jpg) |
| Figure 4-14 shows primary object and action in admin task configuration |

You can use blthContext.getUser() because this admin task has primary object is user. The primary object does need to be user. It can be account or endpoint object. There is another way to access the primary object of this task by method getSubject() return primary object. This code below modifies the attribute of primary object.

| //User user = blthContext.getUser();//user.setAttribute("l", "New City");blthContext.getSubject().setAttribute("l", "New City"); |

### 4.4.3 Modify user’s attribute by ProviderAccessor

We will use business logic task handler modify telephone number by ProviderAccessor API.

Code

1.  Compile our java code: com.book.idm.blth. ModifyUserByProviderAccessor.
2.  Copy class (include package folder ” com.book.idm.blth” ) to folder “\IdentityMinder.ear\custom”.

Configuration

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu modify admin task.
3.  Search and select our admin task name: Update Location and Ext Number
4.  Click button “Business Logic Task Handlers”, then icon “pencil”.
5.  Modify value as below.

| Field Name | Value | Description |
| Java Class | com.book.idm.blth.ModifyUserByProviderAccessor | Our java class that we put in custom folder |

| ![](OEBPS/image_rsrc8U5.jpg) |
| Figure 4-15 put value of new java class |

How it works

We can execute our code by admin task following these steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select menu: Basic.
3.  Select Admin Task: “Update Location and Ext Number”.
4.  Search and select some users.
5.  Modify city’s attribute (you have to modify city value) and put the value “xxxxxx” in phone extension number. Submit the admin task.

| ![](OEBPS/image_rsrc8U6.jpg) |
| Figure 4-16 shows values for our task |

Using ProviderAccessor

Using providerAccessor means using any method of ProviderAccessor is parent class of BLTHContext. For examples: getUserProvider(), getGroupProvider(), etc . The name of method will end with word provider. Each managed object type (such as User, Group, and Organization) is associated with a provider object that you use to access the managed object's data.

| User user = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null); |

BLTHContext has parent interface: ProviderAccessor. When we call getUserProvider, it returns UserProvider. The UserProvider has method findUser()

| findUser(TSContext context, java.lang.String name, AttributeRightsCollection attributes) |

This method requires 3 arguments:

*   context: Context information of the current task session. Our code uses BLTHContext.
*   name: The name of the user to retrieve. The name can be a unique name or a friendly name. Our code uses unique name of user.

| //Get unique name from taskString userid = blthContext.getUser().getUniqueName(); |

*   attributes: A collection of AttributeRight objects, each containing an attribute name and a permission request. Our code pass null value.

We get user object from ProviderAccessor. We can modify telephone number attribute. The attribute name is same as physical attribute’s name of user store.

| user.setAttribute("telephoneNumber", "212-222-2222x1234");user.modifyObject(); |

We modify a managed object through ProviderAccessor, we are changing the local (in-memory) representation of the object. To persist the changes to the data store, we need to call modifyObject(). The changes are then made directly to the data store. No Identity Manager events are generated, and no workflow approvals, auditing, or security checks are performed.

Check the results in user store

We did the 2 things: change city attribute and our java code use AccessProvider to modify telephone number. Use LDAP client to connect to user store, we will see telephone number value has been changed.

| ![](OEBPS/image_rsrc8U7.jpg) |
| Figure 4-17 shows telephone number attribute has been changed |

Check the results in view Submitted task screen

Select menu: view submitted task, under tab: system.  Select our task, you will see events inside.

| ![](OEBPS/image_rsrc8U8.jpg) |
| Figure 4-18 shows all events |

Click Modify User event to see attributes changes: 

*   The city attribute came from screen to modify value in user store.
*   The telephone number, we use ProviderAccessor to modify. So attributes changed in Modify User event, we don’t see value from ProviderAccessor but we see only the value from screen.

| ![](OEBPS/image_rsrc8U9.jpg) |
| Figure 4-19 shows attributes changed after submitted |

The sequence of modification

Now we have 2 attributes to provision: city and telephone number:

*   The city value came from screen.
*   The telephone number value came from ProviderAccessor.

    *   On screen, we put the value “xxxxxx”  
    *   The final result is “212-222-2222x1234”

If your environment setup for provisioning and active directory accounts, you will see telephone attribute in endpoint is “212-222-2222x1234”.

| ![](OEBPS/image_rsrc8UA.jpg) |
| Figure 4-20 telephone number was provisioned to endpoint |

We can explain step by steps as:

*   Step 1: When user submit admin task, the method handleSubmission() execute. The telephone number will be commit when method modifyObject() is called.
*   Step 2: Modify user event has been generated. When modify user event complete. CA IdentityMinder will commit the city value.
*   Step 3: Synchronize User event, it is not relate. It will trigger Policy Set.
*   Step 4: Synchronize User Attribute with Account will provision attributes from provisioning directory and to endpoint.

| ![](OEBPS/image_rsrc8UB.jpg) |
| Figure 4-21 shows steps of provisioning |

### 4.4.4 BLTHContext and ProviderAccessor

This example is kind of experiment for better understanding BLTHContext and ProviderAccessor. We will try to update city and telephone attribute by using both APIs. Let see what is going on.

Code

1.  Compile our java code: com.book.idm.blth. ModifyUserByBoth
2.  Copy class (include package folder ” com.book.idm.blth” ) to folder “\IdentityMinder.ear\custom”.

Configuration

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu modify admin task.
3.  Search and select our admin task name: Update Location and Ext Number
4.  Click button “Business Logic Task Handlers”, then icon “pencil”.
5.  Modify value as below.

| Field Name | Value | Description |
| Java Class | com.book.idm.blth.ModifyUserByBoth | Our java class that we put in custom folder |

We can execute our code by admin task following these steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select menu: Basic.
3.  Select Admin Task: “Update Location and Ext Number”.
4.  Then search and select some users.

Modify attributes by using BLTHContext

Let see the first version of our code inside method handleSubmission(). We comment every things about ProviderAccessor.

| //Using BLTHConextUser user1 = blthContext.getUser();user1.setAttribute("l", "New City");user1.setAttribute("telephoneNumber", "1111111");//Using ProviderAccessor/*String userid = user1.getUniqueName();User user2 = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);user2.setAttribute("l", "New Town");user2.setAttribute("telephoneNumber", "2222222");user2.modifyObject();*/ |

Execute admin task: Update Location and Ext Number. We will get error with the telephone attribute.

| ![](OEBPS/image_rsrc8UC.jpg) |
| Figure 4-22 screen shows errors |

We got error about the presence of attribute: telephoneNumber.  When you use BLTHContext to modify the attributes, you have to concern “fields” that are defined in this admin task.             

| ![](OEBPS/image_rsrc8UD.jpg) |
| Figure 4-23 shows all attributes defined in our admin task |

BLTHContext can modify any attributes defined in admin task. If you try to modify any attributes outside scope (for example: telephone number), you will get exception.

Modify attributes by using ProviderAccessor

The next version of our code, we comment the problem line (modify telephone number) and uncomment ProviderAccessor part. Compile and deploy code to server.

| public void handleSubmission(BLTHContext blthContext) throws Exception {//Using BLTHConextUser user1 = blthContext.getUser();user1.setAttribute("l", "New City");//user1.setAttribute("telephoneNumber", "1111111");//Using ProviderAccessorString userid = user1.getUniqueName();User user2 = blthContext.getUserProvider().findUser(      blthContext.getTSContext(), userid, null);user2.setAttribute("l", "New Town");user2.setAttribute("telephoneNumber", "2222222");user2.modifyObject();} |

Execute our admin task again and see the result. On the screen, we select city value as: Toronto.

| ![](OEBPS/image_rsrc8UE.jpg) |
| Figure 4-24 we change city value as Toronto |

Now we have 3 places set one city attribute:

1.  On screen set value as“Toronto”.
2.  BLTHContext modify city value as “New City”.
3.  ProviderAccessor modify city value as “New Town”.

Which one is the winner? The final result is:

*   City is “New City”
*   Telephone Number is “2222222”

| ![](OEBPS/image_rsrc8UF.jpg) |
| Figure 4-25 shows the final result |

We can see step by steps:

*   Step 1: User entry city attribute value as “Toronto”.
*   Step 2: BLTHContext override city attribute value as “New City” but not commit.
*   Step 3: ProviderAccessor commit city attribute value as “New Town”. Now city attribute has been already change to be “New Town”
*   Step 4: When modify User event complete, CA IdentityMinder commit the city attribute value from task that has been modify by BLTHContext.  

Step 1 – 3 are occurred in synchronous phase. Step 2 and 3 are occurred by business logic task handler. The step 4 is asynchronous phase.

| ![](OEBPS/image_rsrc8UG.jpg) |
| Figure 4-26 shows sequence of modification |

### 4.4.5 Business Logic Task Handler and screen.

This example, we will do programming to get data from admin task’s screen. This example shows:

*   How to get current extension telephone number and display on screen.
*   Validate user input. The extension telephone number must be present and be number only.
*   Shows how to send error message back to user.
*   Using session attribute to share the extension telephone number between methods.

Code

1.  Compile our java code: com.book.idm.blth. ModifyUserAndScreen
2.  Copy class (include package folder ” com.book.idm.blth” ) to folder “\IdentityMinder.ear\custom”.

Configuration

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu modify admin task.
3.  Search and select our admin task name: Update Location and Ext Number
4.  Click button “Business Logic Task Handlers”, then icon “pencil”.
5.  Modify value as below.

| Field Name | Value | Description |
| Java Class | com.book.idm.blth.ModifyUserAndScreen | Our java class that we put in custom folder |

How it works

We can execute our code by admin task following these steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select menu: Basic.
3.  Select Admin Task: “Update Location and Ext Number”.
4.  Then search and select some users.

handleSetSubject(): display the current telephone number on screen

The method handleSetSubject() is called, when screen initial display. So we implement to set the show extension number inside this method.              

| ![](OEBPS/image_rsrc8UH.jpg) |
| Figure 4-27 the current value of extension number has been show on screen |

Setting extension number, we have to do 2 things:

*   Get current telephone number
*   Set the value of screen logical attribute: |ExtNumber|

Getting the current telephone number is not new, we use the ProviderAccessor get the value.

| String userid = blthContext.getUser().getUniqueName();User user = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);String telephoneNumber = (String)user.getAttribute("telephoneNumber"); |

Please imagine the screen of admin task. When we define the admin task:

*   Inside of admin task, we have tabs.
*   In our admin task has one profile tab.
*   Inside of tab, we have a screen. 
*   Inside of screen, we have fields.

| ![](OEBPS/image_rsrc8UJ.jpg) |
| Figure 4-28 shows tab screen in admin task configuration |

Inside of admin task, we have tabs. We call method getTaskTabHandlers() return all tabs of this admin task.

| Vector<TabHandler> tabs = blthContext.getTaskTabHandlers();for (TabHandler tab : tabs) { |

In our admin task has one profile tab, so we have to check type of ProfileTabHandler.  If you have many profile tabs, you need condition to check screen’s tag name. We check screen’s tag name “BookBasicUpdateLocationAndExtNo”. (In our example has only one tab, you can skip this condition)

| // Check tab typeif (tab instanceof ProfileTabHandler) {ProfileTabHandler profileTab = (ProfileTabHandler) tab;String screenName = profileTab.getScreenHandler().getScreen().getTag();if(screenName.equals("BookBasicUpdateLocationAndExtNo")){ |

We can set the value on screen by using method updateRawData().

| HashMap<String, String> data = new HashMap<String, String>();data.put("&#124;ExtNumber&#124;", telephoneNumber.substring(telephoneNumber.indexOf("x") + 1));...profileTab.updateRawData(data); |

Inside of screen, we have fields. We create new HashMap object. We put key and value pair, key’s name |ExtNumber| came from the screen definition in admin task. If you want to set city attribute, you can use attribute name same as user store.  The city’s attribute uses “l” as key.

handleValidation (): validate user input

After user submit the admin task, if extension number is blank or put some characters, the error will be display.

| ![](OEBPS/image_rsrc8UK.jpg) |
| Figure 4-29 shows error messages |

We have to override method handleValidation (). We can get any fields from screen by method getRawData(). If you are not sure about fields’ name, you can print by method getRawData(). It is a HashMap object that key represent by field’s name.

| String extNumber = (String) profileTab.getRawData().get("&#124;ExtNumber&#124;"); |

You can get the values from the screen and perform the validation logic as code below.

| String extNumber = (String) profileTab.getRawData().get("&#124;ExtNumber&#124;");if (extNumber == null) {...} else {try {int number = new Integer(extNumber);  } catch (NumberFormatException ne) {...}} |

Shows the error message

We show error by throwing IMSException object. You can put message display on screen by method addUserMessage().

| IMSException imsEx = new IMSException();imsEx.addUserMessage("Telephone number can't be empty");throw imsEx; |

Session attributes: pass the value between methods

We have already validated telephone number and we can pass the valid telephone value to method handleSubmission() by session. BLTHContext provide session attribute for sharing data between method and other CA IdentityMinder APIs.

| public void handleValidation(BLTHContext blthContext) throws Exception {// Setting value to sessionblthContext.setSessionAttribute("extNumber", number);…}public void handleSubmission(BLTHContext blthContext) throws Exception {// Getting value from sessionint extNumber = (Integer) blthContext.getSessionAttribute("extNumber");} |

## 4.5 Use cases examples

The official CA IdenityMinder document gave use cases examples but not provide detail of programming. This section will give you some idea of those examples.

Please see full description from Programming Guides › Programming Guide for Java › Business Logic Task Handler API › Business Logic Task Handler API Overview › Use Case Examples.

Check whether a group membership limit is reached

| When an administrator attempts to add a member to a group by submitting a Modify Group task for execution, access the Group managed object to determine the number of current members. If the group has the maximum number of members, throw an exception. |

The modify group task, we can use BLTHContext,getGroup(). We call method getMembers() return all members inside group. We can check size.  

| Vector users = blthContext.getGroup().getMembers(ObjectType.USER, null);System.out.println(“user size : “+users.size()); |

Please note, the Group class has method getUsers() and getMembers():

*   Method getUsers() return only user object
*   Method getMembers() can return any object depending parameters: ObjectType . Please see java document: ObjectType for details.

Verify the job title of a new administrator

| When a user submits a Create Administrator task for execution, access a third-party database to determine the job title of the administrator being created. If this particular person does not have the job title Supervisor (the only job title authorized to be an administrator), throw an exception. |

We can write java code access the database in handleSubmission().  You pass administrator id as argument and get job title.

| //Get administrator who is executing the taskUser admin = blthContext.getAdministrator();//Call the third party to get titleString jobTitle = callDB(admin.getFriendlyName()); |

Check for duplicate objects

| CA IdentityMinder is shipped with a predefined business logic task handler that checks for possible duplication of objects before object creation. For example, the name of a newly created role must be unique. When a role is about to be created, the predefined business logic task handler validates whether the name of the new role already exists. If the name does exist, the handler throws an exception indicating that the role name must be unique, and the administrator has the opportunity to change the name and resubmit the task. |

We can write code by using ProviderAccessor search role name.

| 1oolean isUnique = false;try{//Search by friendlyNameAccessRole role = blthContext.getAccessRoleProvider().findAccessRole(roleName);}catch(NoSuchObjectException e){isUnique = true;}if(!isUnique){IMSException imsEx = new IMSException();imsEx.addUserMessage(“The role name must be unique”);throw imsEx;} |

Disable a user account after the maximum failed login attempts

| After a user fails to log in three consecutive times, the account is immediately disabled in the data store. Because the account is updated directly in the data store rather than in the task session, CA IdentityMinder does not generate an event for this action, and any workflow approval process, auditing, and security checks that may be associated with this action are bypassed. After the final login attempt, a custom message advises the user that the account is disabled. |

The use case said the user account is updated (disable) directly in the data store.  This use case mean using ProviderAccessor update user attributes directly. (For update account attribute directly, please see book volume II)

Assign a user to a group during self-registration

| A user who self-registers with the job title Benefits Administrator is assigned to the group HR. This update is made in the task session, through a call to assignResources() in RelationshipTabHandler. This update triggers the event AddToGroupEvent, allowing the group assignment to be subject to auditing and workflow approval. |

We use business logic task handler modify the value in tab as below code.

| For (TabHandler tab : tabs) {RelationshipTabHandler rTab = (RelationshipTabHandler)tab;rTab.assignResources(groups);} |

Assign “manager” attribute for a new user

| An administrator wants to set a value of “manager” before the profile is displayed on the screen. A business logic task handler could be written that would implement the handleSetSubject() method for initialization. This method would assign the administrator’s name to the attribute for the manager’s name. If the name of the administrator is not available, an exception is thrown. |

We write code in method handleSetSubject to initial the manager attribute.

| Public void handleSetSubject(BLTHContext blthContext) throws Exception {String managerId = blthContext.getAdminFriendlyName();if(managerId == null){throw new IMSException(“administrator’s name is not available”);}HashMap<String, String> screenFields = new HashMap<String, String>();screenFields.put(“managerId”, managerId);tab.updateRawData(screenFields);} |

## 4.6 Conclusion

This chapter we learn basic programming of Business Logic Task Handler API Concepts. We can make short note as follow:

Implement business logic task handler

*   There are 2 steps: coding and configuration.
*   For Coding, you have to write java class that extends BLTHAdapter and override methods as need.

    *   handleStart(), it will call when user select admin task.
    *   handleSetSubject() for setting field before display.
    *   handleValidation()  for validating.
    *   handleSubmission() will execute when user submit, after validation.
    *   Compile and copy to folder “\IdentityMinder.ear\custom”.
*   There are 2 levels of BLTH configuration: global and task-specific.

Access to managed objects

*   There are 2 ways: by ProviderAccessor and BLTHConext (task session)
*   BLTH, we have to consider:

    *   What is primary object?
    *   The modified attributes are defined in admin task?

Programming Note

*   The user’s attribute names in code are the physical names in user store.
*   You can use getRawData() and setRawData() access the values on screen
*   We can display message on screen by IMSException object.
*   We can use session keeps value and share between methods.

The Business Logic Task Handler API performs business logic in synchronous phase. In asynchronous phase, we use workflow perform business logic. The next chapter is workflow.

# Chapter 5 Workflow

The CA IdentityMinder official document does not have much detail about work flow. We learned some basic concepts from previous chapter:

*   If requirement requires approver, you need workflows.
*   Workflow runs under asynchronous phase.
*   Workflows can have a long life. It may take time up to an hour or month.
*   The Business Logic Task Handler has been done before workflow start.

This chapter, you will learn both workflow API and how to create custom workflow.             

## 5.1 Workflow Concepts

You must enable workflow in Management Console. By default, workflow is disabled.

Configuration: Management Console

1.  In the Management Console, select an Environment.
2.  Go to Advanced Settings, Workflow.
3.  Select the Enabled check box, and click Save.
4.  Restart the application server.

| ![](OEBPS/image_rsrc8UM.jpg) |
| Figure 5-1 shows workflow properties in Management Console |

In the event mappings table, there are some default mappings between event and global workflow process. It means when any events in this table start, workflow will be executed. We do not modify any values.

### 5.1.1 Default Workflow Features

This section, we will learn default workflow features in CA IdentityMinder. We cover these topics:

*   Workflow Level, workflow can run admin task or event level.
*   Select Workflows, which workflow can execute.
*   Policy Base, it is condition to start workflow.
*   Task and screen for Approver.
*   Approver, who is approver.
*   Expected Outcome, the final result: approve or reject.

Workflow Level

Workflow can run at Admin task level and/or Event level. What level should be? It is depending on requirements. For example, we have admin task “Modify User”, our admin task has 2 tabs:  Profile Tab and Access Role Tab. So events will be generated from this admin task divides as 2 groups:

*   The first group of events came from profile tab; events will be generated when user’s attributes have been modified.
*   The second group of events came from access role tab; events will be generated when we add or remove access role.

| ![](OEBPS/image_rsrc8UN.jpg) |
| Figure 5-2 shows all events from example admin task. |

We have 2 requests: request to modify user’s attributes from the profile tab and another one request to add/remove role from the access role tab.

*   Senario1: all requests (both modify user’s attributes and add/remove role) need only one workflow for approval, we should specific workflow as Admin Task Level.
*   Senario2: only modify user’s attributes request (profile’s tab) require approver, we should specific workflow at Event Level: ModifyUserEvent.  
*   Senario3: only add role (access role tab) request requires approver, we should specific workflow at Event Level: AssignAccessRoleEvent.  
*   Senario4: Any requests (modify user’s attributes and add/remove role) require Manager as first approver.

    *   Modify user’s attributes request requires HR manager as second approver
    *   Adding role request requires IT manager second approver.

We specific the first approver workflow at Admin Task Level and the HR and IT workflow at Event Level: ModifyUserEvent and AssignAccessRoleEvent. This case shows in the picture below.

| ![](OEBPS/image_rsrc8UP.jpg) |
| Figure 5-3 shows workflow of Senario4 |

Admin Task Level

The workflow at admin task requires to set an attribute TASK_LEVEL=true. You will see it in the example code. Enable work flow at admin task level, you have to configure:

*   On the Profile tab, check Enable Workflow checkbox.
*   On the Profile tab, click the pencil icon at workflow process label. The workflow configuration screen display.

| ![](OEBPS/image_rsrc8UR.jpg) |
| Figure 5-4 shows how to configure workflow at admin task level |

Event Level

Enable work flow at event level, you have to configure:

*   On the Profile tab, verify that Enable Workflow is checked
*   On the Events tab, click pencil icon on events. The workflow mapping screen display, and select a process template.

| ![](OEBPS/image_rsrc8US.jpg) |
| Figure 5-5 shows how to configure workflow at event level |

Select Workflows

You can select workflow from drop down. CA IdentityMinder provides three default process templates:

*   SingleStepApprovalProcess for one primary approver and default participant when primary approver is not found.
*   TwoStageApprovalProcess for two primary approvers and default participant when primary approver is not found.
*   EscalationApprovalProcess for one primary approver and default participant when primary approver is not found. This workflow primary approver can escalate to another approver.

You can create more custom workflow, so we will go details later.

Policy Base

The policy-based is condition before start workflow. The picture below show Policy Base: if user’s city is New York, it requires workflow: TwoStageApprovalProcess.              

| ![](OEBPS/image_rsrc8UT.jpg) |
| Figure 5-6 shows screen of workflow’s policy base |

If request is not met any condition, event or admin task will execute without workflow.

Approver’s Task

If workflow requires approver, we need screen for approver to perform action approve or reject. The picture below show screen to select Approval Task:

| ![](OEBPS/image_rsrc8UU.jpg) |
| Figure 5-7 shows configuration for approver’s screen. |

The picture below shows the example approver’s screen. The icon ![](OEBPS/image_rsrc8UV.jpg) means that value has been changed. You can click to rollback the value.

| ![](OEBPS/image_rsrc8UW.jpg) |
| Figure 5-8 shows screen for approver |

You can create new approver task by create new admin task. You have to choose action as “Approve Event” or “Approve Task”.

Approver

If workflow requires approver, we have to specific who is approver. We can select type of approver form drop down Participant Resolver. It provides condition to get approver.

| ![](OEBPS/image_rsrc8UX.jpg) |
| Figure 5-9 shows drop down: Participant Resolver |

If your requirement getting approver is complicated, you can do programming by using Participation Resolver API. We will learn Participation Resolver API in the next chapter.

Expected Outcome

Working with workflow, we should always aware outcomes: approve or reject. For example, we have admin task with 2 tabs: Profile tab and Access Role tab. We have one Business Logic Task Handler and we set 3 workflows: one at admin task level, one for ModifyUserEvent and one for AssignAccessRoleEvent. The picture below shows all outcomes.

| ![](OEBPS/image_rsrc8UY.jpg) |
| Figure 5-10 shows all outcomes examples |

If you use ProviderAccessor API, you have to aware ProviderAccessor updates user store directly and not depend on workflow. The picture below shows initial value of City is Toronto. And then we use ProviderAccessor API modify City attribute to be New York. Whatever workflows will be rejected or approved, the final value of city is New York.

| ![](OEBPS/image_rsrc8UZ.jpg) |
| Figure 5-11 shows ProviderAccessor API modify attribute’s value |

### 5.1.2 Workpoint Designer Concept

The workflows inside of CA IdentityMinder are created by tools WorkPoint Designer. WorkPoint Designer is 3rd party software and integrated with CA IdentityMinder. You can run Workpoint Designer by command in <admin_tools>\WorkPoint\bin\Designer.bat

| ![](OEBPS/image_rsrc8V0.jpg) |
| Figure 5-12 shows starter screen of Workpoint Designer |

You have to check configuration file “workpoint-client.properties”. The file is located in folder <admin_tools>\WorkPoint\conf. The J2EE Client Configuration must match with your application server.

Processes vs. Jobs

Process and Job is technical term of Workpoint.

*   Processes are a function that a business conducts and normally repeats.
*   Jobs are the process instance.

For example, if the Process is a plan for an order fulfillment process, the specific cases (or Jobs) are the actual orders. Process looks like a Class in java and job is an object or instance of java class.

Processes

Run Workpint Designer, select “Open Process” from menu. Double click on process named “SingleStateApproval”, you will see the process.             

| ![](OEBPS/image_rsrc8V1.jpg) |
| Figure 5-13 shows processes “SingleStateApproval” |

Jobs

Select “Open Job” from menu. Double click on process named “SingleStateApproval” you will see the jobs of this process. (If you executed some admin task that contains workflow SingleStateApproval) You can see the current status of job date created, date started. Select one of them.

| ![](OEBPS/image_rsrc8V2.jpg) |
| Figure 5-14 shows job |

The selected nodes appear as blue color; in picture is node “Approval” and node “IM Reject”. The selected line paths appear as green line.

Using Help

Click menu “Help”, help contents will display as pop up. You can select topic “process definition” and “job definition”.  It shows “What is a Process?” and “What is a Job?”

| ![](OEBPS/image_rsrc8V3.jpg) |
| Figure 5-15 shows help of Workpoint Designer |

Another Workpoint document located in <admin_tools>\Workpoint\docs.

## 5.2 Custom Workflow

The official CA IdentityMinder documents do not tell exactly how to create custom workflow step by steps. The all the rest of this chapter will show how to create custom workflow.

Why we need custom workflow?

The first reason, the default template workflows do not fit our requirements. For example, you may want 3 approvers, the default supports up to 2 approvers.

The second reason, we need integration with other systems or perform some business logic during workflow process. For example:

*   During workflow, we need to call web services.
*   If user’s location is North America, it requires second approver. We have to create routing path to check user’s location.

This section contains 2 parts.

*   Workflow for CA IdentityMinder, you will learn the rule of workflow that relates to CA IdentityMinder. 
*   Workpoint Programming, we introduce some Workpoint API features.

### 5.2.1 Workflow and CA IdentityMinder

When you create workflow for CA IdentityMinder, you have to follow these rules:

Rule 1: Must start with a node “Start” and end with a node “Stop”

It makes sense rule, workflow must have start and end point. In Workpoint designer, you drag node from menu.

| ![](OEBPS/image_rsrc8V4.jpg) |
| Figure 5-16 shows Start and Stop node in Workpoint Designer |

Rule 2: Must have Node “Approve” or “Reject” before go to Node “Stop”

Any workflow, you need to set state to be “Approve” or “Reject” before complete workflow. We need to tell the final result to CA IdentityMinder, it is approved or rejected.

Drag automate node and set configuration:  (You will see details in example code, do not worry)

*   In the resources tab: select external
*   In the agents tab, for approve state, select “Notify IM Approver” and for reject state, select “Notify IM Reject”

| ![](OEBPS/image_rsrc8V5.jpg) |
| Figure 5-17 shows Approve and Reject state before Stop |

Workflow does not always require both approve and reject but workflow must have at least one approve node before node stop. (The work flow has only one reject node does not make sense)

Rule 3: Approver Configuration (If you require approver)

If you require approver, you have to: (You will see details in example code)

*   Drag activity node to canvas
*   In the resources tab: select “IMApprovers”
*   In the agents tab: select “Nobody AutoComplete” to asynchronous
*   In the user data tab, set value in below table: (We have details step by step in example: Basic custom workflow.)

| Name | Type | Description |
| ACTION_PERFORMED | Text | For transition |
| PARTICIPANT_ID | Text | Approver ID |
| PARTICIPANT_NAME | Text | Link to properties file |
| PARTICIPANT_DESCRIPTION | Text | Link to properties file |

Rule 4: workflow at admin task level (Optional)

The default value, workflow can run at event level. If you want workflow run at admin task level, you have to:

*   Select process’s User Data and add TASK_LEVEL = true

### 5.2.2 Workpoint Component

We will introduce basic components of Workpoint Desinger.

Activity Node

An activity represents a step in the business process. There are 3 types of activity depending how activity is complete. The node are shown different.

| Node | Type | Description |
| ![](OEBPS/image_rsrc8V6.jpg) | Automated by a person | It will complete by a person, it is used for approver. |
| ![](OEBPS/image_rsrc8V7.jpg) | Automated by activity | Requires special code to complete activity |
| ![](OEBPS/image_rsrc8V8.jpg) | Automated by server | The WorkPoint Server automatically completes this activity |

If you require approver, choose node type “Automated by a person”.

If you have to do any logic or call any backend, choose node type “Automated by server”. For example, you have logic to call web services, when logic complete, Workpoint will move to next node. You do not to do any special code.

If you choose node type “Automated by activity” to call web service, when logic complete it will not move to next node. The process will stop. You have to do special code to complete activity this node and then Workpoint will move to next node. (The node Approve and Reject has code to complete activity)

The picture below shows 3 types of activities/nodes.

*   Node “App Admin” is Activity: Automated by a person.
*   Node “Call Web Servcies” is Activity: Automated by server.
*   Node “Approve” and “Reject” is Activity: Automated by activity.

| ![](OEBPS/image_rsrc8V9.jpg) |
| Figure 5-18 shows 3 types of activities |

Transition

A transition is a line on the work map that connects to two different nodes. A transition can be unconditional or conditional. A conditional transition associates with a transition selection script.

We use transition as selection path in workflow. The figure below shows the transition with conditions. For example, if division equals central, goes to send ticket and then sending email and finish workflow.

| ![](OEBPS/image_rsrc8VA.jpg) |
| Figure 5-19 shows 3 conditional transitions. |

Delay Node

A delay represents a pause or hold in the business process. For example during provision process, we create user but we have to wait until the hire date, then we will enable that user. If user’s city is New York, we will add role to user at 6 AM.

| ![](OEBPS/image_rsrc8VB.jpg) |
| Figure 5-20 shows example of delay |

Category

Category is group of object. Category can be used to filter lists of alerts, mail, scripts, processes and node templates within the designer. The category help us to import and export workflow.

Parameters

When we write code, Workpoint provides some parameters:

*   ClientContext, For CA IdentityMinder, ClientContext is one required parameter to construct WorkflowContext. WorkflowContext is sub class of ProviderAccessor API.
*   SymbolTable, it used for return value to the WorkPoint Server. We usually use the SymbolTable in Delay node to answer how long to delay.
*   JobData, it contains data at job level. We use JobData to share data between nodes.
*   ActivityInstData, it contains data at node level. We usually use ActivityInstData with Transition.

## 5.3 Code Examples

The example in this chapter will have 2 parts: 

*   Workpoint and code
*   Configuration.

We will use admin task from previous chapter. Please disable Identity Policy Set, policy Xpress and Business Logic Task Handler API from previous chapter that relate to the admin task “Update Location and Ext number”.

| ![](OEBPS/image_rsrc8VC.jpg) |
| Figure 5-21 shows admin task |

We can remove Business Logic Task Handler by

*   Search our admin task name: Update Location and Ext Number
*   Click button “Business Logic Task Handlers”, then click minus icon to remove Business Logic Task Handlers
*   Click ok and submit.

| ![](OEBPS/image_rsrc8VD.jpg) |
| Figure 5-22 shows icon to remove Business Logic Task Handler |

### 5.3.1 Workflow:  One Approver

We will create the basic workflow with one approver and deploy to CA IdentityMinder. This example still does not require any programming.

If you do not want to create workflow, you can import our example workflow, please see Appendix A: import workflow for more detail.

Workpoint and Code

1.  Run Workpoint designer.
2.  Create new process, by click menu on top

| ![](OEBPS/image_rsrc8VE.jpg) |
| Figure 5-23 shows menu “New Process” |

3.  Put the value in the general tab, as below table:

| Field Name | Value | Description |
| Name | Example: One Approver | The Name field identifies the name of the Process Definition |
| Reference | BookEx.OneAppv | The Reference field contains the unique name |

Then click OK. The picture below shows the values in tab general.

| ![](OEBPS/image_rsrc8VF.jpg) |
| Figure 5-24 shows the values in tab general |

4.  Following the rule 1, the flow must start with a “Start” node and end with a “Stop” node. Drag node from menu to canvas.

| ![](OEBPS/image_rsrc8VG.jpg) |
| Figure 5-25 shows node “Start” and “Stop” |

5.  Following the rule 2, the flow must have Approve or Reject state before the Stop node. Drag node “Activity” from menu.

| ![](OEBPS/image_rsrc8VH.jpg) |
| Figure 5-26 shows node “Activity” |

Click one node (Node3 in above picture) and put value following below table:

| Tab | Field Name | Value | Description |
| General | Name | Approve | The Name field contains the name of the activity |
| Resources | Assignment | External | The Resource page identifies resources (human or automated) that can perform the activity.For CA IdentityMinder, select External. See the picture below |
| Agents | Asynchronous | Notify IM Approve | This value is required for CA IdentityMinder. Select script “Notify IM Approve”. See the picture below |

| ![](OEBPS/image_rsrc8VJ.jpg) |
| Figure 5-27 shows resources tab and agents tab with script “Notify IM Approve” |

Then click button OK. The next thing we will do Reject state.(Node 4) It is almost same approve activity, but script’s agent is “Notify IM Reject”.

| Tab | Field Name | Value | Description |
| General | Name | Reject | The Name field contains the name of the activity |
| Resources | Assignment | External | For CA IdentityMinder, select External |
| Agents | Asynchronous | Notify IM Reject | This value is required for CA IdentityMinder. Select script “Notify IM Reject”. See the picture below |

| ![](OEBPS/image_rsrc8VK.jpg) |
| Figure 5-28 shows agents tab and script “Notify IM Reject” |

When we have done this step, our canvas should display as the below figure.

| ![](OEBPS/image_rsrc8VM.jpg) |
| Figure 5-29 shows canvas |

6.  For Approver, drag node Activity to canvas

| ![](OEBPS/image_rsrc8VN.jpg) |
| Figure 5-30 shows activity node |

Rule 3: if we have approver, we have to set some properties. Does the right click on approver node and select properties. Approver node requires configuration as below:

| Tab | Field Name | Value | Description |
| General | Name | Approver | The Name field contains the name of the activity |
| Resources | Assignment | Any | This value is required for CA IdentityMinder. Select resource: IM Approvers. |
| Include | IM Approvers |
| Agents | Agents | Nobody AutoComplete | (Optional) Select “Nobody AutoComplete” to Asynchronous list. |
| User Data | See the table below | It is required properties for CA IdentityMinder |
|  |  |  |  |

| ![](OEBPS/image_rsrc8VP.jpg) |
| Figure 5-31 shows resources tab of approver |

The script “Nobody AutoComplete” in agent tab is optional step. This script will calculate number of approvers. If approver is 0, this script will complete this node and move on to next node.

| ![](OEBPS/image_rsrc8VR.jpg) |
| Figure 5-32 shows optional step, agents tab of approver |

The table shows value of user data tab.

| Name | Type | Value |
| ACTION_PERFORMED | Text | none |
| PARTICIPANT_ID | Text | Approval |
| PARTICIPANT_NAME | Text | imstask.label.singlestepapproval.approvalstep.name |
| PARTICIPANT_DESCRIPTION | Text | imstask.label.singlestepapproval.approvalstep.description |

| ![](OEBPS/image_rsrc8VS.jpg) |
| Figure 5-33 shows user data tab of approver |

The properties: PARTICIPANT_NAME and PARTICIPANT_DESCRIPTION link to properties file: <server>/IdentityMinder.ear/custom/resourceBundle/IMSResources.properties.

| # SingleStepApprovalimstask.label.singlestepapproval.approvalstep.name=Primary Approverimstask.label.singlestepapproval.approvalstep.description=Identity Manager sends the first request to the primary approver.  If found, the primary approver can approve or reject the task or event. |

These properties value will show on screen, when you set approver. You can add new properties and set to approver node.

| ![](OEBPS/image_rsrc8VT.jpg) |
| Figure 5-34 shows properties value on screen |

7.  Transition. Drag transition to connect between nodes

*   From Approve to Stop node , define as Unconditional
*   From Reject to Stop node, define as Unconditional
*   From Start to Approver node, define as Unconditional
*   And drag connection from Approver to Approve node, define type as condition. Select existing script: Approved.

| ![](OEBPS/image_rsrc8VU.jpg) |
| Figure 5-35 shows properties of transition |

*   Drag connection from Approver to Reject node, define type as condition. Select existing script: Rejected. All connections show as the below figure.

| ![](OEBPS/image_rsrc8VV.jpg) |
| Figure 5-36 shows complete workflow |

8.  We want to see this workflow at admin task level. Does the right click on canvas and selects User Data tab.Select type Text, and put name: TASK_LEVEL and value as true and click Add.

| ![](OEBPS/image_rsrc8VW.jpg) |
| Figure 5-37 shows properties of process |

Click save button. ![](OEBPS/image_rsrc8VX.jpg) This workflow will deploy to CA IdentityMinder automatically.

Configuration

There are 2 ways of workflow configuration: admin task level and event level. This example will use workflow at admin task level.

5.  Log into the Identity Manager User Console as administrator.
6.  Select tab Roles and Tasks, and select menu modify admin task.
7.  Search our admin task name: Update Location and Ext Number
8.  Verify box Workflow is checked.
9.  Select icon pencil to add workflow

| ![](OEBPS/image_rsrc8VY.jpg) |
| Figure 5-38 shows enable workflow in admin task |

10.  Select our workflow “Example: One Approver”. If you can’t see workflow, it means you may miss step add attribute workflow properties (TASK_LEVEL=true).
11.  For Approval Task (approver’s screen), select “Approve Admin Task”.
12.  Participant Resolver is who is an approver. Select “List of Users” and select “Add Users”. Choose an approver. You can use your user as approver.
13.  Click OK button and then submit again to complete task modification.

| ![](OEBPS/image_rsrc8VZ.jpg) |
| Figure 5-39 shows workflow configuration in admin task |

How it works

We can execute our workflow as following these steps:

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select Admin Task: “Update Location and Ext Number” from tab “Book Example”, Then search and select some users.
3.  Modify city’s attribute and submit admin task

After submit task, you will see message “Alert:  Task pending”. It means workflow is working in asynchronous phase.

Approval process

1.  After submit, if you login as approver, you will see list approval waiting.

| ![](OEBPS/image_rsrc8W0.jpg) |
| Figure 5-40 shows task is approval waiting |

2.  When you click inside this task, you will see button approve or reject. Click approve button.

| ![](OEBPS/image_rsrc8W1.jpg) |
| Figure 5-41 shows approver task with button: approve and reject |

See workflow job in view submitted task screen

Select “View submitted task” under tab “System”, select our task.

| ![](OEBPS/image_rsrc8W2.jpg) |
| Figure 5-42 shows our task in view submitted task |

Click pencil icon and see details inside. In section Task Workflow Job View, click pencil icon then we will see our workflow.

| ![](OEBPS/image_rsrc8W3.jpg) |
| Figure 5-43 show workflow at admin task level |

See the job in Workpoint designer

There is another way to see job. Run Workpoint designer, and select menu open Jobs. Double click on our workflow.

Work flow jobID

Workpoint will open new tab. It shows all jobs of our process. You can see JobID from view submitted task screen matches with JobID in the Workpoint designer.

| ![](OEBPS/image_rsrc8W4.jpg) |
| Figure 5-44 show workflow Job’s ID |

You can see routing path of workflow by click on job in Workpoint designer or select pencil icon in view submitted task screen.

| ![](OEBPS/image_rsrc8W5.jpg) |
| Figure 5-45 show workflow job |

Our first custom workflow is very easy. There is no programming required. We just start familiar with the Workpoint Designer environment. The next example requires some programming.

### 5.3.2 Workflow: Delay by city

This example shows advance techniques. We do programming in activity, delay and transition. Our requirement is user modify the city attribute. If new value of city equals New York, the process will delay for 10 minutes. If new value of city is some things else, it will not delay. Our flow will show in the picture below:

| ![](OEBPS/image_rsrc8W6.jpg) |
| Figure 5-46 shows our workflow |

Workpoint and Code

1.  Run Workpoint designer.
2.  Create new process, by click on menu File > New > New Process
3.  Put the value as the below table in the general tab. Then click OK.

| Field Name | Value | Description |
| Name | Example : Delay for NY | The Name field identifies the name of the Process Definition |
| Reference | BookEx.DelayNY | The Reference field contains the unique name. |

| ![](OEBPS/image_rsrc8W7.jpg) |
| Figure 5.-47 shows the values in tab general |

4.  Following the rule 1, the flow must start with a “Start” node and end with a “Stop” node. Drag node from menu to canvas.

| ![](OEBPS/image_rsrc8W8.jpg) |
| Figure 5-48 shows node “Start” and “Stop” |

5.  Following the rule 2, the flow must have Approve or Reject state before the Stop node. Drag node “Activity” from menu. Our requirement does not need reject, so we drag only one node. We do configure same as approve node but we put name “Commit”

| Tab | Field Name | Value | Description |
| General | Name | Commit | The Name field contains the name of the activity |
| Resources | Assignment | External | For CA IdentityMinder, select External. |
| Agents | Asynchronous | Notify IM Approve | This value is required for CA IdentityMinder. Select script “Notify IM Approve”. |

TIP: you can copy Approved node from other processes by using CRLT+C and parse to our process.

6.  Drag “Delay” node to canvas

| ![](OEBPS/image_rsrc8W9.jpg) |
| Figure 5-49 shows node “Delay” |

Double click on Activity node (Node 4 in picture above) and add configuration as below:

| Tab | Field Name | Value | Description |
| General | Name | Delay 10 Minutes | The Name field contains the name of the activity |

In tab Evaluation Date, Script Calculated Delay. Click icon new to create new script.

![](OEBPS/image_rsrc8WA.jpg)

|  |
| Figure 5-50 shows icon create new script |

In general tab, put name as “Delay 10 Minutes” and select tab Statement.

| Tab | Field Name | Value |
| General | Name | Delay 10 Minutes |
| Statements | Statement Type | Java |
| Java Class | com.book.idm.workflow. DelayForNYFlow |
| Method | delay10Minutes |
| Parameters | SymbolTable |

| ![](OEBPS/image_rsrc8WB.jpg) |
| Figure 5-51 shows the script screen. |

We need parameter SymbolTable because our java code set the result delay time to object SymbolTable.

7.  Drag “Server Automated” to canvas. We will write some business logics.

| ![](OEBPS/image_rsrc8WC.jpg) |
| Figure 5-52 shows node server automated |

Double click on node (Node 5 in picture) and add configuration as below:

| Tab | Field Name | Value | Description |
| General | Name | Check City Value | The Name field contains the name. |
| Resources | Assignment | External | This work assignment option allows an external application to insert resource assignments into the WorkPoint database. |

Select agents tab, click on new button to add new script.

| Tab | Field Name | Value |
| General | Name | IsNewYorkCity |
| Statements | Statement Type | Java |
| Java Class | com.book.idm.workflow. DelayForNYFlow |
| Method | checkCityValue |
| Parameters | ClientContext, ThisJobData, ThisActivityInstData |

Then click ok to finish new script.

| ![](OEBPS/image_rsrc8WD.jpg) |
| Figure 5.53 shows new script screen |

Click user data tab, we will add value for transition. User Data allows custom application data to be saved in the form of name/value data pairs.  In our requirement we want to keep city value in user data.

| Name | Type | Value |
| city | Text | none |

For initial value, we put value as none. We will go details later in programming part.

| ![](OEBPS/image_rsrc8WE.jpg) |
| Figure 5-54 shows user data |

Click “add” button and then click ok to finish.

8.  Drag transition and define type as unconditional between nodes:

*   From “Start” to “Is New York City” node
*   From “Delay 10 Minutes” to Commit node
*   From “Commit” to “Stop” node

| ![](OEBPS/image_rsrc8WF.jpg) |
| Figure 5-55 shows transition between nodes |

9.  We will define the conditional transition when city equals New York.

*   Drag transition from “Is New York City” to “Delay 10 Minutes” node
*   Select type: Conditional
*   Select create new script
*   Put name: City == New York
*   Click next button

| ![](OEBPS/image_rsrc8WG.jpg) |
| Figure 5-56 shows conditional transition screen |

*   Click the first column: left operand, select “SourceActivity.UD.city”
*   The second column: comparison, select “String =”
*   The third column: right operand, put value “new york”
*   Click finish to finish step.

| ![](OEBPS/image_rsrc8WH.jpg) |
| Figure 5-57 shows statement of conditional transition screen |

This step, we create condition.  If  “SourceActivity.UD.city == new York”, let goes this path.

10.  We have to define another condition transition when city does not equal New York.

*   Drag transition from “Is New York City” to “Commit” node
*   Select type: Conditional
*   Select create new script
*   Click next button

*   Put name: City != New York
*   Click the first column: left operand, select “SourceActivity.UD.city”
*   The second column: comparison, select “String !=”
*   The third column: right operand, put value “new york”
*   Click finish to finish step.

| ![](OEBPS/image_rsrc8WJ.jpg) |
| Figure 5-58 shows statement of conditional transition screen |

11.  Click save icon, the whole workflow should be as the picture below.

| ![](OEBPS/image_rsrc8WK.jpg) |
| Figure 5-59 shows complete workflow |

12.  Copy java class to folder “custom”. (same folder as Business Logic Task Handler Code)

*   com.book.idm.workflow.DelayForNYFlow
*   com.book.idm.workflow.WorkpointHelper

We will go detail of java code later.

Configuration

This example we will specific our workflow at event level.

1.  Search our admin task name: Update Location and Ext Number
2.  Make sure check box Enable Workflow selected and remove workflow from previous example void confusion.

| ![](OEBPS/image_rsrc8WM.jpg) |
| Figure 5-60 shows enable workflow checked box and remove previous workflow |

3.  Select events tab and select icon pencil at event ModifyUserEvent
4.  Select our workflow “Example: Delay for NY”.
5.  Click OK button and then submit again to complete task modification.

| ![](OEBPS/image_rsrc8WN.jpg) |
| Figure 5-61 shows workflow in ModifyUserEvent. |

How it works

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example and select Admin Task: “Update Location and Ext Number”, Then search and select some users.
3.  Modify city’s attribute and submit admin task.

View submitted task

Select “View submitted task” under tab “System”, select our task. Click icon pencil to see detail inside.

| ![](OEBPS/image_rsrc8WP.jpg) |
| Figure 5-62 show our task |

Scroll down until you see event name: Modify user. Click icon “pencil” to see workflow detail.

| ![](OEBPS/image_rsrc8WR.jpg) |
| Figure 5-63 shows ModifyUserEvent |

.Look at section “Event Workflow Job View” and select pencil icon to see workflow. If you change city attribute to be New York, you will see the flow stop and node delay for 10 minutes. Waiting until 10 minutes, it will complete workflow.

| ![](OEBPS/image_rsrc8WS.jpg) |
| Figure 5-64 shows job, when user update city to be New York |

If you change the city attribute to be something else, it will go node commit directly without waiting 10 minutes.

Node: Check City Value

This node, we have these configurations:

-          In user data tab, we set name and value: city=none.

-          In agents tab, we select script “IsNewYorkCity”

*   Java Class Name: com.book.idm.workflow.DelayForNYFlow
*   Method name: isNewYorkCity
*   Parameters: ClientContext,SymbolTable,ThisJobData,ThisActivityInstData

| ![](OEBPS/image_rsrc8WT.jpg) |
| Figure 5-65 shows configuration of automated node |

In method checkCityValue, the arguments must have exactly match with script’s parameters both sequence order and values. (ClientContext clientContext, JobData thisJobData,ActivityInstData thisactivityInstData)

*   ClientContext – it needs to construct WorkflowContext
*   JobData – it needs to construct WorkflowContext.
*   ActivityInstData – it used to access value “city” in user data tab.

| public void checkCityValue(ClientContext clientContext, JobData thisJobData,ActivityInstData thisactivityInstData){User user = null;WorkflowContext workflowContext = null;try{//Get ContextworkflowContext = WorkpointHelper.getWorkflowContext(clientContext,thisJobData);user = WorkpointHelper.getUser(workflowContext);System.out.println("City : New Value ="+user.getAttribute("l"));System.out.println("City : Old Value ="+user.getLastCommittedAttribute("l"));//Put new value to User DatathisactivityInstData.setUserData("city",user.getAttribute("l").toLowerCase());}catch(Exception e){e.printStackTrace();}} |

We have to get WorkflowContext. WorkflowContext is the main API to interact with CA IdentityMinder.

| workflowContext = WorkpointHelper.getWorkflowContext(clientContext,thisJobData); |

CAIdentityMinder provides class WorkflowCallbackHelper. generateWorkflowContext() to get the workflow context. We create utility class: WorkpointHelper andmethod generateWorkflowContext. You can reuse this class in your project.

| public static WorkflowContext getWorkflowContext(ClientContext clientContext,JobData thisJobData) throws WorkPointEJBException,Exception{TableID jobTableId = thisJobData.getJobID();Job job = Job.queryByID(clientContext, jobTableId, true);//Get the idJobUserDataTable imsIdUD = job.getUserData("ims-id");String imsId = (String)imsIdUD.getVariableValue();String envOid = (String)job.getUserData("ime-id").getVariableValue();WorkflowContext workflowContext = (new WorkflowCallbackHelper()).generateWorkflowContext(imsId,envOid);return workflowContext;} |

WorkflowCallbackHelper. generateWorkflowContext require 2 parameters: ims-id and ime-id. These ids will be generated when job create. You can search the job (instance of process) and do the right click on canvas and see the user data tab of job. Our code get current job by method queryByID(), then get ims-id and ime-id by method getUserData().

By the way, The code gets WorkflowContext is pattern, you justcopy and reuse.

| ![](OEBPS/image_rsrc8WU.jpg) |
| Figure 5-66 shows ims-id and ime-id in user data tab of job. |

The next line shows getting User object from workflow context. We create the utility method getUser() that return user object.

| user = WorkpointHelper.getUser(workflowContext); |

We use method getSubject() returns the primary object of admin task. Our admin task has User as primary object. If you try to call this method in admin task that primary object is not user, you will get error.

| public static User getUser(WorkflowContext workflowContext) throws Exception{ManagedObject managedObject = workflowContext.getSubject();if(managedObject instanceof User){return (User)managedObject;}else{throw new IllegalArgumentException("Managed Object is not User");}} |

WorkflowContext extends IMContext, IMPersistentContext, ProviderAccessor, ServiceProvider, TaskInfo. Please see official java document for more details. It is almost same as BLTHContext but there is one difference is WorkflowContext extends EventContext.

Please note workflow has 2 levels: admin task level and event level. If your workflow run at admin task level and you try to call any methods from parent class EventContext, you will get unexpected results.

We have another method getUser(EventContext context). You have to make sure your workflow runs at user event. The code below shows how to get user object from event.

| IMEvent evt= workflowContext.getEvent();       User user = ((UserEvent)evt).getUser(); |

The our method getUser()in WorkpointHelper.java can be reuse in your project. We have additional note for workflow programming.

Note 1: WorkflowContext, calling method from the parent class (EventContext) properly.

*   If work flow run at admin task level, does not call methods from parent: EventContext. 
*   Make sure you do the right casting. For example

    *   Workflow attached with event ModifyUserEvent, you can cast object by UserEvent  (ModifyUserEvent is sub class of UserEvent)

| User user = ((UserEvent)evt).getUser(); |

*   Workflow attached to event: AddToGroupEvent, you can cast by GroupEvent (AddToGroupEvent is sub lcass of GroupEvent)

| Group group = ((GroupEvent)evt).getGroup(); |

It is same as BLTHContext, when you use method getSubject(), please check what the primary object of admin task.

The next line of our code, we print value. It is demonstrate how to access new value and old value.

| System.out.println("City : New Value ="+user.getAttribute("l"));System.out.println("City : Old Value ="+user.getLastCommittedAttribute("l")); |

The next line of code shows how to set value in user data tab. In user data tab, we add key/value pairs  (city=none). This code will modify value to be new user’s city attribute.

| //Put new value to User DatathisactivityInstData.setUserData("city",user.getAttribute("l").toLowerCase()); |

Transition uses city in User Data to determine path. If there are exception occurs (default value is “none”), it will go to path “City != New York”. So you should aware exception inside workflow.

| ![](OEBPS/image_rsrc8WV.jpg) |
| Figure 5-67 shows relationship of user data and transition |

Transition

Transition is connection between nodes. You can edit condition in transition by clicking pencil icon in condition tab.

| ![](OEBPS/image_rsrc8WW.jpg) |
| Figure 5-68 shows icon pencils for editing condition |

In our example, we use condition wizard. In condition tab, there are many ways to create condition. You can do programming also (but not recommend)

You cannot edit condition after submit but you can change statement type or delete this script and create new one. (Some cases, you cannot delete because there are some references, I suggest to change name if you don’t want to delete references)

| ![](OEBPS/image_rsrc8WX.jpg) |
| Figure 5-69 shows listing of statement type in transition |

Transition’s condition with java code

You can use java code in transition; you need to set final result TRUE or FALSE into Symbol table. Transition will reference value of “Result1” in SymbolTable to determine path. For example, Transition “City == New York”, we can write as code below:

| boolean result = false;if(city.equalsIgnoreCase("new york")){result = true;}symbolTable.add("Result1").setValue(0,result); |

For more details about SymbolTable class, please see Workpoint help document.

We have to get city value from User Data of node “Check City Value”. The transition is connection between “source node” and “destination node”.

| ![](OEBPS/image_rsrc8WY.jpg) |
| Figure 5-70 shows source and destination of transition |

There are 2 ways to access city value from user data tab of source node.

The first way: passing parameters. You have to put SourceActivity.UD.city in parameter text field. SourceActivity means source node, UD means User Data and you have to put name “city”

| ![](OEBPS/image_rsrc8WZ.jpg) |
| Figure 5-71 shows SourceActivity.UD.city in parameters |

For programming, you just declare String as parameter

| public void isCityEqualNewYork(String city,SymbolTable symbolTable,JobData thisJobData,JobTranData jobTransData){                                         System.out.println("Get city UD by passing SourceActivity.UD.city :"+city);} |

The second way, look up by source node id. This way you need 2 paramters: JobData and JobTranData.

| ![](OEBPS/image_rsrc8X0.jpg) |
| Figure 5-72 shows JobData and JobTranData in parameters |

ThisJobData means instance of process. ThisJobTransitionData means instance of this transition. The code below shows how to access user data from source node.

| TableID sourceJobNodeID = jobTransData.getSourceJobNodeID();ActivityInstData sourceActivity = thisJobData.getActivityByNodeID(sourceJobNodeID);String cityUD = sourceActivity.getUserData("city").getVariableValue();System.out.println("Get city by sourceJobNodeID :"+cityUD); |

We use jobTransData to get source ID, and then we use job look up source node by sourceID. When we get source node, we can get User Data

Note 2: Keep transition’s condition simple

My suggesting is please keep transition condition simple. You should use condition wizard. Avoid any complicated logic in transition. For example, we have 2 transitions: “City == New York” and “City != New York”. If you do programming to calculate inside transition “City == New York”, you have to do programming in another transition also. It means you do twice.

The suggestion, please do logic or calculation in source node and keep the plain result in user data. The transition just use only result to determine paths. It is easier to maintenance logic. 

Delay

The concept of delay is straightforward: you want this node hold until when. You just put the value date time in format “yyyy-MM-dd HH:mm:ss” in result1 of SymbolTable.

| public void delay10Minutes(SymbolTable symbolTable){Date current = new Date();Calendar calendar = Calendar.getInstance();calendar.setTime(current);calendar.set(Calendar.MINUTE, calendar.get(Calendar.MINUTE)+10);//yyyy-MM-dd HH:mm:ssSimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");String executeTime = simpleDateFormat.format(calendar.getTime());SymbolData r1 = symbolTable.add("Result1");r1.addValue(executeTime);} |

Delay node support delay time by configuration in evaluation date tab. Please see Workpoint document for more details.

Node Commit

We have the rule; we must do approve or reject before finish the workflow. In this example we require only one path. So we just want only approve status but we use name as “Commit”.

Error workflow

Sometimes, you do programming on workflow and you got some errors. You should cancel your task or event. We should not leave unfinished flow in system. You can cancel in View Submitted task.

| ![](OEBPS/image_rsrc8X1.jpg) |
| Figure 5-73 shows buttons cancel event in view submitted task screen |

### 5.3.3 Category

Category is group of object. We can use Category to filter object. It is very useful to manage our workflow. This example, you will learn:

*   How to create category and add object to category.
*   Using library and searching object
*   Export workflow.

Create Category

1.  Click on menu Library > Category.

| ![](OEBPS/image_rsrc8X2.jpg) |
| Figure 5-74 shows menu category in library menu |

2.  Click new button and put name “BookExample”

| ![](OEBPS/image_rsrc8X3.jpg) |
| Figure 5-75 shows new button. |

Add objects to category

Select our process and script and add category.

*   Process

*   Does the right click on canvas
*   Select properties and select tab: category
*   Select “BookExample” and click add button
*   Node (Activity, Automated, Server Automated, Delay, Transition) , you do not need to do, it will follow process’s category.

*   Script inside Node or transition

*   Edit script
*   Select tab category
*   Select “BookExample” and click add button

| ![](OEBPS/image_rsrc8X4.jpg) |
| Figure 5-76 shows category of script |

Filter by category

After we add category, we can do filter in condition of transition or agents of node.

| ![](OEBPS/image_rsrc8X5.jpg) |
| Figure 5-77 shows category button for filter |

Export workflow

We can export workflow and import to UAT or production.

*   Select menu File > Export
*   Put file name, and click next
*   You can use category to filter.
*   We usually export object we did: Category, Process and Script

| ![](OEBPS/image_rsrc8X6.jpg) |
| Figure 5-78 shows menu export and export screen filter by category |

Please see appendix A, we have detail about import workflow.

## 5.4 WorkPoint Programming

Now you learned some Workpoint examples. This section has additional concepts after you learn some example code.

### 5.4.1 Activity, Server Automated and Automated

There are 3 type of node: Activity![](OEBPS/image_rsrc8X7.jpg), Server Automated ![](OEBPS/image_rsrc8V8.jpg) and Automated![](OEBPS/image_rsrc8V7.jpg) . We have 3 types of activity, automated and server automated. There are checked boxes in general tab. The picture below shows relationship between checkbox and node type .

| ![](OEBPS/image_rsrc8X8.jpg) |
| Figure 5-79 below shows relationship between checkbox and node type |

### 5.4.2 Script for Server Automated and Automated

Script for Server Automated ![](OEBPS/image_rsrc8V8.jpg) and Automated![](OEBPS/image_rsrc8V7.jpg) are different. If you use node Automate implement business logic, you have to do additional code to complete activity by code. The picture below shows we use Automate node “Check City Value” and flow does not move on after logic completed.

| ![](OEBPS/image_rsrc8X9.jpg) |
| Figures 5-80 shows the flow stops at automated node and not move on. |

We can fix the picture above by adding code to complete activity.

| public void completeActivity(ClientContext cc,ActivityInstData ad,SymbolTable st) throws Exception{short workitem = Short.parseShort((String)st.getSymbol("WorkItemIteration").getPrimaryValue());WorkItemEntry workItemEntry = WorkItemEntry.queryByID(cc, ad.getActivityInstID(),workitem);short currentState = workItemEntry.getWorkStateID();if (currentState == WorkItemConst.WORK_STATE_AVAILABLE) {workItemEntry.changeState(WorkItemConst.WORK_STATE_OPEN);}workItemEntry.changeState(WorkItemConst.WORK_STATE_COMPLETE);} |

Note 3: Using server automated implement business logic. (Recommendation)

This topic, we suggest to use the server automated. You don’t need to worry to complete activity.             

### 5.4.3 Agent scripts can be designated Synchronous or Asynchronous.

Let understand what is Synchronous or Asynchronous in Workflow:

*   Synchronous Scripts means resource’s scripts, synchronous agent’s scripts, and state rules.
*   Asynchronous Scripts mean asynchronous agent’s scripts, mail’s scripts, and alert’s scripts.

Agent scripts are typically used to make changes to the database or invoke an action.  Agent script can be Synchronous or Asynchronous.

| ![](OEBPS/image_rsrc8XA.jpg) |
| Figure 5-81 shows agent script screen |

Synchronous agent scripts are executed in the same transaction as the state change. Asynchronous agent scripts are executed outside of the state change transaction and therefore are completed independently. So there are the things need to know:

*   If you use script modify node’s User Data, script must execute in synchronous.
*   If you want to complete activity, script must execute in asynchronous.

Note 4: agent script of server automated should designate as synchronous.

When you do the business logic in work flow, please designate your script in synchronous.

### 5.4.4 Saving Job Objects

In official document: programming guide for java, there is topic “Saving Job Objects” in Workflow API.

What is saving job object?

Job is instance of process. Saving job object means you want to keep some value for sharing between nodes inside this workflow.  For example

*   You have node 1 connect to node 2, and node 2 connect to node 3.
*   Node 1 modify value X =1
*   Node 3 can see value X

So we have to declare variable X in user data at process/job level.  Does the right click on canvas, select tab user data and put the value X as name. It is same step as when you specific TASK_LEVEL for workflow.

| ![](OEBPS/image_rsrc8XB.jpg) |
| Figure 5-82 shows user data tab in process properties |

The official document tell develop aware cache when they save Job’s User Data in asynchronous. It requires special code.

Saving job data in Synchronous scripts

All synchronous scripts must use the ThisJobData or ThisActivityInstData  to fetch User Data.

| ![](OEBPS/image_rsrc8XC.jpg) |
| Figure 5-83 Synchronous scripts access job object from parameters |

Saving job data in Asynchronous scripts

For read only, you can use ThisJobData or ThisActityInstData objects. When you want to save job in Asynchronous scripts you must write code as:

| var jobTableId = ThisJobData.getJobID();var job = Job.queryByID(ClientContext,jobTableId,true);job.setUserData("Test","Pass");job.save(); |

### 5.4.5 Search reference

Sometimes, you cannot delete some object because there are some references. For example, you want to delete script, but you get error because of references. You want to know which process or jobs use this script. Click menu library > scripts, and does right click on script, and select search references or search dialog. The search dialog gives more option, if you want to search jobs, please check option on jobs check box in search dialog.

| ![](OEBPS/image_rsrc8XD.jpg) |
| Figure 5-84 shows search references |

Note 5: Delete related jobs before delete process.

If you deleted process before job, you will get complicated when you want to delete script. You select script and search references; you will see some jobs refer to scripts. You can’t access all relate jobs because you already deleted process. You have to open job one by one and delete each job.

So we suggest delete all related jobs before delete process.

## 5.5 Use cases examples

In the official CA IdentityMinder document talked about use case examples. Please see Programming Guides › Programming Guide for Java › Workflow API › Workflow API Overview › Use Case Examples for full details

*   Determine workflow direction based on a User object attribute

| The first activity in a workflow process for a CreateUserEvent is an automated activity with three conditional transitions leading from it. The condition script in each transition retrieves the email attribute from the User object contained in the event.The next activity that the workflow process performs is determined by the outcome of the condition scripts, as follows: 
*   The transition CA.COM SUFFIX, goes to one approver: HR Manager.

*   The transition SECURITY.COM SUFFIX, goes to 2 approvers: HR Manager and IT Manager.

*   The transition EMAIL INVALID, reject workflow

 |

The document said using condition script in each transition retrieves the email. You can write the transition’s condition with java code.

| ![](OEBPS/image_rsrc8XE.jpg) |
| Figure 5-85 shows workflow of use case |

*   Update a CA IdentityMinder object during a workflow process

| In the previous use case example, suppose the condition script for the transition CA.COM SUFFIX is updated to check whether the email attribute is blank. If it is blank, the script constructs an email address from the user’s ID and the default suffix ca.com. The script assigns the address to the email attribute of the User object. The script then returns true, and the transition is performed as in the previous example. The updated object is saved when CA IdentityMinder completes the execution of the event. |

There are 2 interesting things:

*   The condition script for the transition CA.COM SUFFIX is updated to check whether the email attribute is blank.

    *   You can do the logic inside condition script of transition “CA.COM SUFFIX”
*   . The script assigns the address to the email attribute of the User object.

    *   We can assign the address to email attribute by ProviderAccessor and Workflow Context. For this case, we have to use Workflow context because of 2 reasons. The first one is CreateUserEvent. I means user not created until event has been done. The second reason, this workflow requires approver. If it rejected, we have to concern outcome.

We plan to modify email attribute in workflow context, you have to make sure you define email attribute in fields tab when you create admin task.

*   Validate an object from a workflow process using third-party data

| The workflow process for a CreateUserEvent contains an automated activity that retrieves the new user’s credit score from a third-party database. First, the activity script calls the Workflow API to retrieve the event and the User object within the event. Then, after the script retrieves the user’s credit score, it uses the workflow engine’s API to write the credit score to the User Data for the activity, and finally completes the activity. Transition scripts leading from the activity then use the workflow engine’s API to retrieve the credit score from the User Data and evaluate it to determine the subsequent course of the workflow process. |

We can use script in server automated to call third party data. For example, you call the third party to get type and determine path.

| ![](OEBPS/image_rsrc8XF.jpg) |
| Figure 5-86 shows workflow calls the third party data |

## 5.6 Conclusion

This chapter, you learned workflow context API or how to create custom workflow. We can conclude concept of workflow as:

The check list before create work flow:

*   What is level of workflow? admin task level or event level
*   Which workflow? Choose from 3 default workflow or create new custom workflow?
*   Do we need policy (or condition) before workflow starts?
*   What screen (task) for approver?
*   Who is approver?
*   What is outcome?

Rule of custom work flow

*   Rule 1: Must start with a “Start” node and end with a “Stop” node
*   Rule 2: Must have Approve or Reject before go to Stop node
*   Rule 3: Approver Configuration (If you require approver)
*   Rule 4: workflow at admin task level (Optional)

Note for custom workflow

*   Note 1: WorkflowContext, calling method from the parent class (EventContext) properly.
*   Note 2: Keep transition’s condition simple
*   Note 3:  Using server automated implement business logic. (Recommendation)
*   Note 4: Agent script of server automated should designate as synchronous.
*   Note 5: Delete related jobs before delete process.

You may think workflow API is difficult, my suggesting you just remember rules and notes in this chapter. For programming detail, please see book volume II contains a lot of examples. You will familiar it. The business logic task handler and workflow is useful in real project. The next chapter, we will go the rest of APIs.

# Chapter 6: Additional APIs

We learned 2 main API to develop business logics; business logic task handler under synchronous phase and workflow under asynchronous phase. These APIs in this chapter is helpers to achieve the goals.

There are a lot of details in this chapter. You may not need to pay attention to all APIs. My opinion, I give summary the table below:

| API Name | Frequency | Purpose |
| Participant Resolver API | sometimes | Determines who is approver |
| Event Listener API | often | Performs custom business logic when event occurs |
| Logical Attribute API | rarely | Convert between physical and logical attributes |
| Validation Rules | sometimes | Validate values |
| Email & Notification Rule API | sometimes | Sending email |
| Task Execution Web Service | sometimes | Enable admin task as web services producer |

## 6.1 Participant Resolver API

The Participant Resolver API is a part of workflow. The Participant Resolver API determines the participants in a workflow activity. A participant is a person who is authorized to approve in workflow.

If workflow requires approver (for example SingleStepApproval), you need to select the participant resolver in configuration screen.

| ![](OEBPS/image_rsrc8XG.jpg) |
| Figure 6-1 shows the participant resolver screen |

CA IdentityMinder provides configurable condition for participant resolver, see official document topic “Types of Participant Resolvers” for more details. We need the participant resolver API, when configurable condition is not support.

### 6.1.1 Programming

Using the ParticipantResolver API, you must create class extend ParticipantResolverAdapter and override method resolver(); The return value is a vector of user objects containing the list of participants.

| public Vector resolve(ParticipantResolverContext ctx, Hashtable data, String approvalNodeName) |

There are 3 parameters passed from workflow. The first one is context same as BLTHContext or WorkflowContext. The second parameter HashTable has key value TASK_TAG contain admin task name. The last parameter string contain node name in workflow.

### 6.1.2 Code Example: Participant Resolver API

This example uses the workflow; SingleStepApproval. The SingleStepApproval workflow has 2 approvers; the primary approver and default approver. The primary approver calls our ParticipantResolver code. For default approver, we use our administrator.

Our requirement want the primary approver is manager or manager is approver. If user does not have manager of manager, use manager. If user does not have manager, skip to default approver.

Code

3.  Compile our java code: com.book.idm.etc.MgrOfMgrParticipantResolver
4.  Copy class (include package folder ” com.book.idm.etc” ) to folder “<server>\IdentityMinder.ear\custom”

Configuration: Management Console

1.  In the Management Console, click Environments.
2.  Click the name of the environment.
3.  Click Advanced Settings.
4.  Click Workflow Participant Resolvers.
5.  Click new button and put value as the below table

| Field Name | Value | Description |
| Name | MgrOfMgrParticipantResolver | Name of Participant Resolver |
| Class | com.book.idm.etc.MgrOfMgrParticipantResolver | Name of our java class |

Configuration: Identity Manager User Console

1.  Log into the Identity Manager User Console as administrator.
2.  Search our admin task name: Update Location and Ext Number.

*   Please disable business logic task handler, policy Xpress or workflow from previous example.

3.  Select tab event and click ModifyUserEvent.

4.  Select Non-Policy Based workflow: singleStepApproval

*   For Primary Approver:

*   Approval Task drop down, select Approve Modify User
*   Participant Resolver drop down, select Custom: MgrOfMgrParticipantResolver

*   For Default Approver:

*   Approval task drop down, select Approve Modify User
*   Participant Resolver drop down, select your administrator.

| ![](OEBPS/image_rsrc8XH.jpg) |
| Figure 6-2 shows workflow configuration |

How it works

You have to prepare 3 users:  user A, user B and user C. Login to user data store and check attribute managerID:

*   User A has managerID = user B
*   User B has managerID = user C.
*   User C has managerID = “”

Log into the Identity Manager User Console as administrator, Select tab: Book Example

Case 1: Modify user A, participant is Manager of Manager

4.  Select Admin Task: “Update Location and Ext Number”, then search and select user A. Modify city’s attribute and submit admin task.
5.  Login as user C, you should see request for approval

Case 2: Modify user B, Participant is Manager

1.  Select Admin Task: “Update Location and Ext Number” again and select user B. Modify city’s attribute and submit admin task.
2.  Login as user C, you should see request for approval

Case 3: Modify user C, There is no manager

1.  Select Admin Task: “Update Location and Ext Number” again and select user C. Modify city’s attribute and submit admin task.
2.  Login as administrator, you should see request for approval

Find manager of manager

We use ProviderAccess find the manager. We get user then we look up attribute managerID, and search manager by managerID and so on until we get manager of manager.

| String userId = ctx.getSubject().getFriendlyName();User user = ctx.getUserProvider().findUser(userId, null);String managerID = user.getAttribute("managerID");User managerUser = ctx.getUserProvider().findUser(managerID, null);String mgrOfMgrID = managerUser.getAttribute("managerID");User mgrOfMgrUser = ctx.getUserProvider().findUser(mgrOfMgrID, null);resolver.add(mgrOfMgrUser); |

Add participants

The code is pretty straightforward. We create vector object and add object User who is participant to object.

| Vector resolver = new Vector();resolver.add(mgrOfMgrUser); |

No manager of manager

If user does not have manager of manager, we will return manager

| if(mgrOfMgrID == null&#124;&#124;mgrOfMgrID.trim().length()==0){System.out.println(userId+" has only manager "+managerID);resolvers.add(managerUser);return resolvers;} |

If there are no approver, just return empty vector.

### 6.1.3 Use Case Example

In official document (Programming Guide for Java > Workflow API > Participant Resolver API > Participant Resolver Overview > Use Case Example) give one use case example.

Assign a group’s administrators as participants

| Workflow approval is required whenever a user is added to the group HR. A custom participant resolver assigns the administrators of the group as participants in the workflow activity. When a user is added to HR, the event AddToGroupEvent comes under workflow control, and cannot be completed successfully until a designated participant approves the activity. |

This workflow runs specific event level AddToGroupEvent. We can write the condition, if group’s name equals “HR”, return approver. If group’s name does not equal “HR”, return empty vector.

| public Vector resolve(ParticipantResolverContext ctx, Hashtable userData, String approvalNodeName) throws Exception {Vector resolver = new Vector();AddToGroupEvent event = (AddToGroupEvent)ctx.getEvent();String groupName = event.getGroup().getFriendlyName();if(groupName.equals("HR")){resolver = event.getGroup().getAdmins(null);}return resolver;} |

We get group from event. We can get administrator of this group by method getAdmins(). Please see java doc for more details.

## 6.2 Event Listener API

When CA IdentityMinder executes an admin task, it breaks down the task into its component events. Each event represents a specific action to be performed during the execution of the task, for example a CreateUserEvent is adding the new user.

An event listener listens to a specific event or a group of events. When the event occurs, the event listener performs custom business logic that is appropriate for the event and the current event state.

### 6.2.1 Programming

For Event Listener API, you must create java class extend EventListenerAdapter and override methods as needs.

*   int  before(EventContext evtCtx)

    *   Performs custom business logic during the Pre-approval state.
*   int  approved(EventContext evtCtx)

    *   Performs custom business logic during the Approved state.
*   int  rejected(EventContext evtCtx)

    *   Performs custom business logic during the Rejected state.
*   int  after(EventContext evtCtx)

    *   Performs custom business logic during the Post-execution state.
*   int  failed(EventContext evtCtx)

    *   Performs custom business logic after execution failure state.

Every method return constant of EventListenerAdapter; BREAK or CONTINUE. One event can has many listeners. If return BREAK means no more event listeners are processed for the current event state. If return CONTINUE means processing for this event listener is complete. CA IdentityMinder processes the next event listener in the same event state. My suggestion, we should always return CONTINUE, it will not break other listeners in future.

### 6.2.2 Code Example: Event Listener API

Our example shows life cycle of listener. It use standard out printing message.

Code

1.  Compile our java code: com.book.idm.etc.LifeCycleEventListener
2.  Copy class (include package folder ” com.book.idm.etc” ) to folder “\IdentityMinder.ear\custom”

Configuration

1.  In the Management Console, click Environments.
2.  Click the name of the environment where the event listener will be used.

5.  Click Advanced Settings.
6.  Click Event Listeners.
7.  Click new button and put value as the below table

| Field Name | Value | Description |
| Name | LifeCycleEventListener | Name of event listener |
| Class | com.book.idm.etc.LifeCycleEventListener | Name of our java class |
| Listener Level | ModifyUserEvent | Event that class is listening to |

| ![](OEBPS/image_rsrc8XJ.jpg) |
| Figure 6-3 shows event listener configuration |

8.  Click Restart Environment.

Configuration: Identity Manager User Console

1.  Log into the Identity Manager User Console as administrator.
2.  Search our admin task name: Update Location and Ext Number.

*   Please disable business logic task handler, policy Xpress or workflow from previous example.

3.  We require one workflow for testing our event listener in case of reject or approve. Select tab event and click ModifyUserEvent.

*   Select Non-Policy Based: singleStepApproval.
*   For primary approver and default approver

*   Approval Task drop down, select Approve Modify User
*   Participant Resolver drop down, select your administrator.

How it works

Execute admin task: Update Location and Ext Number.

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example, and select menu Update Location and Ext Number.
3.  Select Admin Task: “Update Location and Ext Number” from tab “Book Example”, Then search some users. Modify city’s attribute and submit admin task. You can see message in log file. The message does not appear immediately, you have to wait until event start.

| 2013-10-27  INFO  [STDOUT] =============>LifeCycleEventListener:before |

4.  Log in as approver, you will see approve task and click approve. Look at message in log file.

| 2013-10-27  INFO  [STDOUT] =============>LifeCycleEventListener:approved2013-10-27  INFO  [STDOUT] =============>LifeCycleEventListener:after |

Listener Level

We set listener level equal to ModifyUserEvent. It means our program listen to only one event type: ModifyUserEvent. If we change listener level as User, it means it listens to all events that relate to user.

| ![](OEBPS/image_rsrc8XK.jpg) |
| Figure 6-4 shows event listener level configuration |

If you select *, it means this listener will listen every events.

### 6.2.3 Code Example: Event Generating

Event generating is not feature of Listener, but it is feature of context. Our example will show how to event generate new event; Add user to group.  This example code requires group named “IT”. If you do not have, you can create new group or modify code to change group name.

We can generate new event by EventContext. An EventContext can generate a secondary event within the current task. The EventContext has method generateEvent()

| void generateEvent(java.lang.String className,java.lang.Object primary,java.lang.Object secondary,java.lang.String workflowID)throws java.lang.Exception |

The first parameter className is the fully qualified name of the class to be instantiated for the event being generated. Event classes are in the package com.netegrity.ims.events. You can see details in java doc, but I suggest to see in management console > Environments > Advance Settings > Event List. It is up to date.

| ![](OEBPS/image_rsrc8XM.jpg) |
| Figure 6-5 shows Event List |

The second and third parameters are primary and secondary object type, you can see the picture above. The last parameter is workflowID. The name of the workflow process (such as SingleStepApproval) map to the event being generated. If you do not require any workflow, you just pass null.

This example shows if city attribute == “new york”, then we will add user to group “IT”.

Code

1.  Compile our java code: com.book.idm.etc.NewYorkCityEventListener
2.  Copy class (include package folder ”com.book.idm.etc” ) to folder “\IdentityMinder.ear\custom”

Configuration

1.  In the Management Console, click Environments.
2.  Click the name of the environment where the event listener will be used.
3.  Click Advanced Settings.
4.  Click Event Listeners.
5.  Click new button and put value as the below table

| Field Name | Value | Description |
| Name | NewYorkCityEventListener | Name of event listener |
| Class | com.book.idm.etc.NewYorkCityEventListener | Name of java class |
| Listener Level | ModifyUserEvent | Event that class is listening to |

6.  Click Restart Environment.

Configuration: Identity Manager User Console

1.  Log into the Identity Manager User Console as administrator.
2.  Check our admin task name: Update Location and Ext Number:

*   Remove all business logic task handlers and policy Xpress.
*   Remove workflow from previous example.

How it works

Execute admin task: Update Location and Ext Number.

1.  Log into the Identity Manager User Console as administrator.
2.  Select Admin Task: “Update Location and Ext Number” from tab “Book Example”, Then search some users. Change city’s attribute to be “New York” and submit admin task.
3.  Go to view submitted task, and select details. You will see event “Add user to group”.

| ![](OEBPS/image_rsrc8XN.jpg) |
| Figure 6-6 shows generated event "Add user to group" |

You can search group “IT” and see the membership for checking the result.

Specific admin task

We specific an event by configuration and admin task by code. We add condition to check admin task tag.

| if(!"BookBasicUpdateLocAndExtNo".equalsIgnoreCase(evtCtx.getAdminTask().getTaskTag())){return CONTINUE;} |

Event generation

This code shows event generating: AddToGroupEvent. We look up group IT and pass to method generateEvent(). The result is user added to group IT.

| if(city.equalsIgnoreCase("new york")){Group group = evtCtx.getGroupProvider().findGroup("IT",null);evtCtx.generateEvent("com.netegrity.ims.events.AddToGroupEvent",user,group, null);} |

### 6.2.4 Use Case Examples

We go through the code for all use case examples from official document (Programming Guide for Java > Event Listener API > Event Listener API Overview > Use Case Examples).

Add a user to Microsoft Exchange (specific event listener)

| When a user is successfully added to the admin role Exchange Users, CA IdentityMinder calls the method after() in an event listener associated with the event AssignAdminRoleEvent. The implementation of the after() method uses an Exchange API to add the user to the Exchange system. The information required to access the Exchange server (SERVER_NAME, ADMIN_ID, ADMIN_PASSWORD, and so on) is included in the user-defined properties of the CA IdentityMinder environment. CA IdentityMinder environment properties are passed to the init() method of the EventListenerAdapter. |

This use case, you just override method after() and do programming to add user to Microsoft exchange. For init() method, you can get in the user-defined properties. Please see the example code at the end of this chapter.

Create a rule for group assignments (specific event listener)

| When a user is created, CA IdentityMinder calls the after() method in an event listener associated with the event CreateUserEvent. The implementation of the after() method evaluates user attributes such as Job Title, Security Level, and Department to assign the user to one or more groups. For each group assignment, the implementation generates the secondary event AddToGroupEvent. This secondary event can be subject to workflow approvals and auditing. |

This use case you have to write condition by checking job title, etc. If it is match, you can generate new event: AddToGroupEvent. It is same as our example: event generation.

Update an RDBMS with user data (class-level event listener)

| Suppose that user information such as user ID, user name, email address, and group membership is stored in an RDBMS. Whenever any user-level event occurs (CreateUserEvent, ModifyUserEvent, and so on), the user’s record in the RDBMS must be updated. After the event is executed, CA IdentityMinder calls the method after() in an event listener associated with user events. The implementation of this method retrieves the RDBMS connectivity parameters from the CA IdentityMinder environment properties passed into the init() method, and then updates the user record in the RDBMS. |

This use case, we implement logic to update database in method after(). In configuration in management console, we choose listen to “user” level. It means java class will execute on every events about users. (CreateUserEvent, ModifyUserEvent, etc)

Post events to a JMS queue (all event listener)

| After any event is successfully executed, CA IdentityMinder calls the method after() in an event listener associated with all events. This event listener writes all events to a specific Java Message Service (JMS) queue. The Java Naming and Directory Interface (JNDI) name for the queue and the information in the jndi.properties file is configurable through the properties of the CA IdentityMinder environment. The after() method implementation uses the JNDI information to post a simple object message to the queue. |

This one is the same as previous, override method after() and send message to JMS. For configuration in management console select “*”, it will execute when every event occurs.

## 6.3 Logical Attribute API

Logical Attribute API is used to convert between logical attribute (shows on screen) and physical attribute (keeps in user data store). Logical attribute handler execution occurs in the synchronous phase of task processing.

Logical Attributes

A logical attribute value is presented in a task screen field. A logical attribute name appears within vertical bars (|). For example, an Extension logical attribute appears as |Extension|.

| ![](OEBPS/image_rsrc8XP.jpg) |
| Figure 6-7 shows logical attribute |

Logical attribute values are not directly associated with or written to the data store. It needs processing by a logical attribute handler.

Predefined Logical Attributes

CA IdentityMinder has predefined logical attributes for some purposes for example |passwordConfirm|, |oldPassword|. We can use or customized them. Please see office document for more detail.

Physical Attributes

Physical attributes are attributes of the underlying data store (a user directory such as LDAP). If a task screen field is configured with a physical attribute, a value entered into the field is written to the data store.

### 6.3.1 Programming

Create java class extends LogicalAttributeAdapter and override methods:

*   public void toLogical(LogicalAttributeContext apiContext) throws java.lang.Exception

    *   Convert value from physical attribute to be logical attribute.
*   public void toPhysical(LogicalAttributeContext apiContext) throws java.lang.Exception

    *   Convert value from logical attribute to be physical attribute.
*   public void initializeOptionList(LogicalAttributeContext apiContext) throws java.lang.Exception

    *   If you want to render value as list, you need to implement this method and return Vector as display value list on screen.
*   public void initialize(LogicalAttributeContext apiContext) throws java.lang.Exception

    *   In case of create user or create any object, this method set initial value of attribute.

### 6.3.2 Code Example

Our example show convert city (physical attribute) to be office code (logical attribute). The screen will display office as code. When users select office code, it will convert value from office code as city value. 

| ![](OEBPS/image_rsrc8XR.jpg) |
| Figure 6-8 shows user’s screen for updating office  |

Code

1.  Compile our java code: com.book.idm.etc.OfficeCodeLogicalAttr
2.  copy class (include package folder ” com.book.idm.etc” ) to folder “<server>\IdentityMinder.ear\custom”

Configuration: Management Console

1.  In the Management Console, click Environments.
2.  Click the name of the environment where the logical attribute will be used.
3.  Click Advanced Settings.
4.  Click Logical Attribute Handlers.
5.  Click new button and put value as below

| Field Name | Value | Description |
| Name | OfficeCodeLogicalAttr | Name of logical attribute |
| Class | com.book.idm.etc. OfficeCodeLogicalAttr | Name of java class |
| Object Type | User | Type of object that has logical attribute |
| Logical Attributes |  |
| Name | officeCodeList | Name that uses in code. |
| Attribute Name | &#124;officeCodeList&#124; | Name that shows in admin task’s screen |
| Option List | Check | Tell CA IdentityMinder, this attribute is list |
| Name | officeCode | Name that uses in code. |
| Attribute Name | &#124;officeCode&#124; | Name that shows in admin task’s screen |
| Physical Attributes |  |
| Name | officeCodePhyAttr | Name that uses in code. |
| Attribute Name | l | (lower case of L) Name of attribute city in user store. |
|  |  |  |

| ![](OEBPS/image_rsrc8XS.jpg) |
| Figure 6-9 shows logical attribute configuration in management console |

6.  Click Restart Environment button.

Configuration: Identity Manager User Console

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu create admin task.
3.  Create admin task, put value as below

| Field Name | Value | Description |
| Tab: Profile |
| Name | Update Office | Name of admin task |
| Tag | BookBasicUpdateOffice | Tag name of admin task |
| Description | Example for Logical Attribute | Description of admin task |
| Category | Book Example | Where admin task will show. |
| Category Order | 11 |
| Category 2 | Task |
| Category 3 | Basic |
| Primary Object | User | We want to update the city, so you have to choose object user, and action modify. |
| Action | Modify |
| For testing, you can disable some values. 
*   User Synchronization and Account Synchronization: off.

*   Enable Auditing, Enable Workflow, Enable Web Services: uncheck

 |
| Tab: Search |
| Search Screen | Default User Search | Screen for searching user |
|  |  |  |

4.  For Tab: Tabs

    Select standard tab controller.

    Select Profile(UserProfile) from list, and click symbol (+)

    Select browse button at screen text field.

    Click new button to create new screen, and select choice standard profile screen.

    Put value

*   Name: Book Example: Update Office
*   Tag: BookBasicUpdateOffice

    Add attribute: |officeCode|

*   Attribute Name: |officeCode|
*   Style: Drop down
*   Name:  Office Code
*   Click apply button to finish.

    Add attribute: |officeCodeList|

*   Attribute Name: |officeCodeList|
*   Style: Hidden
*   Click apply button to finish.

    Add attribute: City

*   Attribute Name: City
*   Style: Hidden
*   Click apply button to finish.

    Click ok

| ![](OEBPS/image_rsrc8XT.jpg) |
| Figure 6-10 shows  configuration of each attributes |

5.  Submit to finish creating task.

Add this task to admin role.

1.  Select tab: Roles and Tasks, and select menu modify admin role.
2.  Select role system manager.

*   Select tab: task
*   Select  filter by category:  Book Example
*   Select add task: Update Office

3.  Click submit to finish modify admin role.

How it works

Execute admin task: Update office.

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example, and select menu update office
3.  Search a user, the screen will show office code drop down.
4.  Modify office code attribute, and click submit.

You can check the result by login to the user store , search the modified user, and check city attribute. The city attribute in user store is “l”.

Method: toLogical()

This method converts the value from physical to be logical attribute. The code has 3 steps:

*   Step 1: Get the value from physical attribute.
*   Step 2: Mapping, convert from physical to logical attribute. You may have other ways to convert. Our code use map for conversion.
*   Step 3: Set the value back to logical attribute.

| private String ATTR_REFER_PHY = "officeCodePhyAttr";@Overridepublic void toLogical(LogicalAttributeContext ctx) throws Exception {//get physical attribute valueString city = ctx.getPhysicalAttributeName(ATTR_REFER_PHY);String cityValue = ctx.getPhysicalAttributeValue(city);//mapping from physical value to logicalString officeCodeValue = indexPhysicalAsKey.get(cityValue);if(officeCodeValue!=null){//Set value for logicalString officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);ctx.setLogicalAttributeValue(officeCode, officeCodeValue);}} |

In our code can explain as step by steps:

Step 1: We get value from physical attribute, variable “officecodePhyAttr” link to attribute “l” in user data store when we do configuration.

| ![](OEBPS/image_rsrc8XU.jpg) |
| Figure 6-11 shows attribute mapping for physical attributes |

Step 2: mapping, we have our helper object (indexPhyicalAsKey) class to convert to be logical value. In the real world requirement, you may have some logic to convert. The official document said:

| Logical attribute handler execution occurs in the synchronous phase of task processing. If response time during interaction with a third-party system is an issue, the same objective can be performed using an event listener during the Pre-approval state. |

It means if you want to call third-party to convert attribute value, you should concern response time because logical attribute API execute under synchronous phase.

Step 3: The last line of code is set value back to logical attribute value

| ctx.setLogicalAttributeValue(officeCode, officeCodeValue); |

Method: toPhysical()

This method is reverse of toLogical(). The steps are same but reverse.

*   Step 1: Look up logical attribute value.
*   Step 2: Mapping, convert to be physical value.
*   Step 3: Set value back to physical attribute.

| @Overridepublic void toPhysical(LogicalAttributeContext ctx) throws Exception {//step 1String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);String officeCodeValue = ctx.getLogicalAttributeValue(officeCode);//step 2String cityValue = indexLogicalAsKey.get(officeCodeValue);//step 3String city = ctx.getPhysicalAttributeName(ATTR_REFER_PHY);ctx.setPhysicalAttributeValue(city, cityValue);} |

Attributes in admin task

We declare 3 fields on screen:

*   2 logical attributes:|officeCode| (dropdown) and |officeCodeList| (hidden) are required for dropdown.
*   1 physical attribute: City (hidden) we need because we populate city attribute. So city attribute must be present in admin task context.

Method: initializeOptionList()

If you want dropdown for this logical attribute, you have to implement this method. You just set vector to logical attribute value.

| ctx.setLogicalAttributeMultiValue(officeCodeList,officeCodes); |

Make sure you check option list in configuration page.

| ![](OEBPS/image_rsrc8XV.jpg) |
| Figure 6-12 shows check box for option list |

Method: initialize()

This method will be execute for task create only, for example create user, create account. This method used for initial value for logical attribute.

For modification task, this method has never been executed. Our example never called this method. If you want to execute this method, you have to change action to be “create”. (The primary object is user) And then you execute this admin task again, you will see this method set default value “006NY”.

| @Overridepublic void initialize(LogicalAttributeContext ctx) throws Exception {String officeCodeName = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);String officeCodeValue = ctx.getLogicalAttributeValue(officeCodeName);if(officeCodeValue == null&#124;&#124;officeCodeValue.trim().length()==0){ctx.setLogicalAttributeValue(officeCodeName, "006NY");}} |

Method: validate()

Validate() method will be execute when user submit task. You can test our code by select empty value and clicks submit.

| @Overridepublic void validate(LogicalAttributeContext ctx) throws Exception {String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);String officeCodeValue = ctx.getLogicalAttributeValue(officeCode);if(officeCodeValue==null&#124;&#124;officeCodeValue.trim().length()==0){IMSException e = new IMSException();e.addUserMessage("Invalid office value");throw e;}} |

| ![](OEBPS/image_rsrc8XW.jpg) |
| Figure 6-13 shows exception during validate() method |

Screen-Defined Logical Attributes vs. our Logical Attribute

When you create screen, you can create screen-Defined Logical Attributes. The screen-Defined Logical Attributes are defined for only one screen. They can’t share with other screens but the logical attributes can share.

### 6.3.3 Use Case

Refer to the official document, Progamming guide > Logical Attribute > Use Case Examples

Format data from a data source

| In the user directory, a telephone number is stored as the physical attribute phone. It has 10 digits—for example, 9785551212\. This physical attribute is associated with the logical attribute formatted_phone. |

This use case need to override toLogical(), to return formatted phone and override method toPhysical() to convert from formatted phone to be number.

Validate data entry

| The physical attribute employeeNumber exists in a data source, and it is mapped to the logical attribute validEmployeeNumber. After a user assigns an employee number to the validEmployeeNumber attribute on the task screen and clicks Submit, CA IdentityMinder calls a custom logical attribute handler to query the data source to be sure that the supplied employee number exists in employeeNumber. If it does not exist, the logical attribute handler throws an exception. |

This use case queries the database to convert between logical attribute and physical attribute.

| @Overridepublic void toLogical(LogicalAttributeContext ctx) throws Exception {//step 1String empNo = ctx.getPhysicalAttributeName(“employeeNumber”);String empNoValue = ctx.getPhysicalAttributeValue(empNo);//step2String validEmpNoValue = queryByPhysicalID(validEmpNoValue);//step 3if(validEmpNo!=null){String validEmpNo = ctx.getLogicalAttributeName(“validEmployeeValue”);ctx.setLogicalAttributeValue(validEmpNo, validEmpNoValue);return;}throw new IMSException(“invalid employee number”);} |

Add a drop-down list to a task screen

| A task screen requires a customer to provide the type of service they have purchased—Gold, Silver, or Bronze. These options are presented in a drop-down list associated with the logical attribute serviceType. When the customer chooses a service level and clicks Submit, CA IdentityMinder calls a logical attribute handler that converts the selected service level to the corresponding physical attribute value (1, 2, or 3) and assigns the value to the physical attribute type. |

This use case is same as our example. You have to implement initializeOptionList() returns type of service: Gold, Silver, or Bronze and implement method toPhysical() and toLogical() convert the value between type of service(Gold, Silver, or Bronze) to be number (1,2, or 3).

## 6.4 Validation Rules

Attribute validation rules help validate value that user types on screen meet the right format. Validation of user data entry can be regular expression, JavaScript, or Java implementations. In this book will focus on Java programming. For regular expression and JavaScript, you can see example from official document (but validation rules by Java programming is missing details).

Types of Validation Rules

*   Task-level validation: validation rule directly to a field on a particular task screen. You can define rule during task-screen configuration.
*   Directory-level validation: validate the attribute’s value but It has been applied all tasks. It is global scope. You have to define the rule in directory.xml

### 6.4.1 Programming

For task-level validation, you have to implement TaskValidator and override method validate().

| public boolean validate(BLTHContext ctx, String attrValue,StringRef changedValue, StringRef errorMsg) throws AttributeValidationException |

For directory-level validation, you have to extend AttributeValidator and override method validate(). It is almost same as task-validation but there are some details. You will see in our examples.

| public boolean validate(Object attrValue, StringRef changedValue, StringRef errorMsg)throws AttributeValidationException |

### 6.4.2 Code Example: Task-level validation

This example require attribute Employee Number, please check your user store. Our requirement uses employee number attribute. The validate rule is

*   Employee number must be number only.
*   Maximum is 4 Digits.
*   If user types 1-3 digits, the format fill in 0 as prefix. For example: 2, the right format will be 0002

| ![](OEBPS/image_rsrc8XX.jpg) |
| Figure 6-14 shows user’s screen for updating employee number  |

Code

1.  Compile our java code: com.book.idm.etc.EmployeeNumberTaskValidator
2.  Copy class (include package folder ”com.book.idm.etc” ) to folder “\IdentityMinder.ear\custom”

Configuration: Identity Manager User Console

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu create admin task.
3.  Create admin task, put value as below

| Field Name | Value | Description |
| Tab: Profile |
| Name | Update Employee Number | Name of admin task |
| Tag | BookBasicUpdateEmployeeNumber | Tag name of admin task |
| Description | Example for Validation | Description of admin task |
| Category | Book Example | Where admin task will show. |
| Category Order | 11 |
| Category 2 | Task |
| Category 3 | Basic |
| Primary Object | User | We want to update the employee number, so you have to choose object user, and action modify. |
| Action | Modify |
| For testing, you can disable some values. 
*   User Synchronization and Account Synchronization: off.

*   Enable Auditing, Enable Workflow, Enable Web Services: uncheck

 |
| Tab: Search |
| Search Screen | Default User Search | Screen for searching user |
|  |  |  |

4.  For Tab: Tabs

    Select standard tab controller.

    Select Profile(UserProfile) from list, and click symbol (+)

    Select browse button at screen text field.

    Click new button to create new screen, and select choice standard profile screen.

    Put value

*   Name: Update Employee Number
*   Tag: BookBasicUpdateEmployeeNumber

    Add attribute: Employee Number

*   Attribute Name: Employee Number
*   Style: Text
*   Name:  Employee Number
*   Validation Java Class: com.book.idm.etc.EmployeeNumberTaskValidator
*   Click apply button to finish.

    Click ok

| ![](OEBPS/image_rsrc8XY.jpg) |
| Figure 6-15 shows  configuration of employee number attributes |

5.  Submit to finish creating task.

Add task to admin role

1.  Select tab: Roles and Tasks, and select menu modify admin role.
2.  Select role system manager.

*   Select tab: task
*   Select  filter by category:  Book Example
*   Select add task: Update Employee Number

3.  Click submit to finish modify admin role.

How it works

Execute admin task: Update employee number.

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example, and select menu update employee number.
3.  Search a user, the screen will show employee number as text field.
4.  Modify employee number attribute, and click submit.

Method validate()

There are 2 cases of error:

*   Put 5 digits of employee number.

| ![](OEBPS/image_rsrc8XZ.jpg) |
| Figure 6-16 shows error by return value |

*   Put any characters.

| ![](OEBPS/image_rsrc8Y0.jpg) |
| Figure 6-17 shows error by exception |

There are 2 ways to return error message, you can pick one.

*   Return false and set message back by errorMsg.reference.

| if(attrValue.trim().length()>4){errorMsg.reference = "Employeer Number can not more than 4 digits";return false;} |

*   Throw exception and put message as parameter.

| try{...int employeeNo = new Integer(attrValue);...}catch(Exception e){throw new AttributeValidationException("Employeer Number:invalid format");} |

Try to put number one digit, for example 1, and submit. Login to user store, employee number will display as 0001\. We can modify value by using changedValue.reference parameter.

| int employeeNo = new Integer(attrValue);DecimalFormat format = new DecimalFormat("0000");changedValue.reference = format.format(employeeNo); |

Task-level validation provides BLTHContext as parameter. You can use BLTHContext  to search some attribute from managed object, for example you have to check the new value must be unique.

### 6.4.3 Code Example: Directory-level validation

This example will use same requirement as task-level validation. Please disable task-level validation from admin task: update employee number.

*   Search admin task: update employee number

*   Go to tab: tabs and modify screen: Update Employee Number.
*   Remove value of validation java class: com.book.idm.etc.EmployeeNumberTaskValidator

Code

1.  Compile our java code: com.book.idm.etc.EmployeeNumberDirValidator
2.  Copy class (include package folder ”com.book.idm.etc” ) to folder “\IdentityMinder.ear\custom”

Configuration: Management Console

1.  In the Management Console, click Directory.
2.  Click the name of the user store directory.
3.  Click export button at bottom page. You will get the xml file.
4.  Using text editor to open the xml file.
5.  You have to modify 2 places:

    Add validation rule under element <ImsManagedObjectAttrValidation>. Please go check xml schema from official document.

| <ValidationRule name="Employee Number pattern" description="Validates employee number" messageid="4002"><Java class="com.book.idm.etc.EmployeeNumberDirValidator"/></ValidationRule><ValidationRuleSet name="Employee Number format"description="validate employee number format"><ValidationRule name="Employee Number pattern"/></ValidationRuleSet> |

5.2  add attribute validationruleset =”Employee Number format” for employeeNumber attribute.

| <ImsManagedObjectAttr physicalname="employeeNumber"description="Employee Number"displayname="Employee Number"valuetype="String"maxlength="0"validationruleset="Employee Number format"/> |

6.  Go back management console, and select our use store directory.
7.  Click update button and select our xml file. Click next and finish button. The screen will show message in console, and click continue and restart environment.

How it works

Execute admin task: Update employee number.

4.  Log into the Identity Manager User Console as administrator.
5.  Select tab: Book Example and select menu update employee number.
6.  Search a user, the screen will show employee number as text field.
7.  Modify employee number attribute, and click submit.

Method validate()

There are 2 ways to show error message. It is almost same as task-level validation but the difference is how to get message.

*   If you return false, you do not need to set any message. The message came from the xml file. The attribute messageid="4002" in element < ValidationRule > indicate value. The value of message came from property file:IMSException.properties in directory custom\resourceBundle.
*   If you throw exception, the message came from message id in constructor. Our code use value 4002\. You can change to be another number.

| try{...}catch(Exception e){throw new AttributeValidationException("Employee Number",                                                          attrValue.toString(),"4002","invalid format");} |

| ![](OEBPS/image_rsrc8Y1.jpg) |
| Figure 6-18 shows error from messageid in IMSException.properties file |

Validation rule set

In the Management Console, and click user store directory. Scroll down until section validation rule set. Click link inside, you will see the details.

| ![](OEBPS/image_rsrc8Y2.jpg) |
| Figure 6-19 shows validation rule sets in management console |

Please disable directory-level validation rule after testing. We will use employee number in book volume II.

## 6.5 Email Notification

This section is special topic. It needs it for the next API: Notification Rule API. The CA IdentityMinder official document has topic email notification in administration guide, not in the programming guide.

Configure SMTP

You need to check SMTP configuration before starting email notification. There are 2 things to check before working with email notification. The first one is SMTP configuration, what is SMTP server.

*   Jboss: check jboss_home\server\default\deploy\mail-service.xml
*   WebLogic: check a mail session with JNDI name “nete/Mail”
*   WebSphere: check mail session object called mailMail

Please see the official document administration guide > email notifications > configure SMTP Setting. JBoss, WebSphere and WebLogic have different configuration.

The second one is file email.properties in folder iam_im.ear\config\com\netegrity\config. This file is used for specific return email address.

### 6.5.1 How to implement email notification

There are 2+1 ways to implement email notification. The official document introduces 2 ways to send email. This book offers another way to send email.             

1.  Email Notification Policies.

*   No coding is required to create email notifications.
*   Email notification policies are Policy Xpress policies. You can create condition (entry rule) when policy should run.
*   It is under the System tab, select Email menu.

2.  Email templates

*   Require code (JSP/java syntax)
*   Support dynamic content (include if-else condition in content).
*   Support Notification Rule API.

Both email notification policies and email templates are depending on task completion or event outcome (approve, reject or fail). You cannot send email any time you want. For example, you may have long process steps:

*   Step 1: HR staffs update user’s office.
*   Step 2: Send email to remind manager for approval.
*   Step 3: Send remedy ticket and then send email to HR staff about ticket number.
*   Step 4: Send web services request to facility system to request permission to access the office. Send email to HR staff after web services response successfully.  If request fail, send email to IT administrator.
*   Step 5: Wait until expected hire date, Send email to confirm user and HR staff.

For long flow process, you have to analysis solutions when email has to be notified. This book has a trick to send email by java API.

3.  Service API

*   It can send email anytime.
*   Support dynamic content. You can use any popular framework such as velocity.
*   Please note, CA IdentityMinder document do not mention this way. Please use with your own risk.

### 6.5.2 Code Example: Email Template

This example shows how to implement email template. Understanding email template is requires for next topic Notification Rule API. Our example code will send email after administrator execute admin task: Update Location and Ext Number successfully.

Code

1.  Locate file “Update Location and Ext Number.tmpl”
2.  Copy file to folder “<server>\IdentityMinder.ear\custom\emailTemplates\default\completed”

Configuration: Management Console

1.  In the Management Console, click Environments.
2.  Click the name of the environment.
3.  Click Advanced Settings.
4.  Click Email.
5.  Select check box Tasks e-mail enabled.

| ![](OEBPS/image_rsrc8Y3.jpg) |
| Figure 6-20 shows task e-mail enabled configuration |

6.  Scroll down until you see “Send e-mail when the following tasks are completed or during workflow”

    In Admin Task Name, select Equal from drop down and put value: Update Location and Ext Number

    Update Location and Ext Number will be displayed in search result. Select check box on that task and click add button.

    You should see task Update Location and Ext Number in task table

| ![](OEBPS/image_rsrc8Y4.jpg) |
| Figure 6-21 shows adding task for email template |

7.  Click save button.
8.  Click Restart Environment button.

How it works

Execute admin task: Update Location and Ext Number.

6.  Log into the Identity Manager User Console as administrator.
7.  Select tab: Book Example, and select menu Update Location and Ext Number.
8.  Search a user, the screen will show city drop down.
9.  Modify city attribute, and click submit.

Got the Email

After administrator submitted, the use should get email that has content as below:

| ![](OEBPS/image_rsrc8Y5.jpg) |
| Figure 6-22 shows email content |

Open file “Update Location and Ext Number.tmpl”, you will see code for email content. They have special variables likes _to or _taskContextInformation. _to means receiver of email. We will cover more detail in notification rule API. For _taskContextInformation is a task context. Please see administration guide for more details.

| <%_to = _util.getNotifiers("USER", "");_cc = "";_bcc = "" ;_subject = "Update Location and Ext Number";%>User:<%var imsEventContexts  = _taskContextInformation.getExposedEventContexts();if(imsEventContexts != null){var eventContext = imsEventContexts.get(0);template.add(eventContext.getPrimaryObjectName());}%>has been updated location and ext number successfully. |

If you are not getting email or error display on screen, please check log file. SMTP may not correct.

If you do not get email but administrator gets email instead and subject is “Update Location and Ext Number Completed”, that means CA IdentityMinder uses default template: defaultTask.tmpl sending email. Please check folder name “default/completed” and admin task should matches with our template name exactly. Restart server or environment may is required for some modification.

### 6.5.3 Code Example: Email notification by Service API

This example shows how to send email by CA IdentityMinder service. We will send email by using business logic task handler. Please disable email template from previous example.

Code

1.  Compile our java code: com.book.idm.etc.SendEmail
2.  Copy class (include package folder ” com.book.idm.etc” ) to folder “<server>\IdentityMinder.ear\custom”

Configuration: Identity Manager User Console

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab Roles and Tasks, and select menu modify admin task.
3.  Search admin task: Update Location and Ext Number.
4.  Click button Business Logic Task Handlers.
5.  Click add and put value as below

| Field Name | Value | Description |
| Name | SendEmail | Name of business logic task handler |
| Class | com.book.idm.etc.SendEmail | Name of java class |

6.  Click ok and submit task.

How it works

Execute admin task: Update Location and Ext Number.

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example, and select menu Update Location and Ext Number.
3.  Search a user, the screen will show city drop down.
4.  Modify city attribute, and click submit.

Service API

The code is pretty straightforward.  You can send email by method sendMail().

| InternalServiceAccessor.getEmailProviderService().sendMail(from,to,cc,bcc,encoding,contentType,priority,subject,body); |

We can access administrator email in configuration: email.properties by calling getAdminEmailID().

| String adminEmail = InternalServiceAccessor.getEmailProviderService().getAdminEmailID();String from = adminEmail; |

We can get email recipient by ProviderAccessor. (We cannot get email by BLTH because email attribute does not presence in admin task)

| User user = ctx.getUserProvider().findUser(ctx.getUser().getUniqueName(), null);String toEmail = user.getAttribute("mail");String to = toEmail; |

This example sends email using business logic task handler (Email has been sent before task complete) If you want to send email after task complete, please send email by event listener in method after().

## 6.6 Notification Rule API

This API is used with email template only. It determines who receive an email notification.

### 6.6.1 Programming

You have to create java class extend NotificationRuleAdapter and override method evaluate().

*   public Vector evaluate(NotificationRuleContext ctx, Hashtable templateParams)

    *   You have to put email address into vector object and return. The first parameter is context is almost same as other APIs. The second parameter telmplateParams keeps name/value pairs of user-defined data that may be specified in the email template.

### 6.6.2 Code Example

This example require previous example: email template. So you need to enable email template on task completion. Our requirement is when administrator executes admin task: Update Location and Ext Number, it has to send email to user and cc manager. If they do not have manager, you can skip cc email.

Code

1.  Compile our java code: com.book.idm.etc.ManagerNotificationRule
2.  Copy class (include package folder ” com.book.idm.etc” ) to folder “<server>\IdentityMinder.ear\custom”
3.  Modify file Update Location and Ext Number.tmpl in folder email template.  Add notification rule name for _cc.

| _cc = _util.getNotifiers("ManagerNotificationRule","param1=A,param2=B"); |

Configuration: Management Console

1.  In the Management Console, click Environments.
2.  Click the name of the environment.
3.  Click Advanced Settings.
4.  Click Notification Rules.

| Field Name | Value | Description |
| Name | ManagerNotificationRule | Name of notification rule |
| Class | com.book.idm.etc.ManagerNotificationRule | Name of java class |

5.  Click save and restart environment.

How it works

Execute admin task: Update Location and Ext Number.

1.  Log into the Identity Manager User Console as administrator.
2.  Select tab: Book Example, and select menu Update Location and Ext Number.
3.  Search a user, the screen will show city drop down.
4.  Modify city attribute, and click submit.

Email Recipient

We user ProviderAccessor and look up manager of user and then you get attribute “mail” and add email address into vector and return.

| String emailManager = manager.getAttribute("mail");if (emailManager != null &#124;&#124; emailManager.trim().length() != 0) {emails.add(emailManager);} |

Template parameters

In email template, we add notification rule.

| _cc = _util.getNotifiers("ManagerNotificationRule","param1=A,param2=B"); |

"param1=A,param2=B" is template parameter. We can get these values from parameters templateParams.

| public Vector evaluate(NotificationRuleContext ctx,Hashtable templateParams){Enumeration keys = templateParams.keys();while (keys.hasMoreElements()) {Object key = keys.nextElement();System.out.println("parameter: " + key + "="+ templateParams.get(key));}} |

### 6.6.3 Use Case

We implement use case example in the official document (Programming Guide for Java › Notification Rule API › API Overview > Use Case Examples).

Notify a single user

| When user data is being modified, retrieve the user’s name and cc the user with the status of the request. |

Form notification rule code, you can get user name from context and add suffix as email. You have to call notification rule in _cc of email template.

| String userName = ctx.getSubject().getFriendlyName();String email = userName+"@somedomain.com";emails.add(email); |

Notify a group

| When a user is being created and added to a group, retrieve the group name (from the context information passed into the notification rule) and cc the group about the new group member. |

We write the email template under event: AddToGroupEvent, so primary object is group. We get group name and add group name as context information in email template and pass to notification rule.

| String groupName = _eventContextInformation.getPrimaryObjectName();_cc = _util.getNotifiers("NotificationRule","group="+groupName); |

### 6.6.3 Notification Rule and Email Template Limitation and Service API

There are some issues about email template and notification rules:

*   The Notification Rule works with email template only, and Notification Rule is not necessary for Service API.

*   The goal of notification rule is who email recipients are. While we can use service API (InternalServiceAccessor.getEmailProviderService()), we can access recipients: to, cc and bcc. We can use context to search email attribute.

*   The email template support dynamic content but you need to learn new JSP tag lib.

*   If you use email template, you may have to learn new tag lib, for example _taskContextInformation. If you choose service API, you can use simple java code or the popular template java framework likes Apache Velocity generate email content.

*   The email template works under conditions of task or event, fail, complete, etc.

*   While as service API can called any time in code.

## 6.7 Task Execution Web Service (TEWS)

Many people confuse about Task Execution Web Service.  The task execution web service or TEWS make admin task as web services producer. It is not consumer. The TEWS is a web service interface that allows third-party client applications to submit remote tasks to CA IdentityMinder.

| ![](OEBPS/image_rsrc8Y6.jpg) |
| Figure 6-23 shows how TEWS works |

### 6.7.1 Code Example

We develop java client to consume TEWS. We want to execute our admin task: Update Location and Ext Number by java web services.

Please disable all previous code: Policy Xpress, workflow, validation and email notification.

Configuration: Management Console

1.  In the Management console, click Environments.
2.  Click the name of the environment where the web services used.
3.  Click Advanced Settings.
4.  Click Web Services.
5.  Put value as below

| Field Name | Value | Description |
| Enable Execution | Check | Check to enable the Task Execution Web Service (TEWS) for the environment. |
| Enable WSDL Generation | Check | Check to enable WSDL generation for the environment. |
| Enable admin_id | Check | TEWS uses the admin ID found in the SOAP message sent to the web service to authenticate the request.If this option is not selected, the ID of the user who generated the request is used to authenticate the request. |
| SiteMinder Authentication | none | For authentication, in our example we use none. |

| ![](OEBPS/image_rsrc8Y7.jpg) |
| Figure 6-24 shows management console |

Configuration: Identity Manager User Console

1.  Log into the User Console.
2.  Select the Roles and Tasks tab. Select Admin Tasks. Select Modify Admin Task.
3.  Search and select the admin task: Update Location and Ext Number.
4.  Select Enable Web Services.
5.  Click Submit to save your changes.

| ![](OEBPS/image_rsrc8Y8.jpg) |
| Figure 6-25 shows admin task configuration |

Code

1.  Generate java from WSDL by Axis API. We use command WSDL2Java to generate java code. Please check all path of jars file.

| java -cp lib/axis.jar;lib/log4j-1.2.8.jar;lib/wsdl4j-1.5.1.jar;lib/commons-logging-1.0.4.jar;lib/commons-discovery-0.2.jar;lib/jaxrpc.jar;. org.apache.axis.wsdl.WSDL2Java -wrapArrays=true http://<host>:8080/idm/TEWS6/<enviroment>?wsdl |

2.  Copy the generated code to eclipse and compile.
3.  Open java code in eclipse: com.book.idm.etc.TEWSClient
4.  Check the required parameters.

    *   userId is user that you want to modify.
    *   adminDN is name who is execute this task. We will go more detail later.
    *   City and extNumber are the values that we want to modify.

| String userId = "allmi01";String adminDN = "uid=superuser,ou=users,ou=na,dc=host,dc=com";String city = "New York";String extNumber = "1234"; |

How it works

1.  Execute our java code from eclipse : com.book.idm.etc.TEWSClient
2.  Login in to the user store directory and check city attribute.

The code starts from java class has same name as tag of admin task: BookBasicUpdateLocAndExtNo. The code admin task has 2 tabs: search tab and profile tab.

| BookBasicUpdateLocAndExtNo task = new BookBasicUpdateLocAndExtNo();...task.setBookBasicUpdateLocAndExtNoSearch(search);...task.setBookBasicUpdateLocAndExtNoUserProfileTab(profileTab); |

For search tab, we search using filter by user id.

| BookBasicUpdateLocAndExtNoSearchFilter[] filters = newBookBasicUpdateLocAndExtNoSearchFilter[1];BookBasicUpdateLocAndExtNoSearchFilter filter = newBookBasicUpdateLocAndExtNoSearchFilter();filter.setIndex(new BigInteger("0"));filter.setField("%USER_ID%");filter.setOp(OperatorType.EQUALS);filter.setValue(userId);filters[0] = filter;search.setFilter(filters); |

We set the city and |extNumber| attributes in profile tab object.

| BookBasicUpdateLocAndExtNoUserProfileTab profileTab = newBookBasicUpdateLocAndExtNoUserProfileTab();profileTab.setL(city);profileTab.set_BAR_ExtNumber_BAR_(extNumber); |

In our code, we have additional 2 files: LogHandler.java and client-config.wsdd. These files are helper for Axis client logger. You can see soap message between server and client. You can use this xml as request in SOAP UI or any web services tool.

SOAP Request

| <?xml version="1.0" encoding="UTF-8"?><soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><soapenv:Body><TaskContext xmlns="http://tews6/wsdl"><admin_id>uid=superuser,ou=users,ou=na,dc=host,dc=com</admin_id></TaskContext><BookBasicUpdateLocAndExtNo xmlns="http://tews6/wsdl"><BookBasicUpdateLocAndExtNoSearch><Filter index="0"><Field>%USER_ID%</Field><Op>EQUALS</Op><Value>allmi01</Value></Filter></BookBasicUpdateLocAndExtNoSearch><BookBasicUpdateLocAndExtNoUserProfileTab><l>New York</l><_BAR_ExtNumber_BAR_>1234</_BAR_ExtNumber_BAR_></BookBasicUpdateLocAndExtNoUserProfileTab></BookBasicUpdateLocAndExtNo></soapenv:Body></soapenv:Envelope> |

SOAP Response

| <?xml version="1.0" encoding="UTF-8"?><soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns="http://tews6/wsdl" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.xmlsoap.org/soap/envelope/ http://schemas.xmlsoap.org/soap/envelope/" ><soapenv:Body><ImsStatus version="6.0" ><transactionId>cb40e808-a5029bf5-aeacf1a7-1401ca</transactionId></ImsStatus></soapenv:Body></soapenv:Envelope> |

Authentication and Authorization

In management console: web services properties, because we check option enable admin_id (allow impersonation), we can pass any administrator DN as who execute admin task.

| ctx.setAdmin_id(adminDN);    |

If you uncheck option enable admin_id (allow impersonation), you need to do authentication. You have to select SiteMinder Authentication, you have to modify code for authentication.

| Tews6SoapBindingStub stub = (Tews6SoapBindingStub) _port;stub.setUsername("SuperAdmin");stub.setPassword("test");stub.setMaintainSession(true);stub._setProperty("Cookie","SMCHALLENGE=YES"); |

For Authorization, you may need configuration in web.xml. Please see the official document Programming Guide for Java > Task Execution Web Service > Authorization.             

Public Task

When you define admin task, there is one check box: public task. The public task means the task available to users who have not logged in to CA IdentityMinder. The default public tasks are forgotten password and self-registration. The public task can use in requirement for the third party want to query or get data from CA IdentityMinder without authentication.

| ![](OEBPS/image_rsrc8Y9.jpg) |
| Figure 6-26 shows public task check box in admin task configuration |

The client coding for the public task TEWS need to change 3 places are search, port type and context. If you modify check box public task, it needs to regenerate java code from WSDL.

For search, you can’t use search filter. You have to use search subject because public task design for self-modification.

| BookBasicUpdateLocAndExtNoSearchSubject[] subjects = newBookBasicUpdateLocAndExtNoSearchSubject[1];BookBasicUpdateLocAndExtNoSearchSubject subject = newBookBasicUpdateLocAndExtNoSearchSubject();subject.setUID("uid=allmi,ou=users,ou=northamerica,dc=server,dc=com");subject.setIndex(new BigInteger("0"));subjects[0] = subject;search.setSubject(subjects);task.setBookBasicUpdateLocAndExtNoSearch(search); |

The port type and context have to be change public task.

| Tews6PublicPortType portType = locator.getTews6PublicPort();//Tews6PortType portType = locator.getTews6Port();PublicTaskContext ctx = new PublicTaskContext();//TaskContext ctx = new TaskContext();//ctx.setAdmin_id(adminDN);      |

## 6.8 Additional Concept

Access user defined properties

Business logic task handler, logical attribute, event listener, etc. have the user defined properties.

| ![](OEBPS/image_rsrc8YA.jpg) |
| Figure 6-27 shows user defined properties |

We can access these properties by overriding method init(java.util.Hashtable imeProperties) of interface com.netegrity.imapi.LifeCycle. You can keep these value in class variable and use in other methods.

| @Overridepublic void init(Hashtable imeProperties) throws Exception {System.out.println(imeProperties.get("param1"));} |

Access to Managed Objects

The EventContext, LogicalAttributeContext, NotificationRuleContext, ParticipantResolverContext, and etc, extends ProviderAccessor. They can perform search or modify managed object same as BLTHContext or Workflow context  

logErrorMessage

The context extends Logger. The Logger class provides 4 logging methods. It will log a message to the application server log.

*   logDebugMessage(java.lang.String message, boolean addDetail)
*   logErrorMessage(java.lang.String message, boolean addDetail)
*   logInfoMessage(java.lang.String message, boolean addDetail)
*   logWarningMessage(java.lang.String message, boolean addDetail)

If addDetail is true, it will print more details about admin DN, task name or adapter name. Please see java doc for more details.

## 6.9 Conclusion

This chapter, we are complete cover all APIs more over business logic task handler and workflow API. We can conclude all APIs as below table:

| API name and purpose | Phase* | Types | Note or Limitation |
| Participant Resolver : determines the participants in a workflow activity | A | - | Using within workflow only |
| Event Listener: listens for an event. It performs custom business logic | A | Listener Level (configure in management console) 
*   Listens a specific event

*   Listens a group of events

 | Event Listener can generate new event. (work flow belong to event can generate event also) |
| Logical Attribute: converting between logical attribute (shows on screen) and physical attribute (keeps in user data store) | S | Do not confuse between: 
*   Logical Attribute

*   Screen-Defined Logical Attributes (not part of this API)

 |  
*   Logical Attribute can share with any screen.

*   Screen-Defined Logical Attributes scope only one screen.

 |
| Validation Rule: validate value that user types on screen meet the right format. | S |  
*   Task-level validation

*   Directory-level validation

 | Task-level scope only in the defined screen but directory-level applies to that field in all screens. |
| Email Notification: sending email | S or  A |  
*   Email Notification Policies (policy Xpress)

*   Email templates

*   (Service API)

 |  
*   Email Notification Policies has limit for email recipient and content.

*   Email template and Service API are programming.

 |
| Notification Rule: determines the users receive an email notification. | S or A | - | Works with email template only. |
| Task Execution Web Services: is web services producer. It allows third-party client applications to submit remote tasks | -            | Depending on configuration: 
*   Is it enable admin_id?

*   Is it public task?

 | Need configure for authentication and authorization. |

* Phase. There are 2 phases: A means asynchronous and S means synchronous.

I suggest getting book volume II shows many advanced examples. The mainly API are business logic task handler and work flow.

# Appendix A: Import Workflow

Please download code from book’s web site. Please use the CODE: 120140924

Import workflow

*   Start IdentityMinder Server
*   Run WorkPoint Designer
*   Select file > import
*   Select file “IdmCodeWorkflow.zip”
*   Choose select all

| ![](OEBPS/image_rsrc8YB.jpg) |
| Figure A-1 shows import screen |

*   When screen ask are you importing to empty database, select “No”. Click next.
*   When screen show This Import will, select “Treat all objects as new objects”. Click next.
*   Screen ask “If a duplicate Name or Reference is encountered”, select Rename he imported Name or Reference to be unique. Click Next
*   Dialog will show list of our import code, click finish
*   Select Open process, and verify. You should see process with reference name start with “BookEx.”

| ![](OEBPS/image_rsrc8YC.jpg) |
| Figure A-2 shows all processes |

# Appendix B: Hot Deployment

CA IdentityMinder does not support hot deployment. When you update code in folder <IdentityMinder>/custom, application server will not load your class. There are a few ways to fix:

Restart Server or Redeploy IdentityMinder.ear

You have to restart or redeploy after you update code. This solution takes time and not suitable for development process.

OSGi

The new version of application server supports OSGi specification. OSGi enable class load dynamically at runtime. Please check your application server document.

Rename Code

I prefer this way. It is pretty simple and does not take time. CA IdentityMinder requires 2 things: configuration and code. For example, my code is MyCode.java

*   BLTH

    *   Code: I rename code to MyCode1.java, compile and copy to folder “custom”.
    *   Configuration: update java class name in admin task’s BLTH.
*   Workflow

    *   Code: I rename code to MyCode1.java, compile and copy to folder “custom”.
    *   Configuration: update agent script in node

You can do the same in Listener and other APIs.

#CODE : DGUJK101