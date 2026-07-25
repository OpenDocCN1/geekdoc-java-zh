![](cover_image.jpg)

![](index-1_1.jpg)

Web Services

Author: Antonio J. Martín & Ramón Egido

**CONTENTS**

[**1.** **INTRODUCTION ................................................................................................... 5**](#index_split_000.html_5)

[**2.** **SOA ARCHITECTURE ......................................................................................... 6**](#index_split_000.html_5)

[2.1.](#index_split_001.html_6)

[SERVICES ........................................................................................................... 6](#index_split_001.html_6)

[2.2.](#index_split_001.html_7)

[WEB SERVICE .................................................................................................... 7](#index_split_001.html_7)

[2.3.](#index_split_001.html_7)

[STRUCTURE OF A WEB SERVICE ........................................................................ 7](#index_split_001.html_7)

[**3.** **WEB SERVICES ARCHITECTURE STANDARDS .......................................... 9**](#index_split_001.html_8)

[3.1.](#index_split_001.html_9)

[SOAP ................................................................................................................. 9](#index_split_001.html_9)

[*3.1.1.* *SOAP messages ........................................................................................... 9*](#index_split_001.html_9)

[*3.1.2.* *Types of SOAP messages ........................................................................... 11*](#index_split_001.html_11)

[3.1.2.1\. RPC Messages. ................................................................................... 11](#index_split_001.html_11)

[3.1.2.2\. Document Oriented Messages ............................................................ 12](#index_split_001.html_12)

[*3.1.3.* *Error messages .......................................................................................... 12*](#index_split_001.html_12)

[3.2.](#index_split_001.html_12)

[WSDL ............................................................................................................. 12](#index_split_001.html_12)

[*3.2.1.* *Structure of a WSDL document ................................................................. 15*](#index_split_001.html_15)

[3.2.1.1. types.................................................................................................... 15](#index_split_001.html_15)

[3.2.1.2\. message .............................................................................................. 16](#index_split_001.html_16)

[3.2.1.3\. portType ............................................................................................. 16](#index_split_001.html_16)

[3.2.1.4\. binding ................................................................................................ 16](#index_split_001.html_16)

[3.2.1.5\. service ................................................................................................. 17](#index_split_001.html_17)

[3.3.](#index_split_001.html_17)

[UDDI ............................................................................................................... 17](#index_split_001.html_17)

[*3.3.1.* *UDDI schema ............................................................................................ 18*](#index_split_001.html_18)

[*3.3.2.* *UDDI API .................................................................................................. 19*](#index_split_001.html_19)

[**4.** **IMPLEMENTATING APPLICATIONS BASED ON WEB SERVICES WITH**](#index_split_001.html_21)

[**JAVA / JAVA EE ...................................................................................................................... 22**](#index_split_001.html_21)

[4.1.](#index_split_001.html_22)

[CREATION AND DEPLOYMENT OF A WEB SERVICE USING NETBEANS ........... 22](#index_split_001.html_22)

[*4.1.1.* *Creating a Web service from scratch ........................................................ 22*](#index_split_001.html_22)

[EXERCISE 1 .................................................................................................. 27](#index_split_001.html_27)

[4.1.1.1\. Complex return types ......................................................................... 29](#index_split_001.html_29)

[*4.1.2.* *Creating a Web service from an EJB ........................................................ 31*](#index_split_001.html_31)

[*4.1.3.* *Creating a Web service from a WSDL document ...................................... 33*](#index_split_001.html_33)

[4.2.](#index_split_001.html_34)

[DEVELOPING A CLIENT APPLICATION OF A WEB SERVICE .......................... 34](#index_split_001.html_34)

[*4.2.1.* *Proxy objects ............................................................................................. 34*](#index_split_001.html_34)

[*4.2.2.* *Creating a client application with NetBeans ............................................. 35*](#index_split_001.html_35)

[EXERCISE 2 .................................................................................................. 39](#index_split_001.html_38)

[EXERCISE 3 .................................................................................................. 41](#index_split_001.html_40)

[4.3.](#index_split_001.html_43)

[INVOKING A WEB SERVICE’S METHODS ASYNCHRONOUSLY ......................... 43](#index_split_001.html_43)

[*4.3.1.* *Proxy object configuration ........................................................................ 43*](#index_split_001.html_43)

[*4.3.2.* *Calling methods aysynchronously ............................................................. 45*](#index_split_001.html_45)

[**5.** **USING THE GOOGLE SEARCH WEB SERVICE ......................................... 47**](#index_split_001.html_46)

[5.1.](#index_split_001.html_47)

[USING THE AJAX API ..................................................................................... 47](#index_split_001.html_47)

[*5.1.1.* *Using Google’s search control .................................................................. 47*](#index_split_001.html_47)

[*5.1.2.* *Personalized Search Control ..................................................................... 50*](#index_split_001.html_50)

**1.**

## INTRODUCTION

When we think of a Web application, the first thing that springs to mind is a program that

executes in an application server in response to a request sent from a browser, and whose

ultimate aim is to create an HTML or XHTML page with information obtained from a data

source, that is then delivered back to the client’s browser in the HTTP response.

Despite being an accurate interpretation of what a Web application is, it’s also a

somewhat limited model in that it restricts the only purpose of the response generated by the

application to that of displaying information on screen.

Web services represent a new kind of Web application, whose purpose isn’t to deliver

HTML/XHTML pages to a screen, but to offer a service to other applications connected to the

same network, providing these with a series of functions that carry out common tasks. This

means that the response data generated by the Web service doesn’t adhere to any specific

format or presentation language, but instead to an all-purpose “neutral” language.

This new concept of service-oriented applications that can be consumed by other

programs (or even other services), expands the capabilities of Web-based development to allow

such wide-ranging possibilities from distributed task automation to business applications

integration.

In this unit we will analyze in detail the working principles and purpose of a Web service,

as well as the different technologies and standards in which its architecture is based. From a

practical point of view, we will study how to implement applications based on Web services

using Java / Java EE.

![](index-6_1.jpg)

**2.**

**SOA ARCHITECTURE**

Service-oriented architecture (SOA) is a set of design principles for building applications

by integrating existing software modules (services).

The result is a distributed application that integrates diverse programs, each one with a

different implementation responsible for adding a different feature to the application.

For example, imagine you want to develop a banking application that handles credit

approvals using SOA architecture. We could have a module or service responsible for receiving

the user’s application, another which does a credit check based on their personal details,

another which adds their application to an internal database, etc.

**Figure. 1.**

Essentially, building the application simply entails organizing how to process calls to the

services.

**2.1.**

**SERVICES**

A service can be defined as an application function, packaged as a reusable

autonomous component, that can then be used when building other applications.

In order for a service to be used in building SOA applications, it must comply with the

following requirements:

 Well-defined interfaces: SOA services expose their functionality through

interfaces that describe the operations provided by the service as well as the

information that they should receive and return, hiding the service

implementation details.

 Technology independence: SOA services must be able to be consumed by any

client application, independently of the languages and technologies with which

each are implemented and of the platform on which they are running.

![](index-7_1.jpg)

![](index-7_2.jpg)

 Communication by messages: Clients communicate with the service by

interchanging messages containing information whose format should be

described in the service’s interface.

**2.2.**

**WEB SERVICE**

A Web service is a special type of SOA service deployed on an application server that

client applications connect to through the Web using XML and HTTP standards.

More specifically, a Web service can be defined as a software module that exposes its

functionality on the Web in the form of methods that client applications can call by sending XML

documents in an HTTP request (figure 2).

**Figure. 2.**

The data generated by the Web service, resulting from the execution of its methods, is

then delivered to the client in the HTTP response, also in XML format.

The capability of Web services to communicate with client applications using XML

allows them to be completely independent of each other. This means that a Web service could

be implemented, for example, in Java, whilst the application could be in C or VB. In this case

the XML document, generated by the Java service, could be interpreted correctly by the C/VB

application and vice versa.

**2.3.**

**STRUCTURE OF A WEB SERVICE**

From a technical point of view, a Web service is just a Web application deployed on an

Application Server.

**Figure. 3.**

That application consists of two well-defined layers, as shown in figure 3:

 **Application Logic:** Contains the implementation, in whatever language you

choose, of the methods exposed by the Web service. In the case of a

Java/Java EE application this layer would be implemented by EJBs or standard

classes.

 **XML Adaptor:** Responsible for interpreting XML documents, received in the

HTTP request, using the service’s method call information. Once the

documents have been deciphered and from these the method name and

arguments have been extracted for the service we want to invoke, from this

component the appropriate calls are made to the Application Layer objects.

Therefore, from the data returned by these objects the XML adaptor constructs

the XML response document that will be sent to the client in the body of the

HTTP message.

 This layer would be implemented by Servlets and JSPs in a Java/Java EE

application. Although, to help build them, Java EE includes an API for XML

known as JAX-RPC, with which it is possible to create simple mappings

between Java objects and XML documents and vice versa, facilitating their

manipulation.

![](index-9_1.jpg)

**3.**

**WEB SERVICES ARCHITECTURE STANDARDS**

Apart from XML and HTTP that form the basic standards from which all Web services

architecture is derived, it was necessary for the international community, governed by the W3C

organization, to define additional standards that address the issues that arise when

implementing applications based on this schema. For example, how to structure the XML

documents that are used when interacting with a Web service, or how a service should define

its interface.

These standards are:

 SOAP

 WSDL

 UDDI

**3.1.**

**SOAP**

SOAP, or the **S**imple **O**bject **A**ccess **P**rotocol, is a protocol specification for the transport

of XML messages in computer networks.

SOAP defines the **format that XML documents should have** in order to Exchange

information between Web services and client applications, i.e. it establishes the structure of

both the XML document used to call a service’s methods and the one generated by the service

containing the response (figure 4).

**Figure. 4.**

Although SOAP is independent of the network transport protocols used, the current

specification (SOAP 1.2) concentrates on the use of HTTP in a request/response scenario and

JMS for the asynchronous invocation of the service’s methods.

***3.1.1\. SOAP messages***

The request and response XML documents defined by the SOAP standard are also

known as SOAP messages.

A SOAP message consists of two parts:

 **Header:** Includes optional control information for intermediate applications.

 **Body:** Contains the message itself, i.e. the information to be transmitted from

one application to another.

The structure of an XML SOAP document is as follows:

***<Envelope>***

***<Header>***

***<!-- control information-->***

***</Header>***

***<Body>***

***<!--message-->***

***</body>***

***</Envelope>***

From this we can see that there are three main elements in the SOAP specification,

defined in the namespace:

http://schemas.xmlsoap.org/soap/envelope/

These elements are:

 **Envelope:** Represents the root element of all SOAP documents.

 **Header:** An optional element, which includes header parameters.

 **Body**. The compulsory *body* element contains the contents of the message.

This includes elements specific to the actual application that describe the

information exchanged between the Web service and the client application.

Apart from these application elements, the SOAP specification also allows for a

*fault* element within the *body* that is used for error management.

The following XML is an example of a request SOAP document used to invoke a

function called *login* provided by a Web service, to which user credentials (user and password)

are passed as parameters.

<?xml version="1.0" encoding="UTF-8"?>

**<soapenv:Envelope**

xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"

xmlns:serv="http://www.myservice.com/">

**<soapenv:Header>**

**</soapenv:Header>**

**<soapenv:Body>**

<serv:login>

<serv:user>teacher</q0:user>

<serv:password>admin</q0:password>

</serv:login>

**</soapenv:Body>**

**</soapenv:Envelope>**

As you can see, the *login* element included within the *body* represents the method to be

invoked, within which the values of the method’s parameters appear within their respective

parameter element. All these elements are defined in a specific namespace belonging to the

application.

Once the method has been invoked, the following listing shows a possible SOAP

response XML document generated by the validation Web service:

<?xml version="1.0" encoding="UTF-8"?>

<soapenv:Envelope

xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"

xmlns="http://www.myservice.com/">

<soapenv:Header>

</soapenv:Header>

<soapenv:Body>

<loginResponse>

<result>true</result>

</loginResponse>

</soapenv:Body>

</soapenv:Envelope>

In the above we can see how the *body* structure is made up of a root element, typically

called *service_nameResponse*, which contains a child element holding the return value. Just

like request documents, the elements included in the body of a response are also defined in the

namespace of the application.

***3.1.2\. Types of SOAP messages***

According to how the information is going to be processed by a Web service, there are

two kinds of SOAP message style.

*3.1.2.1\. RPC Messages.*

RPC messages are based on a type of interaction known as **Remote Procedure Call**

**(RPC)**, where the Web service request XML document represents the call to a method or

procedure with its corresponding input parameters, whilst the XML document generated as a

response represents the return value of this method.

This is the simplest and most common type of Web service, where the client and

service communicate synchronously.

*3.1.2.2\. Document Oriented Messages*

The **body** of this type of document can contain one or more child elements structured

according to whatever application they represent.

These XML documents are processed entirely by the Web service, which can involve

calls to the server’s different internal methods. The applications that process this type of

document need to access a schema that defines their structure and syntax.

An example of this type of document could be used in a Web service for processing

purchase orders. In this case the client sends an XML document to the Web service with the

product code to be bought, their bank details and the delivery address. Once the message is

decoded, the Web service begins executing the various tasks, like checking the client’s bank

details, informing the distributor etc. Finally, the Web service sends a response document with

confirmation or rejection of the purchase order.

***3.1.3\. Error messages***

An error may occur when processing a SOAP request, in which case the client

application should be informed by sending a special message known as a SOAP error.

This message contains a <fault> element that describes the characteristics of the error

via a series of child elements, each of which are defined by the SOAP specification.

The following are the child elements of <fault>:

 **faultcode**: The error source. Can have one of the following four values:

o **mustUnderstand**: Indicates that a value flagged as mustUnderstand

in the document’s header wasn’t able to be interpreted by the target

node or some intermediate node.

o **versionmismatch**: The SOAP version specified in the response

message isn’t recognized by some of the nodes.

o **server**: An error occurred in the server whilst processing the message.

o **client**: An error occurred because of errors within the client request

message.

 **faultstring**: Explanatory error message.

 **faultfactor**: Indicates the role that caused the error.

 **detail**: Error information specific to the application. Only present if the error

occurred in the *body*, not in the *header*.

**3.2.**

**WSDL**

WSDL (Web Service Description Language) is a language based on XML that is used to

describe a Web service’s interface. Web service providers use this language to define, with an

XML document with a .wsdl extension, the methods exposed by the service and the data they

receive and return.

A WSDL document contains the following information about a Web service:

 Methods provided by the service.

 The input and output parameters for each method.

 Protocol that should be used to connect to the service and its URL.

The following listing shows a WSDL document for an example Web service called

Operations, which exposes a method that, with *user* and *password*, carries out the process of

verifying user credentials:

<?xml version="1.0" encoding="UTF-8"?>

<wsdl:definitions targetNamespace="http://services"

xmlns:impl="http://services" xmlns:intf="http://services"

xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/"

xmlns:wsdlsoap="http://schemas.xmlsoap.org/wsdl/soap/"

xmlns:wsi="http://ws-i.org/profiles/basic/1.1/xsd"

xmlns:xsd="http://www.w3.org/2001/XMLSchema">

<wsdl:types>

<schema targetNamespace="http://services"

xmlns="http://www.w3.org/2001/XMLSchema"

xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/"

xmlns:xsd="http://www.w3.org/2001/XMLSchema">

<element name="loginResponse">

<complexType>

<sequence>

<element name="loginReturn" type="xsd:boolean"/>

</sequence>

</complexType>

</element>

<element name="login">

<complexType>

<sequence>

<element name="email" nillable="true" type="xsd:string"/>

<element name="password" nillable="true"

type="xsd:string"/>

</sequence>

</complexType>

</element>

</schema>

</wsdl:types>

<wsdl:message name="loginRequest">

<wsdl:part element="intf:login" name="parameters"/>

</wsdl:message>

<wsdl:message name="loginResponse">

<wsdl:part element="intf:loginResponse"

name="parameters"/>

</wsdl:message>

<wsdl:portType name="Operations">

<wsdl:operation name="login">

<wsdl:input message="intf:loginRequest"

name="loginRequest"/>

<wsdl:output message="intf:loginResponse"

name="loginResponse"/>

</wsdl:operation>

</wsdl:portType>

<wsdl:binding name="OperationsSoapBinding"

type="intf:Operations">

<wsaw:UsingAddressing wsdl:required="false"

xmlns:wsaw="http://www.w3.org/

2006/05/addressing/wsdl"/>

<wsdlsoap:binding style="document"

transport="http://schemas.

xmlsoap.org/soap/http"/>

<wsdl:operation name="login">

<wsdlsoap:operation soapAction="login"/>

<wsdl:input name="loginRequest">

<wsdlsoap:body use="literal"/>

</wsdl:input>

<wsdl:output name="loginResponse">

<wsdlsoap:body use="literal"/>

</wsdl:output>

</wsdl:operation>

</wsdl:binding>

<wsdl:service name="OperationsService">

<wsdl:port binding="intf:OperationsSoapBinding"

name="Operations">

<wsdlsoap:address location=

"http://localhost:9080/login_ws/

services/Operations"/>

</wsdl:port>

</wsdl:service>

</wsdl:definitions>

***3.2.1. Structure of a WSDL document***

Every WSDL document is made up of a root element called **definitions**, within which

the different namespaces to be used in the document are declared (figure 5).

Root element

<wsdl:definitions targetNamespace=”http://services”

xmlns:impl=”http://services” xmlns:intf=”http://services”

xmlns:wsdl=”http://schemas.xmlsoap.org/wdsl/”

xmlns:wsdlsoap=”http://schemas.xmlsoap.org/wsdl/soap/”

xmlns:wsi=”http://ws-i.org/profiles/basic/1.1/xsd”

xmlns:xsd=”http://www.w3.org/2001/XMLSchema”>

definition of the namespaces

**Figure. 5.**

To complete the definition of the service, the rest of the child elements included in

*definitions* are *types*, *message*, *portType*, *binding* and *service.*

*3.2.1.1\. types*

This element defines the types of data that will be used by the service, both method

arguments and their return values. When defining a Web service’s data types, an XML Schema

is used:

<wsdl:types>

<schema targetNamespace="http://services"

xmlns="http://www.w3.org/2001/XMLSchema"

xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/"

xmlns:xsd="http://www.w3.org/2001/XMLSchema">

<element name="loginResponse">

<complexType>

<sequence>

<element name="loginReturn" type="xsd:boolean"/>

</sequence>

</complexType>

</element>

<element name="login">

<complexType>

<sequence>

<element name="email" nillable="true" type="xsd:string"/>

<element name="password" nillable="true"

type="xsd:string"/>

</sequence>

</complexType>

</element>

</schema>

</wsdl:types>

*3.2.1.2\. message*

Every ***message*** element defines the information messages that will be exchanged

between the Web service and its clients, messages that are made up of the data defined in

*types*. In fact, every message consists of a child element *part* in which the data types that it contains are specified.

<wsdl:message name="loginRequest">

<wsdl:part element="intf:login" name="parameters"/>

</wsdl:message>

<wsdl:message name="loginResponse">

<wsdl:part element="intf:loginResponse"

name="parameters"/>

</wsdl:message>

*3.2.1.3\. portType*

The ***portType*** element describes the operations exposed by the Web service. In fact,

each operation is defined by the *operation* element and is associated with an input and an

output message:

<wsdl:portType name="Operations">

<wsdl:operation name="login">

<wsdl:input message="intf:loginRequest"

name="loginRequest"/>

<wsdl:output message="intf:loginResponse"

name="loginResponse"/>

</wsdl:operation>

</wsdl:portType>

*3.2.1.4\. binding*

Once the operations that the Web service will perform have been defined, they should

be bound to a specific protocol. This is achieved by the *binding* element, in which we can

specify the type of transport (SOAP or JMS), the network access points for executing a specific

operation and the style (document or RPC):

<wsdl:binding name="OperationsSoapBinding"

type="intf:Operations">

<wsaw:UsingAddressing wsdl:required="false"

xmlns:wsaw="http://www.w3.org/2006/05/addressing/wsdl"/>

<wsdlsoap:binding style="document"

transport="http://schemas.xmlsoap.org/soap/http"/>

<wsdl:operation name="login">

<wsdlsoap:operation soapAction="login"/>

<wsdl:input name="loginRequest">

<wsdlsoap:body use="literal"/>

</wsdl:input>

<wsdl:output name="loginResponse">

<wsdlsoap:body use="literal"/>

</wsdl:output>

</wsdl:operation>

</wsdl:binding>

*3.2.1.5\. service*

Final y, we need to specify the Web service’s address or entry point within the ***service***

element.

Within the *port* child element, the address of each *binding* element is specified. In the

case of SOAP, the *location* attribute within the *address* element contains the actual address.

<wsdl:service name="OperationsService">

<wsdl:port binding="intf:OperationsSoapBinding"

name="Operations">

<wsdlsoap:address location=

"http://localhost:9080/login_ws/

services/Operations"/>

</wsdl:port>

</wsdl:service>

**3.3.**

**UDDI**

The purpose of the UDDI (Universal Description Discovery and Integration project)

specification is to define the standard for publishing and locating a Web service in a services

registry compatible with UDDI.

A UDDI registry is a kind of “*Golden/Yellow Pages*” style database, which stores

information pertinent to published Web services. This means that two types of application can

access this type of registry:

 **Service providers**: Publish the services. UDDI provides mechanisms so that

providers can register their WSDL descriptions and other relevant information

for their Web services.

 **Service consumers**: Use the registry to locate a service and to use it (service

binding). UDDI supports service search mechanisms.

For publishing, editing and searching, SOAP messages are used to access the UDDI

registry.

***3.3.1\. UDDI schema***

Identifies the type of XML data structure that makes up a Web service’s registry entry.

The UDDI XML schema defines four basic data types that describe the information

stored in the UDDI registry. This data is represented by the following elements for all to see:

 **businessEntity**: Describes information about an entity that provides services.

Among this information are the name of the entity, description, list of services

provided, categories and a list of identifiers that can be used for searching

(figure 6).

<businessEntity businessKey=”35AF7F00-1419-11D6-A0DC-

000C0E00ACDD” authorizedName=”0100002CAL” operator=”www-

3.ibm.com/services/uddi”>

<name>Shop</name>

<description xml:lang=”en”>

All kind of product sales

</description>

<contacts>

<contact>

<personName>Jhon Cook</personName>

<phone>918890234</phone>

</contact>

</contacts>

<businessServices>

…

**Figure. 6.**

 **businessService**: Indentifies a Web service provided by an entity. As an

entity can provide more than one Web service, a *businessEntity* can contain

several *businessService* elements, all of which are enclosed within

*businessServices*. Each *businessService* entry contains a description of the

service and, optionally, a list of categories to which the service belongs. The

main child element of *businessService* is *bindingTemplates*, which provides the

technical information for binding to the service..

<businessServices>

< **businessService** serviceKey=”2AB346C0-2282-43B0-756B-0003CC35CC1D”>

<name>Prices</name>

<description xml:lang=”en”>

Calculate product prices

</description>

<categoryBag>

ntis-gov:naic

</categoryBag>

<bindingTemplates>

…

**Figure. 7.**

 **bindingTemplate**: Each *bindingTemplates* is made up of one or several

*bindingTemplate* elements. The *bindingTemplate* element provides two types

of information about the service:

o Technical specifications, like protocols and interchange formats used

to communicate with the service. This information is defined in the

*tModel* structures, which are referenced by the *tModelInstanceDetails*

child element of *bindingTemplate.*

o Access point, which represents the URL at which the Web service can

be invoked. This is specified in the *accessPoint* child element.

<bindingTemplates>

< **bindingTemplate** bindingKey=”4BC7C340-2398-12E6-887C-

0005AC33CC2D”>

Access Point

<description>

to the Service

JAXRPC (SOAP/HTTP) based binding

</description>

<accessPoint>

http://localhost:8080/first-jaxrpc/first

</accessPoint>

<tModelInstanceDetails>

<tModelInstanceInfo tModelKey=”UUID:36E13526-4553-3265-B5F7-

C4B522E75A05” />

</tModelInstanceDetails>

tModel

reference

**Figure. 8.**

 **tModel**: Basically, *tModel* includes the WSDL document address that contains

the service’s technical specifications (figure 9). This information is included in

*overviewURL,* child element of *overviewDoc*. Apart from this, an optional

*description* element and a list of categories ( *categoryBag* element) to which the

service belongs can be included. Each *tModel* element should define a

*tModelKey* attribute that links it to *tModelInstanceDetails*.

<tModel tModelKey="uuid:36E13526-4553-3265-B5F7-C4B522E75A05"

operator="www.ibm.com/services/uddi" authorizedName="0100001QS1">

<name>Price calculation</name>

<description xml:lang="en">Calculate product prices</description>

<overviewDoc>

<description xml:lang="en">Link to WSDL document</description>

<overviewURL>

http://localhost:8080/first-jaxrpc/first?WSDL

</overviewURL>

</overviewDoc>

<categoryBag>

<keyedReference tModelKey="uuid:clacf26d-9672-4404-9d70-39b756e62ab4"

keyName="uddi-org:types" keyValue="wsdlSpec" />

</categoryBag>

</tModel>

**Figure. 9.**

As you can see the *businessEntity*, *businessService* and *tModel* structures can be

classified in a list of categories specified in *categoryBag*, each category to which the structure

belongs is defined in the child element *KeyedReference*.

A category is established based on a particular classification scheme. Several

classification schemes are valid in UDDI. The scheme name to be used should be stored in the

*keyName* attribute, while *keyValue* defines the category to which the structure belongs

according to the classification scheme used.

***3.3.2\. UDDI API***

For applications to interact with a UDDI registry, the latter should expose a series of

functions in the form of SOAP Web services. These Web services allow search operations and

the publication of other Web services within the registry.

Depending on the type of operation carried out, UDDI functions are grouped into two

categories: Inquiry functions and Publication functions. Figure 10 shows the main functions and

the category to which they belong.

**Function**

**Category**

find_business

Inquiry

find_service

Inquiry

find_binding

Inquiry

find_tModel

Inquiry

get_businessDetail

Inquiry

get_serviceDetail

Inquiry

get_bindingDetail

Inquiry

get_tModelDetail

Inquiry

save_business

Publication

save_service

Publication

save_binding

Publication

save_tModel

Publication

delete_business

Publication

delete_service

Publication

delete_binding

Publication

delete_tModel

Publication

**Figure. 10.**

To invoke these functions from an application, you should send SOAP messages with

the appropriate content within the body. For example, to find a company called “Shop” you

would have to include the XML block, shown in figure 11, within the *body*.

<find_business generic=”2.0” xmlns=”urn:uddi-org:api_v2”>

<name>Shop</name>

</find_business>

**Figure. 11.**

The response generated by the registry is also a SOAP document, which includes an

XML block in its *body* with the information found by the search criteria.

For the message in figure 12 the registry would generate a response with a

**businessList** element in which would appear a set of **businessInfo** child elements with each

one of the companies registered that are called Shop.

<businessList generic="2.0" operator="uddi.sourceOperator"

truncated="true" xmlns="urn:uddi-org:api_v2">

<businessInfos>

<businessInfo businessKey="35AF7F00-1419-11D6-A0DC-000C0E00ACDD">

<name>Shop</name>

<servicesInfos>

<serviceInfo serviceKey="2AB346C0-2282-43B0-756B-0003CC35CC1D">

<name>Prices<name>

</serviceInfo>

</serviceInfos>

</businessInfo>

[<businessInfo/>...]

</businessInfos>

</buseinessList>

**Figure. 12.**

![](index-22_1.jpg)

**4.**

**IMPLEMENTATING APPLICATIONS BASED ON**

**WEB SERVICES WITH JAVA / JAVA EE**

As mentioned earlier, the Java EE platform provides an API that facilitates the

construction of applications based on Web services, known as JAX-RPC. However, the

majority of recent development environments contain assistants that greatly simplify the job of

building a Web service, reducing the process to simply that of implementing the application logic

layer.

This is the case for NetBeans. Using this IDE the programmer only needs to take care

of implementing the EJB or class with the required business methods, leaving NetBeans to

dynamically generate both the XML adaptor and the WSDL document that describe the

interface.

**4.1.**

**CREATION AND DEPLOYMENT OF A WEB SERVICE USING NETBEANS**

With the help of NetBeans we can create and deploy a Web service in an application

server. How we go about doing this depends on what we already have or not, giving us three

starting points:

 **Creating a Web service from scratch**: Doesn’t use any existing application

logic nor any type of specification and the Web service is created from scratch.

 **Creating a Web service from an existing EJB**: The application logic is

already implemented in an EJB and we want to expose it as a Web service.

 **Creating a Web service from a WSDL document**. The description of the

methods that the Web service should expose are already defined in a WSDL

interface.

***4.1.1\. Creating a Web service from scratch***

In order to explain the process of creating a Web service with NetBeans, we are going

to develop a simple example Web service called CalcWS, which will expose a method called

factorial, whose function is to calculate the factorial of a number passed as a parameter.

First of all, as all Web services are Web applications, we will create a Web Application

type project that we will call ExampleProyectWS (figure 13)

**Figure. 13.**

![](index-23_1.jpg)

For deployment purposes, we could use either Tomcat or GlassFish as application

servers.

Once the project is created, using the mouse, right-click within the Project window and

choose *New -> Web Service* from the pop-up menu. The dialog box shown in figure 14 will

appear.

**Figure. 14.**

In this dialog box we should enter the Web service name and the package where it will

be located, also choosing whether to create the Web service from scratch (the default) or from

an existing session bean EJB.

Supposing we create a Web service from scratch, on clicking “*Finish”* we will see the

CalcWS class (figure 15) in the NetBeans editor. Here we implement the methods that we want

to expose in the Web service.

package services;

import javax.jws.WebService;

Web Service

class annotation

@WebService()

public class CalcWS {

}

**Figure. 15.**

![](index-24_1.jpg)

![](index-24_2.jpg)

As we can see, the implementation class with its service methods is a normal Java

class, with the difference being that it has to be declared with the **@WebService** annotation as

defined by the javax.jws.WebService package. Using this annotation, the runtime environment

generates everything required so that the class methods are exposed as Web service methods.

Just at the top of the editor window there is a button called “*Design*” that al ows you to

switch to the class Design view (figure 16).

**Figure. 16.**

Using the button “*Add Operation”* we can add the service’s methods graphically,

entering the method names, parameters and return types (figure 17).

**Figure. 17.**

![](index-25_1.jpg)

On clicking the OK button, returning to our class’s source code view, we can see the

declaration of the factorial method, where we can confirm that both the method and the

parameters have been labeled with the respective **@WebMethod** and **@WebParam**

annotations.

Now we complete the implementation of the factorial method, leaving the class looking

as follows:

package services;

import javax.jws.WebMethod;

import javax.jws.WebParam;

import javax.jws.WebService;

@WebService()

public class CalculosWS {

@WebMethod(operationName = "factorial")

public double factorial(@WebParam(name = "num") int num) {

double result=1.0;

for(int i=1;i<=num;i++){

result*=i;

}

return result;

}

}

This is all that is required to implement a Web service with NetBeans. Next we proceed

with the deployment of the Web application in the application server using the *Deploy* pop-up

menu option.

Once the application is deployed, the Web service is ready to be used by client

applications. From NetBeans itself we can test that the Web service works. To do this, inside

the application’s Web service folder, we right-click on our Web service and select “*Test Web*

*Service*” from the pop-up menu (figure 18).

To test the Web service, NetBeans opens an instance of a Web browser and launches

a request from this to the Web service, including the *tester* parameter in the URL. Given this

parameter, the application knows that it’s a request from a browser and generates a test HTML

page that allows you to choose the method to be executed and input its respective parameters

(figure 19).

**Figure. 18.**

![](index-26_1.jpg)

![](index-26_2.jpg)

**Figure. 19.**

On executing the method, the response comes back in the form of a page containing

both the return value and the SOAP messages exchanged between the test page and the Web

service (figure 20).

**Figure. 20.**

**EXERCISE 1**

In this exercise we are going to develop a Web service that validates a user against a

database, a Web service that could be reutilized in many other applications that need to do the

same.

For this exercise we will use any database that includes a table with username and

password fields.

To begin, once we have created the Web application where the Web service will reside,

we wil create a class encompassing al the application’s data access logic. The source code

for this class, which we will call Operations, is shown below:

package model;

import java.sql.*;

public class Operations {

//se establecen unos valores por defecto

//para la conexión con la BD

private String driver="com.mysql.jdbc.Driver";

private String sCon="jdbc:mysql://localhost:3306/books";

private String user="root";

private String pwd="root";

public Operations(){}

public Operations(String driver, String sCon,

String user, String pwd){

this.driver=driver;

this.sCon=sCon;

this.user=user;

this.pwd=pwd;

}

private Connection getConnection() throws SQLException{

Connection cn=null;

try{

Class.forName(driver);

cn=DriverManager.getConnection(sCon, user, pwd);

}

catch(ClassNotFoundException ex){

ex.printStackTrace();

}

catch(SQLException ex){

ex.printStackTrace();

throw ex;

}

return cn;

}

public boolean login(String user, String password){

boolean result=false;

try{

Connection cn;

Statement st;

ResultSet rs;

String sql;

//Clients table contains the user and password

//fields with the user credentials

sql="select user, password from Clients where ";

sql+="user='"+user+"' and password='"+password+"'";

cn= getConnection();

st=cn.createStatement();

rs=st.executeQuery(sql);

//if user exists, next() method will return true

result=rs.next();

}

catch(Exception ex){

ex.printStackTrace();

}

return result;

}

}

From here, following the steps outlined in the previous section, we will create a Web

service called *ValidationsWS*, which exposes a method *login()* that, making use of the

*Operations* class, checks if the user exists in the database. The Web service’s implementation

class source code should look as follows:

package service;

import javax.jws.WebMethod;

import javax.jws.WebParam;

import javax.jws.WebService;

import model.*;

@WebService()

public class ValidationsWS {

private String driver="com.mysql.jdbc.Driver";

private String sCon="jdbc:mysql://localhost:3306/books";

private String buser="root";

private String bpwd="root";

@WebMethod(operationName = "login")

public boolean login(

@WebParam(name = "user") String user,

@WebParam(name = "password") String password) {

Operations op=new Operations(

driver,sCon,buser, bpwd);

if(op.login(user, password)){

return true;

}

else{

return false;

}

}

}

*4.1.1.1\. Complex return types*

Web service methods aren’t limited to just returning primitive types, they can also return

complex types. In the case of a Web service implemented in Java, the method can return

JavaBean type objects, which means, from a SOAP response perspective, an entry containing

a set of XML child elements that represent each of the bean’s fields.

For example, suppose we want to add a new method called *loginClient* to the Web

service in the previous exercise, which, instead of returning a simple Boolean, returns a

complete dataset associated with the client, e.g. user, password and email. The first thing to do

is to implement a class called Client with a default constructor that encapsulates the required

fields. This class could be coded as follows:

package beans;

public class Client {

private String user;

private String password;

private String email;

public Client(){}

public Client(String user, String password, String email) {

this.user = user;

this.password = password;

this.email = email;

}

public String getUser() {

return user;

}

public void setUser(String user) {

this.user = user;

}

public String getPassword() {

return password;

}

public void setPassword(String password) {

this.password = password;

}

public String getEmail() {

return email;

}

public void setEmail(String email) {

this.email = email;

}

}

The next step is to modify the *Operations* class to include the following *loginClient*()

method:

public Client loginClient(String user, String password){

Client c=null;

try{

Connection cn;

Statement st;

ResultSet rs;

String sql;

//Clients table contains the user and password

//fields with the user credentials

sql="select * from Clients where ";

sql+="user='"+user+"' and password='"+password+"'";

cn= getConnection();

st=cn.createStatement();

rs=st.executeQuery(sql);

if(rs.next()){

c=new Client(rs.getString("user"),

rs.getString("password"),

rs.getString("email"));

}

}

catch(Exception ex){

ex.printStackTrace();

}

return c;

}

As for the Web service’s new method, it will look like this:

@WebMethod(operationName = "loginClient")

public Client loginClient(

@WebParam(name = "user") String user,

@WebParam(name = "password") String password) {

Operations op=new Operations(driver, sCon, buser, bpwd);

return op.loginClient(user, password);

}

If we test the Web service, we can check that the SOAP document generated by the

Web service in response to invoking the new method looks like the following listing:

<?xml version="1.0" encoding="UTF-8"?>

<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">

<S:Body>

<ns2:loginClientResponse mlns:ns2="http://service/">

<return>

<email>test1@gmail.com</email>

<password>test1</password>

<user>test1</user>

</return>

</ns2:loginClientResponse>

</S:Body>

</S:Envelope>

We can see from this that the *Client* bean is transformed into an XML document with

three elements.

***4.1.2\. Creating a Web service from an EJB***

If the application logic is implemented in an EJB, we can create a Web service whose

methods redirect calls to the EJB’s methods, therefore exposing the component logic of any

application.

The first thing to do is to open an enterprise project within the IDE in which we already

have defined the EJB module.

Suppose, for example, that we have a simple EJB module called Calculator-ejb, with a

stateless session EJB that exposes two methods, one that calculates the sum of two numbers

and one that multiplies them. The source code for the implementation component class would

be as follows:

package ejbs;

import javax.ejb.Stateless;

![](index-32_1.jpg)

@Stateless

public class Calculator implements CalculatorLocal {

public int add(int x, int y) {

return x+y;

}

public long multiplication(int x, int y) {

return x*y;

}

}

To create the Web service that “wraps” the EJB’s methods, we create a Web

application, either within the same Enterprise application as the EJB module or as an

independent application.

Next, we follow the same steps as in the previous case for creating a Web service,

although when we get to the “*New Web Service*” dialog box, we should choose the *“Create Web*

*Service From Existing Session Bean*” option and click the *“browse”* button to choose the

session EJB (into the “*Enterprise Bean*” field) which implements the application logic (figure 21).

**Figure. 21.**

The code generated for the Web service class will look as follows:

package services;

import ejbs.CalculatorLocal;

import javax.ejb.EJB;

import javax.jws.WebMethod;

import javax.jws.WebParam;

import javax.jws.WebService;

![](index-33_1.jpg)

@WebService()

public class CalculatorWS {

@EJB

private CalculatorLocal ejbRef;

@WebMethod(operationName = "add")

public int add(@WebParam(name = "x")

int x, @WebParam(name = "y")

int y) {

return ejbRef.add(x, y);

}

@WebMethod(operationName = "multiplication")

public long multiplication(@WebParam(name = "x")

int x, @WebParam(name = "y")

int y) {

return ejbRef. multiplication(x, y);

}

}

***4.1.3\. Creating a Web service from a WSDL document***

Although a bottom-up development approach is more common, i.e. create a Web

service from a predefined set of methods, other times, what is know as top-down development

is required.

In top-down development, the starting point is a WSDL inteface that describes the

functionality of the Web service that we want to implement, from which we develop the code for

Web service’s methods and the XML adaptor.

With NetBeans it’s very easy to build the implementation class for a Web service from a

WSDL interface. To do this, choose the “*New -> Web Service From WSDL”* option from the

project pop-up menu, which opens a dialog box (figure 22) in which we should enter, in addition

to the Web service name, the address of the WSDL document that defines its methods.

**Figure. 22.**

![](index-34_1.jpg)

On clicking “*Finish*”, a class declared with the annotation @WebService is generated,

containing the methods that the Web service should expose according to the WSDL document

specifications:

@WebService(serviceName = "OperationsWS",

portName = "Operations",

endpointInterface = "services.Operations",

targetNamespace = "http://services",

wsdlLocation = "WEB-INF/wsdl/

service_from_wsdl/Operations.wsdl")

public class service_from_wsdl {

public boolean login(String email, String password) {

//TODO implement this method

}

}

Obviously, it is the programmer’s responsibility to implement the code for those

methods.

Once completed, the Web service can be deployed normally as in the previous section.

**4.2.**

**DEVELOPING A CLIENT APPLICATION OF A WEB SERVICE**

As we have previously seen for a Web service, in a client application there are also two

separate well-defined modules. On the one hand, we have the application logic, i.e., the part of

the program that performs the application’s specific task using the Web service’s methods. On

the other hand, we have the module that interacts with the service, whose task is to encode and

decode SOAP messages. This module is known as the **proxy** (figure 23).

**Figure. 23.**

***4.2.1\. Proxy objects***

The majority of development environments also provide everything you need so that

you don’t have to worry about implementing the proxy module, so **we only need to**

**concentrate on the application logic**.

![](index-35_1.jpg)

![](index-35_2.jpg)

This is the case for NetBeans that, when the time comes to create a client application of

a Web service, automatically creates a set of classes for creating the proxy from the address of

the WSDL document that describes the Web service.

The **proxy object provides the Java version of the methods exposed by the Web**

**service**. This means that the way the application gains access to the Web service’s methods is

simply via an instance of a normal Java class (figure 24). This class’s methods internally take

care of all the necessary work to connect to the remote Web service, generate the SOAP

invocation messages and process the SOAP response messages.

**Figure. 24.**

***4.2.2\. Creating a client application with NetBeans***

A Java client application of a Web service could be a console application, a servlet or

even another Web service, etc.

In any case, once the client’s type of project has been chosen, to create the proxy class

we click on the “*New -> Web Service Client*” option from the project pop-up menu (figure 25).

If the “*Web Service Client”* option isn’t available in this menu, you can choose “*Other*”

and in the dialog box that follows, within the *Web Service* category, you will also find the same

option.

In the resulting dialog box, it will ask us to specify the WSDL document that describes

the Web service (figure 26). NetBeans will build the proxy using the information provided by

this. Our WSDL document could be published on a server, in which case we would enter the

server’s URL. We could also provide a local copy located in the actual client project, or even be

located in another already loaded project.

**Figure. 25.**

![](index-36_1.jpg)

![](index-36_2.jpg)

Within the same dialog box, we also need to specify the package within the client

application, where we want to store the proxy and helper classes, as well as the invocation

style.

**Figure. 26.**

On clicking “Finish”, the process of generating the proxy begins. If we look at the

projects explorer window, we will see that, inside our client application project, a new folder

called “Generated sources (jax-ws)” has been created, containing the classes and interfaces

that make up the proxy (figure 27).

**Figure. 27.**

The interface whose name conincides with that of the Web service, in our case

CalcWS.java, defines the Java version of the methods exposed by the service. The proxy object

would then be an object of any class that implements this interface, an object which we can

obtain using the <ServiceName>Service.java class (in our example, CalcWSService.java).

Therefore, to get the proxy object, we should follow these steps:

1\. Create a CalcWSService object: Using the class’s constructor without

parameters Utilizando we can create an instance of it:

CalcWSService cservice = new CalcWSService ();

2\. Get the proxy object: We invoke the getCalcWSPort() method on the previous

object that returns an object that implements the CalculosWS interface:

CalcWS proxy = cservice.getCalcWSPort();

We are now at the point where we can invoke the Web service’s methods using the

Java instance referenced by the *proxy* variable.

The following code belongs to a Java console application that requires the user to enter

a number and with this calculates its factorial using the example Web service we already

created:

package example_clientws;

import proxy.*;

import java.util.Scanner;

public class Main {

public static void main(String[] args) {

Scanner sc=new Scanner(System.in);

CalcWSService cservice = new CalcWSService();

CalcWS proxy=cservice.getCalcWSPort();

System.out.println("Type a number ");

int num = sc.nextInt();

System.out.println("Factorial is "+

proxy.factorial(num));

}

}

When the client application of a Web service is a servlet running in a Java EE container,

we use the *@WebServiceRef* annotation from the *javax.xml.ws* package to inject a reference to

the *service* object. All that is required is to specify, in its *wsdlLocation* attribute, the local address of the WSDL document that NetBeans creates in the the client application (normally in

the WDSL folder within the WEB-INF directory):

@WebServiceRef(

wsdlLocation = "WEB-INF\wsdl\localhost_36272\

ExampleProyectWS\CalcWSService.wsdll")

private CalcWSService service;

protected void service(HttpServletRequest request,

HttpServletResponse response)

throws ServletException, IOException {

response.setContentType("text/html;charset=UTF-8");

PrintWriter out = response.getWriter();

try {

CalcWS proxy=service.getCalcWSPort();

:

**EXERCISE 2**

Next we will develop a client application of the validation Web service that we previously

implemented in exercise 1.

We are required to create a Web application with a login page requesting the user’s

credentials. This page will contact a servlet that, making use of the existing Web service we

developed, validates the user and, if the user exists, shows a welcome message; otherwise the

login page will again be displayed.

Here is the code for the login page:

<%@page contentType="text/html" pageEncoding="UTF-8"%>

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"

"http://www.w3.org/TR/html4/loose.dtd">

<html>

<head>

<meta http-equiv="Content-Type" content="text/html;

charset=UTF-8">

<title>JSP Page</title>

</head>

<body>

<center>

<h1>Authentication Form</h1>

<form action="login">

User:<input type="text" name="user"/>

<br/><br/>

Password: <input type="text" name="password"/>

<br/><br/>

<input type="submit" value="Enter"/>

</form>

</center>

</body>

</html>

And the servlet client of the Web service would look like this:

package servlets;

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

import javax.xml.ws.WebServiceRef;

import proxy.ValidationsWSService;

public class Login extends HttpServlet {

@WebServiceRef(wsdlLocation =

"WEB-INF/wsdl/localhost_36272/

Exercise1/ValidationsWSService.wsdl")

private ValidationsWSService service;

protected void service(HttpServletRequest request,

HttpServletResponse response)

throws ServletException, IOException {

response.setContentType("text/html;charset=UTF-8");

PrintWriter out = response.getWriter();

try {

proxy.ValidationsWS port =

service.getValidationsWSPort();

String user = request.getParameter("user");

String password = request.getParameter("password");

boolean result = port.login(user, password);

if(result){

out.println("<html>");

out.println("<body>");

out.println("<h1>Welcome to my page</h1>");

out.println("</body>");

out.println("</html>");

}

else{

response.sendRedirect("login.jsp");

}

}

catch(Exception e){e.printStackTrace();}

}

Among the classes included in the proxy module, we can see the *Client* class, which

comes in handy when invoking the *loginClient*() method of the *ValidationsWS* object. In other

words, **the complex data returned by a Web service is mapped by the client proxy to**

**JavaBean objects**.

**EXERCISE 3**

In this exercise we will develop a Web application, making use of an external Web

service, that checks if the email address, entered by the user in a text field, is valid or not.

We are going to use a free-to-use public Web service belonging to CDYNE Corporation

[(www.cdyne.com)](http://www.cdyne.com/), a Web service that has been implemented in .NET and that we can access from our Java application. The address of the WSDL document that describes its interface is:

[http://ws.cdyne.com/emailverify/Emailvernotestemail.asmx?wsdl](http://ws.cdyne.com/emailverify/Emailvernotestemail.asmx?wsdl)

On the [**http://www.xmethods.org**](http://www.xmethods.org/) Web page we can find information about the different public use Web services offering common functionality.

The email verification Web service exposes four methods, of which we will use

*verifyEmail()*. This method takes an email address and a licence key (being free you can enter

an empty string) and returns a complex data type with the verification results. When creating

the Java proxy, this data type is mapped to a JavaBean of the class **ReturnIndicator**, which

provides the following methods that return information about the verification:

 getResponseText(): Returns a string with information about the verification just

completed.

 getResponseCode(): Returns a code with the result of the verification.

 isGoodEmail(): Indicates if the email is valid or not.

Following the process already discussed, we generate the proxy class from a NetBeans

Web application.

Out of all the clases generated, EmailVerNoTestEmail and EmailVerNoTestEmailSoap

will be the ones we use to create the proxy object.

The Web application consists of a Web page implemented as a JSP with a text field and

a *submit* button asking the user to enter the email address to be checked. The code for this

page is shown below:

<%@page contentType="text/html" pageEncoding="UTF-8"%>

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"

"http://www.w3.org/TR/html4/loose.dtd">

<html>

<head>

<meta http-equiv="Content-Type" content="text/html;

charset=UTF-8">

<title>JSP Page</title>

</head>

<body>

<center>

<form action="Verify" method="post">

Email:<input type="text"

name="email"/><br/>

<input type="submit" value="Verify"/>

</form>

</center>

</body>

</html>

The purpose of the *verify* servlet will be to call the *verifyEmail()* Web service method

and generate a page with the message returned by the verification. The code for the servlet

would be as follows:

package servlets;

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

import proxy.*;

public class Verify extends HttpServlet {

protected void service(HttpServletRequest request,

HttpServletResponse response)

throws ServletException, IOException {

response.setContentType("text/html;charset=UTF-8");

PrintWriter out = response.getWriter();

try {

EmailVerNoTestEmail service=

new EmailVerNoTestEmail();

EmailVerNoTestEmailSoap port =

service.getEmailVerNoTestEmailSoap();

String email = request.getParameter("email");

String licenseKey = "";

ReturnIndicator result =

port.verifyEmail(email, licenseKey);

out.println("<html><body>");

out.println("<h1>Result = "+

result.getResponseText()+"</h1>");

out.println("</body></html>");

}

catch (Exception ex) {ex.printStackTrace();}

finally {

out.close();

}

![](index-43_1.jpg)

}

}

**4.3.**

**INVOKING A WEB SERVICE’S METHODS ASYNCHRONOUSLY**

Natural y, when calling a Web service’s methods via a proxy object, following the steps

already outlined, the program remains locked in the instruction that calls the method, waiting for

the result to be returned by the HTTP response generated by the Web service. This is what is

known as synchronous mode.

However, there are times when we don’t need the value returned by the method to be

able to continue executing the client application. It would be interesting in this case to be able

to invoke the methods asynchronously, which would mean that the program would call the

method and continue executing normally without waiting for it to return a result.

To do this, the client application should provide a callback method that gets executed by

the proxy as soon as the reponse value is received from the Web service.

***4.3.1\. Proxy object configuration***

There are no special steps when developing a Web service in order to asynchronously

invoke it, but you do have to suitably configure the proxy to allow this possibility.

Therefore, once the proxy has been created in the client application, in order to be able

to make asynchronous method calls, we select the reference to our Web service within the

“*Web Service References*” folder and in the pop-up menu click the “Edit Web Service Attributes”

option (figure 28).

**Figure. 28.**

In the dialog box that follows, click the “*WSDL Customization*” tab, open up the *“Port*

*Type Operations”* folder and within the method that we want to invoke asynchronously, check

the “*Enable Asynchronous Client*” option (figure 29).

![](index-44_1.jpg)

![](index-44_2.jpg)

**Figure. 29.**

On clicking “OK”, an informational dialog box wil appear, tel ing us that the proxy

classes will be regenerated.

If we open the *“Web Service References”* folder in the client Project, notice that, apart

from the synchronous version of the method, two new versions have been created allowing

asynchronous calls. One of these methods is for use with a callback function, the one we would

normally use, and the other uses polling, which would periodically poll the proxy checking if the

response has arrived.

**Figure. 30.**

***4.3.2\. Calling methods aysynchronously***

To make an asynchrous call to a Web service, we drag the “Async Callback” element to

the client class within the Web service references, generating the application skeleton shown in

figure 31.

public static void main(String[] args) {

try { //Call Web Service Operation(async.callback)

proxy.CalcWSService service = new proxy.CalcWSService();

object proxy

proxy.CalcWSport = service.getCalcWSPort();

creation

//TODO initialize WS operation arguments here

int num = 0;

javax.xml.ws.AsyncHandler <proxy.FactorialResponse>asyncHandler =

new javax.xml.ws.AsyncHandler<proxy.FactorialResponse>(){

public void handleResponse(javax.xml.ws.Response<proxy.FactorialResponse> response){

try {

//TODO process aynchronous response here

System.out.println("Result = " + response.get());

} catch (Exception ex) {

//TODO handle exception

}

}

anonymous class

that defines the

};

callback method

asynchronous

java.util.concurrent.Future<? extendsjava.lang.Object> result =

call to the method

port.factorialAsync(num,asyncHandler);

while (!result.isDone()) {

//do someting

Checks if there

Thread.sleep(100);

is a result

}

} catch (Exception ex) {

//TODO handle custom exceptions here

}

}

**Figure. 31.**

As you can see from the above code, the callback method *handleResponse()* is defined

in the *javax.xml.ws.AsyncHandler* interface. In this method you should include the instructions

that you want to execute when the result, returned by calling the WS method, is available. This

result can be retrieved through the Response object received in the *handleResponse()* method.

In the code generated by NetBeans, the *handleResponse()* method is implemented in

an anonymous class, whose instance is reference by the *asyncHandler* variable.

On the other hand, we can see that the asynchronous call should be made by the proxy

object’s *factorialAsync()* method:

java.util.concurrent.Future<? extends java.lang.Object> result =

port.factorialAsync(num, asyncHandler);

In addition to the Web service’s own parameters, this method takes the object that

implements the AsyncHandler interface. The call to this method returns a *Future* object that

allows us to check, using the method *isDone()*, if the result has been returned to the client.

For example, the following program calculates the factorial of 7 using the CalcWS Web

service, and while this calculation is in progress, the client program displays a message

“waiting” message every tenth of a second:

package client;

import javax.xml.ws.*;

import proxy.*;

import java.uti.concurrent.*;

public class Test {

public static void main(String[] args) {

try {

CalcWSService service = new CalcWSService();

CalcWS port = service.getCalcWSPort();

int num = 7;

AsyncHandler<FactorialResponse> asyncHandler =

new AsyncHandler<FactorialResponse>() {

public void handleResponse(

Response<FactorialResponse> response) {

try {

System.out.println("Result = "+

response.get().getReturn());

} catch(Exception ex) {}

}

};

Future<? extends Object> result =

port.factorialAsync(num, asyncHandler);

while(!result.isDone()) {

System.out.println("waiting");

Thread.sleep(100);

}

} catch (Exception ex) { }

}

}

**5.**

**USING THE GOOGLE SEARCH WEB SERVICE**

Google has a wide variety of Web services that can be used by developers to integrate

their powerful search engine within their applications.

In 2003 Google published their first Web service, the classic Google search. This Web

service exposes a WSDL interface that defines its functionality, however from 2006 this became

obsolete and from March 2009 Google no longer supports this Web service.

Nowadays, the various Web services provided by Google **should be accessed using**

**special APIs created by Google themselves**, removing the need to rely on proxy objects

created by the many development environments.

These are some of the main APIs available to access Google’s services:

 **AJAX API**: A set of JavaScript objects that provide access to the classic

Google search service from any Web page, also integrating AJAX functionality.

 **Google maps API**: Lets you integrate interactive maps in your Web site.

 **Google Web ToolKit**: Java API for integrating the search service in any

application.

As an example of how to use thse Web services, we are going to analyse the Google

AJAX API with which we can implement a Google search engine within our own Web pages.

**5.1.**

**USING THE AJAX API**

In order to use this service, you need to get a licence key that is available without

charge from the following link:

[http://code.google.com/intl/es/apis/ajaxsearch/signup.html](http://code.google.com/intl/es/apis/ajaxsearch/signup.html)

Once you have this key, it’s very easy to access Google’s JavaScript objects that we

will use to implement our own search page.

***5.1.1\. Using Google’s search control***

The easiest way to implement a search page is by including Google’s own search

control.

The first thing to do is to add the following script to the header of the page that

references Google’s AJAX API loader:

<script type="text/javascript"

src="http://www.google.com/jsapi?key=mykey">

</script>

Here “mykey” represents the key Google supplies us with in URL above. This key can

be used by all the pages in our applications where we want to use the AJAX API.

Next we load the search API using the load method from the google object:

<script type="text/javascript">

google.load("search", "1");

</script>

The loader, which is actually the google object, can load several different APIs. The

search API is obviously loaded by passing the string “search” as the first parameter, whereas if

we wanted to load the Google Maps API we would enter “maps” here.

Next, we will create an instance of SerachControl, the object that represents the Google

search control, i.e. the text field with the search button:

var searchControl = new google.search.SearchControl();

In order to carry out searches, the control needs to know where to search, i.e. whether

it’s a local search, a Web search, searching a newsgroup, etc. To define where you want to

search, you have to instanciate the relevant search objects and add them to the search

collection using the *addSearcher()* method.

For example, to do Web searches, include the following instruction:

searchControl.addSearcher(new google.search.WebSearch());

To finish, all that remains is to indicate where we want to show the Google search

control. This would be a <div> element, where apart from the control, the search results will be

displayed. For example, if the id of the <div> element is *search*, the following instruction should

be included:

searchControl.draw(document.getElementById("search"));

This is all that is required to enhance our page with a search control that, using

Google’s Web service, displays search results on the same page using AJAX technology.

The following code is for the .html page in figure 32, which includes Google’s search

control.

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"

"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">

<head>

<meta http-equiv="content-type" content="text/html;

charset=utf-8"/>

<title>Hello World - Google AJAX Search API Sample</title>

<style type="text/css">

#searchcontrol .gsc-control { width : 400px; }

</style>

<script src="http://www.google.com/jsapi?key=

ABQIAAAAL_EMEkkdOlc7VvLS2ScrhRT2yXp_ZAY8_

ufC3CFXhHIE1NvwkxSNF3RR2EXs8VTzACmPCCglKJVMpQ"

type="text/javascript"></script>

<script type="text/javascript">

//Loads the search

google.load('search', '1.0');

function OnLoad() {

![](index-49_1.jpg)

// Creates search control

var searchControl = new google.search.SearchControl();

searchControl.addSearcher(

new google.search.WebSearch());

//Draws control into page

searchControl.draw(

document.getElementById("search"));

}

</script>

</head>

<body onload="OnLoad();">

<center><h1>Using the Google search control</h1></center>

<br />

<div id="search">Loading</div>

</body>

</html>

**Figure. 32.**

***5.1.2. Personalized Search Control***

If we would like to use our own search control instead of using Google’s, we would need

to include, within the JavaScript code, the same instructions as those performed by the

searches using the API objects.

To carry out Web searches, we need an instance of the **google.search.WebSearch**

class, whose *execute()* method performs the search on the Web using the string provided as a

parameter.

As

*execute()*

is executed asynchronously, we should use WebSearch’s

*setSearchCompleteCallback()* method to specify the callback function where the repsonse will

be processed once its been received by the browser.

Access to the reponse data is acheived using WebSearch’s *results()* method, which

contains an array of results of type **GwebResult**. GwebResult exposes a series of properties

like *title* or *url* that provide us with the title of the page found and its URL, respectively.

The following code is for the page in figure 33, which implements a personalized search

control that uses simple HTML controls to iteract with the user:

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"

"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">

<head>

<meta http-equiv="content-type" content="text/html;

charset=utf-8"/>

<style type="text/css">

#searchcontrol .gsc-control { width : 400px; }

</style>

<script src="http://www.google.com/jsapi?key=

ABQIAAAAL_EMEkkdOlc7VvLS2ScrhRT2yXp_

ZAY8_ufC3CFXhHIE1NvwkxSNF3RR2EXs8VTzACmPCCglKJVMpQ"

type="text/javascript"></script>

<script type="text/javascript">

//Loads the search

google.load('search', '1.0');

var searchControl;

function search() {

searchControl = new google.search.WebSearch();

//process is the callback function

searchControl.setSearchCompleteCallback(this,

process);

searchControl.execute("servers");

}

function process() {

for (var i = 0; i < searchControl.results.length;

i++) {

//For each result, it creates several customized

//elements showing the info of each result

var p = document.createElement('p');

var a = document.createElement('a');

var b = document.createElement('b');

var c = document.createElement('c');

a.href = searchControl.results[i].url;

a.innerHTML = searchControl.results[i].title;

b.innerHTML = "<br>" +

searchControl.results[i].url;

c.innerHTML = "<br>" + searchControl.results[i].

content;

//Builds a *tree of elements* with the results

p.appendChild(a);

p.appendChild(b);

p.appendChild(c);

document.getElementById("result").

appendChild(p);

}

}

</script>

</head>

<body >

<center><h1>Using the Google search control</h1>

Text to search: <input type="text" id="text" /><br />

<input type="button" onclick="search();" value="Search" />

</center>

<br />

<div id="result"></div>

</body>

</html>

![](index-52_1.jpg)

**Figure. 33.**

**SELF-TEST**

1\. A Web service implemented in Java and a client application communicates by:

A. HTTP.

B. RMI

C. FTP.

D. HTML

2\. The SOAP protocol defines:

A. The programming language for implementing a Web service.

B. The methods exposed by the service and the data types interchanged with

client applications.

C. The way in which the client should access the Web service.

D. The format of the Web service’s request and response XML documents.

3\. Choose which of the following statements is INCORRECT

A. It’s possible to develop a client application of a Web service, only having its

WSDL document.

B. A Web service developed in Java can be used from a .NET application.

C. A Web service’s methods can only be accessed synchronously.

D. A UDDI registry entry can be looked up from an application, using the UDDI

API.

4\. Which of the following SOAP document elements is optional?

A. Envelope

B. Header

C. Body

D. Todos son opcionales

5\. The data types handled by a Web service are described in its interface document

using:

A. The native language with which the Web service is implemented.

B. Specific tags from the SOAP specification.

C. UDDI

D. XML Schema

6\. The following code belongs to a servlet that uses a proxy object to invoke the

methods of a Web service called SearchWS:

public class TestServlet extends HttpServlet {

//**missing line of code goes here

private SearchWSservice service;

protected void service(HttpServletRequest request,

HttpServletResponse response)

throws ServletException, IOException {

response.setContentType("text/html;charset=UTF-8");

PrintWriter out = response.getWriter();

try {

SearchWS proxy = service.getSearchWSPort();

//rest of the servlet

Which of the following would successfully complete the code (replacing the

commented missing line)?

A. @WebServiceRef(wsdlLocation = "dirección doc wsdl")

B. @WebService(name= SearchWSservice);

C. new SearchWSService();

D. No code is missing

7\. To access the information returned by a Web service after calling its methods

asynchronously:

A. We should call the proxy object’s *result()* method.

B. The *handleResponse()* method would have to be implemented.

C. The proxy object would put the result in the variable marked with the @Result

annotation.

D. A subclass of WebService should be created.

8\. To make personalized searches from JavaScript code using the Google AJAX API,

we need:

A. A google.search.Searcher object.

B. A google.search.GoogleMap object.

C. A google.search.WebSearch object.

D. A google object.

**Proposed Exercises**

1\. Suppose you have a table of books with the following fields: isbn, title, author,

pages. Create a Web service that exposes a method that, using the book’s ISBN,

returns all its data. Then, create a console client application of the Web service

that asks the user for an ISBN and displays the book’s data returned by the Web

service.

 The method call should be asynchronous, so that when the client application is

waiting for the result, the message “awaiting response” should be displayed every

tenth of a second.

2\. Develop a Web application that, using one of the Web services published on

[www.xmethods.org,](http://www.xmethods.org/) allows its users to send SMS messages to mobile phones.

**Self-Test Answer Key**

1.

A

2.

D

3.

C

4.

B

5.

B

6.

A

7.

B

8.

C