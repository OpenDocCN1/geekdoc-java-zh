![](Images/cover00463.jpeg)

 ADVANCED JAVA

For Beginners

Navi Feroz

About,

Java Server Pages (JSP) is a server side technology for developing dynamic web pages. This is mainly used for implementing presentation layer (GUI Part) of an application. A complete JSP code is more like a HTML with bits of java code in it. JSP is an extension of servlets and every JSP page first gets converted into servlets by JSP container before processing the client’s request.

These tutorials are written for beginners, so even if you have no prior knowledge in this, you won’t face any difficulty understanding these tutorials.

Objectives of our book is to impact basic knowledge in “ADVANCED JAVA” for all the program learners. All the programs are clearly explained with some examples.

This book specially prepared for learners.

Last update:1st feb 2018

Feedback:naviferoz@india.com

© Copyright disclaimer:

The e-book name of” ADVANCED JAVA” are prepared for the student and employees for their developing and pictures are directly provide for understanding purpose under the copyright act.

Content:

[JSP OVERVIEW](#part0000.xhtml_jsp1)

1\. Introduction  to Java Server Pages

2\. Java Server Pages (JSP) Life Cycle

[SCRIPTLETS](#part0000.xhtml_jsp2)

3\. JSP Scriptlets

[ACTION TAGS](#part0000.xhtml_jsp3)

4\. Introduction Action tags

5\. Include action tag

6\. Include action with parameter

7\. Forward action tag

8\. jsp:useBean, jsp:setProperty and jsp:getProperty action tag

[EXPRESSIONS](#part0000.xhtml_JSP4)

9\. Expression Tag

[ DECLARATIONS](#part0000.xhtml_JSP5)

10\. Declarations tag

[JSP IMPLICIT OBJECTS](#part0000.xhtml_JSP6)

11\. JSP Implicit  Objects

12\. OUT Implicit Object

13\. Request Implicit Object

14\. Response Implicit Object

15\. Session Implicit Object

16\. Application Implicit Object

17\. Exception Implicit Object

18\. PageContext Implicit Object

19\. Config implicit object

[EXPRESSION LANGUAGE (EL) IN JSP](#part0000.xhtml_JSP7)

20\. Expression language (EL)

[EXCEPTION HANDLING](#part0000.xhtml_JSP8)

21\. Exception handling in JSP

[CUSTOM TAGS](#part0000.xhtml_JSP9)

22\. Custom tags in JSP

23\. How to access the body of custom tags

[DIRECTIVES](#part0000.xhtml_jsp10)

24\. Page and Taglib directive

25\. Include Directive

26\. Include action with parameters

[JSTL](#part0000.xhtml_jsp11)

27\. JSTL  Core Tags

28\. JSTL Functions

[JSON TUTORIALS](#part0000.xhtml_jsp12)

29\. JSON Tutorials

[SERVLET TUTORIALS](#part0000.xhtml_jsp13)

30\. Servlet Introduction

31\. Servlet API

32\. Servlet Interface

33\. GenericServlet Class

34\. HttpServlet class

35\. How to create and run Servlet in Eclipse IDE

36\. Servlet Life Cycle

37\. Working of Servlet

38\. Welcome-file-list tag in web.xml file of Project

39\. Use load-on-startup tag in web.xml file

40\. ServletRequest Interface

41\. RequestDispatcher methods

42\. ServletConfig Interface

43\. ServletContext Interface

JSP OVERVIEW

Note:

The hyperlink is given below at the some of the topics to go back to their linked headings because some topics are linked to each other to get better scope of reading to their related topics.so don’t get confused during reading.

Introduction to Java Server Pages

JSP is a server side technology that does all the processing at server. It is used for creating dynamic web applications, using java as programming language.

Basically, any html file can be converted to JSP file by just changing the file extension from “.html” to “.jsp”, it would run just fine. What differentiates JSP from HTML is the ability to use java code inside HTML. In JSP, you can embed Java code in HTML using JSP tags. E.g. run the code below, every time you run this, it would display the current time. That is what makes this code dynamic.

<HTML>

<BODY>

Hello JavaBook Readers!

Current time is: <%= new java.util.Date() %>

</BODY>

</HTML>

Your First JSP

Let us start learning JSP with a simple JSP.

<%-- JSP comment --%>

<HTML>

<HEAD>

<TITLE>MESSAGE</TITLE>

</HEAD>

<BODY>

<%out.print("Hello, Sample JSP code");%>

</BODY>

</HTML>

The above JSP generates the following output:

Hello, Sample JSP code.

Explanation of above code

1) The line <%–JSP Comment–%> represents the JSP element called JSP Comment, While adding comments to a JSP page you can use this tag, we will discuss this in detail in coming posts.

Note: JSP Comments must starts with a tag <%– and ends with –%>

2) Head, Title and Body tags are HTML tags – They are HTML tags, frequently used for static web pages. Whatever content they have is delivered to client(Web browser) as such.

3) <%out.print(“ Hello, Sample JSP code ”);%> is a JSP element, which is known as Scriptlet. Scriptlets can contain Java codes. syntax of scriptlet is: <%Executable java code%>. As the code in Scriptlets is java statement, they must end with a semicolon(;). out.print(“ Hello, Sample JSP code ”) is a java statement, which prints“ Hello, Sample JSP code”.

As discussed, JSP is used for creating dynamic webpages. Dynamic webpages are usually a mix of static & dynamic content.

The static content can have text-based formats such as HTML, XML etc and the dynamic content is generated by JSP tags using java code inside HTML.

Servlet Vs JSP

Like JSP, Servlets are also used for generating dynamic webpages. Here is the comparison between them.

The major difference between them is that servlet adds HTML code inside java while JSP adds java code inside HTML. There are few other noticeable points that are as follows:

Servlets –

1.Servlet is a Java program which supports HTML tags too.

2.Generally used for developing business layer(the complex computational code) of an enterprise application.

3.Servlets are created and maintained by Java developers.

JSP –

1.JSP program is a HTML code which supports java statements too.To be more precise, JSP embed java in html using JSP tags.

2.Used for developing  presentation layer of an enterprise application

3.Frequently used for designing websites and used by web developers.

Advantages of JSP

JSP has all the advantages of servlet, like: Better performance than CGI Built in session features,it also inherits the features of java technology like – multithreading, exception handling, Database connectivity,etc.

JSP Enable the separation of content generation from content presentation. Which makes it more flexible.

With the JSP, it is now easy for web designers to show case the information what is needed.

Web Application Programmers can concentrate on how to process/build the information.

Architecture of a JSP Application

Before we start developing web application, we should have a basic idea of architectures. Based on the location where request processing happens (Servlet OR JSP (java server pages)) there are two architectures for JSP. They are – Model1 Architecture & Model2 Architecture.

1\. Model1 Architecture: In this Model, JSP plays a key role and it is responsible for of processing the request made by client. Client (Web browser) make a request, JSP then creates a bean object which then fulfil the request and pass the response to JSP. JSP then sends the response back to client. Unlike Model2 architecture, in this Model most of the processing is done by JSP itself.

![](Images/image00361.jpeg)

2) Model2 Architecture:  In this Model, Servlet plays a major role and it is responsible for processing the client (web browser) request. Presentation part (GUI part) will be handled by JSP and it is done with the help of bean as shown in image below. The servlet acts as controller and in charge of request processing. It creates the bean objects if required by the jsp page and calls the respective jsp page. The jsp handles the presentation part by using the bean object. In this Model, JSP does not do any processing, Servlet creates the bean Object and calls the JSP program as per the request made by client.

![](Images/image00362.jpeg)

Java Server Pages (JSP) Life Cycle

Java Server Pages (JSP) Life Cycle

JSP pages are saved with .jsp extension which lets the server know that this is a JSP page and needs to go through JSP life cycle stages.

In my previous post about JSP introduction, I explained that JSP is not processed as such, they first get converted into Servelts and then the corresponding servlet gets processed by Server.

When client makes a request to Server, it first goes to container. Then container checks whether the servlet class is older than jsp page (To ensure that the JSP file got modified). If this is the case then container does the translation again (converts JSP to Servlet) otherwise it skips the translation phase (i.e. if JSP webpage is not modified then it doesn’t do the translation to improve the performance as this phase takes time and to repeat this step every time is not time feasible).

The steps in the life cycle of JSP page are:

1) Translation

2) Compilation

3) Loading

4) Instantiation

5) Initialization

6) Request Processing

7) Destruction

![](Images/image00363.jpeg)

Let see the Life cycle of JSP in more detail –

1) As stated above whenever container receives request from client, it does translation only when the servlet class is older than JSP page otherwise it skips this phase (reason I explained above).

2) Then the container –

Compiles the corresponding servlet program

Loads the corresponding servlet class

Instantiates the servlet class

Calls the jspInit() method to initialize the servlet instance( Jsp container will do this job only when the instance of servlet file is not running or if it is older than the jsp file).

[code language=”java”]

public void jspInit()

{

//code to intialize Servlet instances

}[/code]

3) A new thread is then gets created, which invokes the_jspService() method, with a request (HttpServletRequest) and response (HttpServletRespnse) objects as parameters -shown below.

[code language=”java”]

void _jspService( HttpServletRequest req, HttpServletResponse res)

{

//code goes here

}[/code]

4) Invokes the jspDestroy() method to destroy the instance of the servlet class. Code will look like below –

[code language=”java”]

public void jspDestory()

{

//code to remove the instances of servlet class

}[/code]

SCRIPTLETS

JSP Scriptlets

We can use java code in JSP using scriptlets. The JSP container moves the scriptlets content into the _jspService() method which is available to the server during processing of the request.

Scriptlets are nothing but java code enclosed within <% and %> tags. JSP container moves the statements enclosed in it to _jspService() method while generating servlet from JSP. The reason of copying this code to service method is: For each client’s request the _jspService() method gets invoked, hence the code inside it executes for every request made by client.

Syntax of Scriptlet:

[code language=”java”]<% Executable java code%>[/code]

JSP to Servlet transition for Scriptlet –

As I stated in my previous tutorials that JSP does not get executed directly, it first gets converted into a Servlet and then Servlet execution happens as normal. Also, I explained in first para that while translation from JSP to servlet, the java code is copied from scriptlet to _jspService() method. Let us see how that happens.

Sample JSP code:

[codelanguage=”html”]

<H3>SampleJSP </H3>

<% myMethod();%>

[/code]

Note:  Semicolon at the end of scriptlet.

Corresponding translated Servlet code for above JSP code:

[code language=”java”]

public void _jspService(HttpServletRequest request,

HttpServletResponse response)

throws ServletException, IOException {

response.setContentType("text/html");

HttpSession session = request.getSession();

JspWriter out = response.getWriter();

out.println("<H2>Sample JSP</H2>");

myMethod();

}[/code]

An example to learn about the Scripting elements:

[code language=”java”]

<%– A jsp example to learn the JSP scripting elements–%>

<%String string1 ="JSP scriptlet";%>

<%!String string2 ="";%>

<html>

<head>

<title> JSP page: Welcome </title>

</head>

<body>

<h1>

<%–This is an Expression statement–%>

Welcome to <%=string1%>

</h1>

<%–sciptlet example–%>

<%if(localstring.equals("JSP scriptlet")){%>

Hi

<%}

else {%>

hello

<%} %>

<%–same thing can be done in this way also–%>

<%if(localstring.equals("JSP scriptlet"))

out.println("Hi"+string2);

else

out.println("hello");

%>

</body>

</html>[/code]

In the above example there are many type of JSP elements present such as Expression, JSP comment, Declaration element etc. We will see each one of them in upcoming JSP tutorials but as of now you can only focus on Scriptlets. The below are the scriptlets statements used in above example –

[code language=”java”]

<%if(localstring.equals("JSP scriptlet"))

out.println("Hi"+string2);

else

out.println("hello");

%>[/code]

The above code is a JSP scriptlet (notice starting <% and ending %> tags). If you analyze above piece of code then you would find that the code inside tags is a pure java code so in order to execute java code in JSP we use scriptlets.

 [code language=”java”]<%String string1 ="JSP scriptlet";%>[/code]

Like above set of statements this statement is a java initialization code which is enclosed within tags.

Apart from above two set of scriptlets there are many other scriptlet tags present in above example (notice if-else control flow logic). To use the if-else control flow statements of java, we have used scriptlet in above example. As this is the main advantage of using scriptlet so let us make it more clear with the help of an example – You must be aware how important are our If – else control statements.

An example to show use of if -else using scriptlets

Suppose there is a variable num and you want to display “hi” on your webpage if it is greater than 5 otherwise you wanna to display a message. Consider the below code for this scenario –

If you wanna to write a code in java for above situation then it would look like this              

[code language=”java”]

if (num > 5)

{

out.println("hi");

}

else

{

out.println("num value should not be less than 6");

}[/code]

To write the similar code in JSP we need to use JSP scriptlets – Code would be like this –

[code language=”html”]

<! DOCTYPE HTML PUBLIC "-//W3C//DTD HTML4.0 translation //EN">

<HTML>

<HEAD>

<TITLE> MY JSP PAGE </TITLE>

</HEAD>

<BODY>

<% if (num > 5) { %>

<H3> hi </H3>

<%} else {%>

<h3> num value should not be less than 6 </h3>

<% } %>

</BODY>

</HTML>

[/code]

Important Point to remember:  Since the code inside it is a java code it must end with a Semicolon(;). Now notice all the statements – you may find that all few scriptlet where we give semicolon in java,needs it here too and ends with a semicolon.

NOTE:

 GO BACK FROM HERE

[Declarations](#part0000.xhtml_DECLARATION)

ACTION TAGS

JSP Actions – Java Server Pages

Directives vs Actions

1.  Directives are used during translation phase while actions are used during request processing phase.
2.  Unlike Directives Actions are re-evaluated each time the page is accessed.
3.  The following are the action elements used in JSP:

1. <jsp:include> Action

Like include page directive this action is also used to insert a JSP file in another file.

<jsp:include> vs include directive:

It has the same difference which I mentioned at the beginning of the article (directive vs action). In <jsp:include> the file is being included during request processing while in case of include directive it has been included at translation phase.

Syntax:

<jsp:include page="page URL"  flush="Boolean Value" />

Here page URL is: the location of the page needs to be included & flush value can be either true or false (Boolean value).

Example:

<html>

<head>

<title>Demo of JSP include Action Tag</title>

</head>

<body>

<h3>JSP page: Demo Include</h3>

<jsp:include page="sample.jsp" flush="false" />

</body>

</html>

Page: Page value is sample.jsp which means this is the page needs to be included in the current file. Just the file name mentioned which shows that the sample.jsp is in the same directory.

Flush:  Its value is false, which means resource buffer has not been flushed out before including to the current page.

JSP include action tag

JSP include action tag – JSP Tutorial

Include action tag is used for including another resource to the current JSP page. The included resource can be a static page in HTML, JSP page or Servlet. We can also pass parameters and their values to the resource which we are including. Below I have shared two examples of <jsp:include>, one which includes a page without passing any parameters and in second example we are passing few parameters to the page which is being included.

Syntax:

1) Include along with parameters.

<jsp:include  page="Relative_URL_Of_Page">

<jsp:param ... />

<jsp:param ... />

<jsp:param ... />

...

<jsp:param ... />

</jsp:include>

2) Include of another resource without sharing parameters.

<jsp:include  page="Relative_URL_of_Page"  />

Relative_URL_of_Page would be the page name if the page resides in the same directory where the current JSP resides.

Example 1: <jsp:include> without parameters

In this example we will use <jsp:include> action tag without parameters. As a result the page will be included in the current JSP page as it is:

index.jsp

<html>

<head>

<title>JSP Include example</title>

</head>

<body>

<b>index.jsp Page</b><br>

<jsp:include  page="Page2.jsp"  />

</body>

</html>

Page2.jsp

<b>Page2.jsp</b><br>

<i> This is the content of Page2.jsp page</i>

Output:

Content of Page2.jsp has been appended in the index.jsp.

![](Images/image00364.jpeg)

Example 2: Use of <jsp:include> along with <jsp:param>

index.jsp

I’m using <jsp:include> action here along with <jsp:param> for passing parameters to the page which we are going to include.

<html>

<head>

<title>JSP Include example with parameters</title>

</head>

<body>

<h2>This is index.jsp Page</h2>

<jsp:include  page="display.jsp">

<jsp:param  name="userid"  value="Chandru"  />

<jsp:param  name="password"  value="Chandru"  />

<jsp:param  name="name"  value="Chandru Babu"  />

<jsp:param  name="age"  value="27"  />

</jsp:include>

</body>

</html>

display.jsp

<html>

<head>

<title>Display Page</title>

</head>

<body>

<h2>Hello this is a display.jsp Page</h2>

UserID: <%=request.getParameter("userid") %><br>

Password is: <%=request.getParameter("password") %><br>

User Name: <%=request.getParameter("name") %><br>

Age: <%=request.getParameter("age") %>

</body>

</html>

Output:

As you can see that the content of display.jsp has been included in index.jsp. Also, the parameters we have passed are displaying correctly in the included page.

![](Images/image00365.jpeg)

JSP include action with parameter example

JSP include action with parameter example

In order to pass the parameters we need to use the <jsp:param> action tag.

Example

In this example we are including a JSP page (file.jsp) to the main JSP page (index.jsp) using <jsp:include> action tag. To pass the parameters from index to file page we are using <jsp:param> action tag. We are passing three parameters firstname, middlename and lastname, for each of these parameters we need to specify the corresponding parameter name and parameter value. The same we can extract at the included page using expression language or expression tag & implicit object.

index.jsp

<html>

<head>

<title>JSP include with parameters example</title>

</head>

<body>

<jsp:include  page="file.jsp"  >

 <jsp:param  name="firstname"  value="Chandru"  />

 <jsp:param  name="middlename"  value="Pratap"  />

 <jsp:param  name="lastname"  value="Prasad"  />

</jsp:include>

</body>

</html>

file.jsp

${param.firstname}<br>

${param.middlename}<br>

${param.lastname}

Output:

![](Images/image00366.jpeg)

As you can see that the included page displayed the parameters values passed from the main page. For displaying the parameters on the file.jsp page, we have used the [expression language (${}).](#part0000.xhtml_EXPLAN) However you can also use the following code which is using the JSP [expression tag](#part0000.xhtml_EXPRESSIONTAG) and [request implicit object.](#part0000.xhtml_REQIMPLICIT)

<%= request.getParameter("firstname")%>

<%= request.getParameter("middlename")%>

<%= request.getParameter("lastname")%>

2. <jsp:forward> Action

<jsp:forward> is used for redirecting the request. When this action is encountered on a JSP page the control gets transferred to the page mentioned in this action.

Syntax:

<jsp:forward page="URL of the another static, JSP OR Servlet page" />

Example:

first.jsp

<html>

<head>

<title>Demo of JSP Forward Action Tag</title>

</head>

<body>

<h3>JSP page: Demo forward</h3>

<jsp:forward page="second.jsp" />

</body>

</html>

Now when JSP engine would execute first.jsp (the above code) then after action tag, the request would be transferred to another JSP page (second.jsp).

Note:  first.jsp and second.jsp should be in the same directory otherwise you have to specify the complete path of second.jsp.

JSP forward action tag

JSP forward action tag – JSP Tutorial

JSP forward action tag is used for forwarding a request to another resource (It can be a JSP, static page such as html or Servlet). Request can be forwarded with or without parameter. In this tutorial we will see examples of <jsp:forward> action tag.

Syntax:

1)  Forwarding along with parameters.

<jsp:forward  page="display.jsp">

<jsp:param ... />

<jsp:param ... />

<jsp:param ... />

...

<jsp:param ... />

</jsp:forward>

2) Forwarding without parameters.

<jsp:forward  page="Relative_URL_of_Page"  />

Relative_URL_of_Page: If page is in the same directory where the main page resides then use page name itself as I did in the below examples.

JSP Forward Example 1 – without passing parameters

In this example we are having two JSP pages – index.jsp and display.jsp. We have used <jsp:forward> action tag in index.jsp for forwarding the request to display.jsp. Here we are not passing any parameters while using the action tag. In the next example we will pass the parameters as well to another resource.

index.jsp

<html>

<head>

<title>JSP forward action tag example</title>

</head>

<body>

<p  align="center">My main JSP page</p>

<jsp:forward  page="display.jsp"  />

</body>

</html>

display.jsp

<html>

<head>

<title>Display Page</title>

</head>

<body>

Hello this is a display.jsp Page

</body>

</html>

Output:

Below is the output of above code. It is basically the content of display.jsp, which clearly shows that index.jsp didn’t display as it forwarded the request to the display.jsp page.

![](Images/image00367.jpeg)

JSP Forward Example 2 – with parameters

Here we are passing the parameters along with forward request. For passing parameters we are using <jsp:param> action tag. In this example we are passing 4 parameters along with forward and later we are displaying them on the forwarded page. In order to fetch the parameters on display.jsp page we are using getParameter method of request implicit object.

index.jsp

<html>

<head>

<title>JSP forward example with parameters</title>

</head>

<body>

<jsp:forward  page="display.jsp">

<jsp:param  name="name"  value="Chandru"  />

<jsp:param  name="site"  value="JavaBook.com"  />

<jsp:param  name="tutorialname"  value="jsp forward action"  />

<jsp:param  name="reqcamefrom"  value="index.jsp"  />

</jsp:forward>

</body>

</html>

display.jsp

<html>

<head>

<title>Display Page</title>

</head>

<body>

<h2>Hello this is a display.jsp Page</h2>

My name is: <%=request.getParameter("name") %><br>

Website: <%=request.getParameter("site") %><br>

Topic: <%=request.getParameter("tutorialname") %><br>

Forward Request came from the page: <%=request.getParameter("reqcamefrom") %>

</body>

</html>

Output:

Above code directly displayed display.jsp page, which is displaying the parameters passed from index.jsp page.

![](Images/image00368.jpeg)

3. <jsp:param> Action

This action is useful for passing the parameters to Other JSP action tags such as JSP include & JSP forward tag. This way new JSP pages can have access to those parameters using request object itself.

Syntax:

<jsp: param name="param_name_here" value="value_of_parameter_here" />

Now considers the same above example –

first.jsp

<html>

<head>

<title>Demo of JSP Param Action Tag</title>

</head>

<body>

<h3>JSP page: Demo Param along with forward</h3>

<jsp:forward page="second.jsp">

    <jsp:param name ="date" value="20-05-2012" />

    <jsp:param name ="time" value="10:15AM" />

    <jsp:param name ="data" value="ABC" />

</jsp:forward>

</body>

</html>

In the above example first.jsp is passing three parameters (data, time & data) to second.jsp and second.jsp can access these parameters using the below code –

Date:<%= request.getParameter("date") %>

Time:<%= request.getParameter("time") %>

My Data:<%= request.getParameter("data") %>

4. <jsp:useBean> Action

This action is useful when you want to use Beans in a JSP page, through this tag you can easily invoke a bean.

Syntax:

<jsp: useBean id="unique_name_to_identify_bean"  class="package_name.class_name" />

Example of <jsp:useBean>, <jsp:setProperty> & <jsp:getProperty>:

Once Bean class is instantiated using above statement, you have to use jsp:setProperty and jsp:getProperty actions to use the bean’s parameters. we will see both.

jsp:useBean, jsp:setProperty and jsp:getProperty Action Tags

jsp:useBean, jsp:setProperty and jsp:getProperty Action Tags

Here we will see how to use a bean class in JSP with the help of jsp:useBean, jsp:setProperty and jsp:getProperty action tags.

Syntax of jsp:useBean:

<jsp: useBean  id="unique_name_to_identify_bean"

class="package_name.class_name"  />

Syntax of jsp:setProperty:

<jsp:setProperty  name="unique_name_to_identify_bean"

property="property_name"  />

Syntax of jsp:getProperty:

<jsp:getProperty  name="unique_name_to_identify_bean"

property="property_name"  />

A complete example of useBean, setProperty and getProperty:

1) We have a bean class Details where we are having three variables username, age and password. In order to use the bean class and it is properties in JSP we have initialized the class like this in the userdetails.jsp page –

<jsp:useBean  id="userinfo"  class="Javabook.com.Details"></jsp:useBean>

We have used useBean action to initialize the class. Our class is in Javabook.com package so we have given a fully qualified name Javabook.com.Details.

2) We have mapped the properties of bean class and JSP using setProperty action tag. We have given ‘*’ in the property field to map the values based on their names because we have used the same property name in bean class and index.jsp JSP page. In the name field we have given the unique identifier which we have defined in useBean tag.

<jsp:setProperty  property="*"  name="userinfo"/>

3) To get the property values we have used getProperty action tag.

<jsp:getProperty  property="propertyname"  name="userinfo"/>

Details.java

package javabook.com;

public  class  Details {

public  Details() {

    }

 private  String username;

 private  int age;

 private  String password;

public  String getUsername() {

return username;

}

public  void setUsername(String username) {

this.username = username;

}

public  int getAge() {

return age;

}

public  void setAge(int age) {

this.age = age;

}

public  String getPassword() {

return password;

}

public  void setPassword(String password) {

this.password = password;

}

}

index.jsp

<html>

<head><title>

useBean, getProperty and setProperty example

</title></head>

<form  action="userdetails.jsp"  method="post">

User Name: <input  type="text"  name="username"><br>

User Password: <input  type="password"  name="password"><br>

User Age: <input  type="text"  name="age"><br>

<input  type="submit"  value="register">

</form>

</html>

userdetails.jsp

<jsp:useBean  id="userinfo"  class="javabook.com.Details"></jsp:useBean>

<jsp:setProperty  property="*"  name="userinfo"/>

You have enterted below details:<br>

<jsp:getProperty  property="username"  name="userinfo"/><br>

<jsp:getProperty  property="password"  name="userinfo"/><br>

<jsp:getProperty  property="age"  name="userinfo"  /><br>

Output:

![](Images/image00369.jpeg)

![](Images/image00370.jpeg)

Note:

Go back from here:

[Expression language (EL) in JSP](#part0000.xhtml_EXPRESSIONLNG)

EXPRESSION

Expressions Tag

Expression tag – Mainly used for display the content on the browser by sending back the result to the client through response object.

JSP Expression Tag – JSP Tutorial

Expression Tag evaluate the expression placed in it, converts the result into String and send the result back to the client through  [response object.](#part0000.xhtml_RESPONSE)  Basically it writes the result to the client (browser).

Syntax:

<%= expression %>

JSP expression tag Examples

Example 1: Expression of values

Here we are simply passing the expression of values inside expression tag.

<html>

 <head>

 <title>JSP expression tag example1</title>

 </head>

 <body>

<%= 2+4*5 %>

 </body>

 </html>

Output:

![expression-tag-example1](Images/image00371.jpeg)

Example 2: Expression of variables

In this example we have initialized few variables and passed the expression of variables in the expression tag for result evaluation.

<html>

<head>

 <title>JSP expression tag example2</title>

</head>

<body>

  <%

 int a=10;

 int b=20;

 int c=30;

  %>

  <%= a+b+c %>

</body>

</html>

Output:

![expression-tag-example2](Images/image00372.jpeg)

Example 3: String and implicit object output

In this example we are setting up an attribute using [application implicit object](#part0000.xhtml_APPLICATION) and then displaying that attribute and a simple string on another JSP page using expression tag.

index.jsp

<html>

<head>

<title> JSP expression tag example3 </title>

</head>

<body>

  <% application.setAttribute("MyName", "Chandru"); %>

 <a  href="display.jsp">Click here for display</a>

</body>

</html>

display.jsp

<html>

<head>

<title>Display Page</title>

</head>

<body>

 <%="This is a String" %><br>

 <%= application.getAttribute("MyName") %>

</body>

</html>

Output:

![](Images/image00373.jpeg)

![](Images/image00374.jpeg)

NOTE:

GO BACK FROM HERE:

[JSP include action with parameter example](#part0000.xhtml_INCLUDEACTION)

[Declarations](#part0000.xhtml_DECLARATION)

DECLARATIONS

Declarations

Declaration tag – Learn how to declare variables and methods in JSP.

JSP Declaration tag – JSP Tutorial

Declaration tag is a block of java code for declaring class wide variables, methods and classes. Whatever placed inside these tags gets initialized during JSP initialization phase and has class scope. JSP container keeps this code outside of the service method (_jspService()) to make them class level variables and methods.

As we know that variables can be initialized using [scriptlet](#part0000.xhtml_SCRIPTLET) too but those declaration being placed inside _jspService() method which doesn’t make them class wide declarations. On the other side, declaration tag can be used for defining class level variables, methods and classes.

Syntax:

<%!  Declaration %>

Example 1: Variables declaration

In this example we have declared two variables inside declaration tag and displayed them on client using [expression tag.](#part0000.xhtml_EXPRESSIONTAG)

<html>

<head>

 <title>Declaration tag Example1</title>

</head>

<body>

<%! String name="Chandru"; %>

<%! int age=27; %>

<%= "Name is: "+ name %><br>

<%= "AGE: "+ age %>

</body>

</html>

Output:

![](Images/image00375.jpeg)

Example 2: Methods declaration

In this example we have declared a method sum using JSP declaration tag.

<html>

<head>

 <title>Methods Declaration</title>

</head>

<body>

  <%!

 int sum(int num1, int num2, int num3){

 return num1+num2+num3;

  }

  %>

<%= "Result is: " + sum(10,40,50) %>

</body>

</html>

Output:

Sum of all three integers gets displayed on the browser.

Result is 100

JSP IMPLICIT OBJECTS

JSP Implicit Objects

JSP Implicit Objects

These objects are created by JSP container while translating the JSP page to Servlet. These objects are present inside service methods so we can directly use them without declaration.

JSP Implicit Objects

These objects are created by JSP Engine during translation phase (while translating JSP to Servlet). They are being created inside service method so we can directly use them within Scriptlet without initializing and declaring them. There are total 9 implicit objects available in JSP.

Implicit Objects and their corresponding classes:

| Out | javax.servlet.jsp.JspWriter |
| request | javax.servlet.http.HttpServletRequest |
| Response | javax.servlet.http.HttpServletResponse |
| Session | javax.servlet.http.HttpSession |
| Application | javax.servlet.ServletContext |
| Exception | javax.servlet.jsp.JspException |
| Page | java.lang.Object |
| pageContext | javax.servlet.jsp.PageContext |
| Config | javax.servlet.ServletConfig |

Note:

Get back from here

[Expression language (EL) in JSP](#part0000.xhtml_EXPRESSIONLNG)

OUT Implicit Object

OUT Implicit Object in JSP with examples

It’s an instance of javax.servlet.jsp.JspWriter. This allows us to access Servlet output stream. The output which needs to be sent to the client (browser) is passed through this object. In simple words out implicit object is used to write content to the client.

Methods of OUT Implicit Object

1) void print()

2) void println()

3) void newLine()

4) void clear()

5) void clearBuffer()

6) void flush()

7) boolean isAutoFlush()

8) int getBufferSize()

9) int getRemaining()

Let us see each of the out’s method in detail –

1.Void print():  This method writes the value which has been passed to it. For e.g. the below statement would display a sentence Out Implicit Object in jSP – JavaBook to the output screen (client browser).

 out.print(“Out  Implicit  Object  in jSP - JavaBook”);

2.Void println():  This method is similar to the print() method, the only difference between print and println is that the println() method adds a new line character at the end. Let’s have a look at the difference with the help of an example.

Print:

out.print(“hi”);

 out.print(" ");

 out.print(“hello”);

Output on browser:  There will not be a new line between the outcomes of all 3 out.print statements.

hi hello

println:

out.println(“hi”);

 out.println(“hello”);

Output on browser:

hi

hello

3.Void newLine():  This method adds a new line to the output. Example –

out.print(“This will write content without a new line”);

 out.newLine();

 out.print(“I’m just an another print statement”);

Output:

This will write content without a new line

I’m just an another print statement

As you know print statement does not add a new line. We have added a new line between two out.print statements using newLine() method.

4.Void clear(): It clears the output buffer without even letting it write the buffer content to the client. This is how it can be called –

out.clear();

5.Void clearBuffer(): This method is similar to the clear() method. The only difference between them is that when we invoke out.clear() on an already flushed buffer it throws an exception, however out.clearBuffer() doesn’t.

6.Void flush() : This method also clears the buffer just like clear() method but it forces it to write the content to the output before flushing it, which means whatever is there in buffer would be written to the client screen before clearing the buffer.

7.Boolean is AutoFlush() : It returns a Boolean value true/false. It is used to check whether the buffer is automatically flushed or not.

8.Int getBufferSize():  This method returns the size of output buffer in bytes.

9.Int getRemaining():  It returns the number of bytes remaining before hitting the buffer overflow condition.

OUT Implicit Object Example

In this example we are using print and println methods of OUT for displaying few message to the client.

index.jsp

<HTML>

<HEAD>

<TITLE> OUT IMPLICIT OBJECT EXAMPLE </TITLE>

</HEAD>

<BODY>

<%

out.print( "print statement " );

out.println( "println" );

out.print("Another print statement");

%>

</BODY>

</HTML>

Output:

printstatement println
Another print statement

Request Implicit Object in JSP with examples

Methods of request Implicit Object

1. GetParameter(String name)  – This method is used to get the value of a request’s parameter. For example at login page user enters user-id and password and once the credentials are verified the login page gets redirected to user information page, then using request.getParameter we can get the value of user-id and password which user has input at the login page.

String  Uid= request.getParameter("user-id");

 String  Pass= request.getParameter("password");

2. GetParameterNames()  – It returns enumeration of all the parameter names associated to the request.

Enumeration e= request.getParameterNames();

3. GetParameterValues(String name)  – It returns the array of parameter values.

String[] allpasswords = request.getParameterValues("password");

4.GetAttribute(Stringname) – Used to get the attribute value.  request.getAttribute(“admin”) would give you the value of attribute admin.

5. GetAttributeNames()  – It is generally used to get the attribute names associated to the current session. It returns the enumeration of attribute names present in session.

Enumerator e = request.getAttributeNames();

6. SetAttribute(String,Object)  – It assigns an object’s value to the attribute. For example I have an attribute password and a String object str which has a value “admin” then calling request.setAttribute(“password”, str) would assign a value admin to the attribute password.

7. RemoveAttribute(String)  – By using this method a attribute can be removed and cannot be used further. For e.g. If you have a statement request.removeAttribute(“userid”) on a JSP page then the userid attribute would be completely removed and request.getAttribute(“userid”) would return NULL if used after the removeAttribute method.

8\. GetCookies() – It returns an array of cookie objects received from the client. This method is mainly used when dealing with cookies in JSP.

9\. GetHeader(String name) – This method is used to get the header information of the request.

10.GetHeaderNames() – Returns enumerator of all header names. Below code snippet would display all the header names associated with the request.

Enumeration e = request.getHeaderNames();

 while (enumeration.hasMoreElements()) {

 String str = (String)e.nextElement();

 out.println(str);

             }

11.GetRequestURI() – This method (request.getRequestURI()) returns the URL of current JSP page.

12.GetMethod() – It returns HTTP request method. request.getMethod(). For example it will return GET for a Get request and POST for a Post Request.

13.GetQueryString() – Used for getting the query string associated to the JSP page URL. It is the string associated to the URL after question mark sign (?).

Request Implicit Object Example

In the below example we are receiving the input from user in index.html page and displaying the same information in userinfo.jsp page using request implicit object.

index.html

<html>

<head>

<title>Enter UserName and Password</title>

</head>

<body>

<form  action="userinfo.jsp">

Enter User Name: <input  type="text"  name="uname"  />  <br><br>

Enter Password: <input  type="text"  name="pass"  />  <br><br>

<input  type="submit"  value="Submit Details"/>

</form>

</body>

</html>

userinfo.jsp

<%@ page import = " java.util.* " %>

<html>

<body>

<%

String username=request.getParameter("uname");

String password=request.getParameter("pass");

out.print("Name: "+username+" Password: "+password);

%>

</body>

</html>

Snapshots of above example

Once you run the above JSP code. It would show you the below screen with two text fields of username and password.

![](Images/image00376.jpeg)

This is the output of userinfo.jsp page. Here we have fetched the id and password which has been entered by the user in login page.

![](Images/image00377.jpeg)

NOTE:

GO BACK FROM HERE:

[JSP include action with parameter example](#part0000.xhtml_INCLUDEACTION)

Response Implicit Object in JSP

Response Implicit Object in JSP with examples

Here we are going to discuss about response implicit object in JSP. It is an instance of javax.servlet.http.HttpServletRequest and mainly used for modifying the response which is being sent to the browser after processing the client’s request.

Methods of response Implicit Object

1) void setContentType(String type)

2) void sendRedirect(String address)

3) void addHeader(String name, String value)

4) void setHeader(String name, String value)

5) boolean containsHeader(String name)

6) void addCookie(Cookie value)

7) void sendError(int status_code, String message)

8) boolean isCommitted()

9) void setStatus(int statuscode)

Let us see each method in detail –

1.Void setContentType(String type) – This method tells browser, the type of response data by setting up the MIME type and character encoding. The information sets by this method helps browser to interpret the response. Example –

response.setContentType("text/html");

    response.setContentType("image/gif");

    response.setContentType("image/png");

    response.setContentType("application/pdf");

2.Void sendRedirect(String address) – It redirects the control to a new JSP page. For e.g. When the browser would detect the below statement, it would be redirected to the javabook.com from the current JSP page.

  response.sendRedirect("http://javabook.com");

3.Void addHeader(String name, String value) – addHeader method adds a header to the response, basically it includes a header name and it’s value. For example – The below statement will include a header “Site” in the response with value “javaBook.com”.

response.addHeader("Site", "JavaBook.com");

4.Void setHeader(String name, String value) – It sets the header value. This method overrides the current value of header with the new value.  Let’s say I’m modifying the value of Header “Site“. The below statement would modify the current value javaBook.com to a new value AA.com

response.setHeader("Site", "AA.com");

5.Boolean containsHeader(String name) – It returns a Boolean value true/false. It basically checks the whether the header is present in the response or not. For example – Above, in the addHeader method example we have added a Site Header in response so the below statement would return true.

response.containsHeader("Site");

6.Void addCookie(Cookie cookie) – This method adds a cookie to the response. The below statements would add 2 Cookies Author and Siteinfo to the response.

response.addCookie(Cookie  Author);

response.addCookie(Cookie  Siteinfo);

7.Void sendError(int status_code, String message) – It is used to send error response with a code and an error message. For example –

  response.sendError(404, "Page not found error");

8.Boolean isCommitted() -It checks whether the Http Response has been sent to the client, if yes then it returns true else it gives false.

<% if(response.isCommited())

       {

           <%--do something --%>

       }else

        {

          <%--do something else --%>

        } %>

9.Void setStatus(int statuscode) – This method is used to set the HTTP status to a given value. For e.g. the below statement would set HTTP response code to 404 (Page not found).

response.setStatus(404);

Response Implicit Object Example

In the below example we are receiving id and password from login page and then we are matching them with hardcoded correct id/pass. If the credentials are correct the sign-in page redirects to success page else it redirects to sign-in fail JSP page.

index.html

<html>

<head>

<title>Login Page</title>

</head>

<body>

<form  action="checkdetails.jsp">

UserId: <input  type="text"  name="id"  />  <br><br>

Password: <input  type="text"  name="pass"  />  <br><br>

<input  type="submit"  value="Sign In!!"/>

</form>

</body>

</html>

This JSP page verifies the input id/pass against hard-coded values.

checkdetails.jsp

<html>

<head><title>Check Credentials</title>

</head>

<body>

<%

String uid=request.getParameter("id");

String password=request.getParameter("pass");

session.setAttribute("session-uid", uid);

if(uid.equals("Chandru") && password.equals("JavaBook"))

{

response.sendRedirect("success.jsp");

}

else

{

response.sendRedirect("failed.jsp");

}

%>

</body>

</html>

This JSP page would execute if id/pass are matched to the hardcoded userid/password.

success.jsp

<html>

<head><title>Success Page</title>

</head>

<body>

<%

String data=(String)session.getAttribute("session-uid");

out.println("Welcome "+ data+"!!");

%>

</body>

</html>

The control will be redirected to this page if the credentials entered by user are wrong.

failed.jsp

<html>

<head><title>Sign-in Failed Page</title>

</head>

<body>

<%

String data2=(String)session.getAttribute("session-uid");

out.println("Hi "+ data2+". Id/Password are wrong. Please try Again.");

%>

</body>

</html>

Output screenshot:

Login page

![](Images/image00378.jpeg)

Success Page: When user Id and Password are correct.

![](Images/image00379.jpeg)

Login with the incorrect detail.

![](Images/image00380.jpeg)

Sign-In fail Page: When Id and Password are wrong.

![](Images/image00381.jpeg)

NOTE:

GET BACK HERE:

[Expressions](#part0000.xhtml_EXPRESSION)

Session Implicit Object

Session Implicit Object in JSP with examples

Session is most frequently used implicit object in JSP. The main usage of it to gain access to all the user’s data till the user session is active.

Methods of session Implicit Object

1.  setAttribute(String, object) –  This method is used to save an object in session by assigning a unique string to the object. Later, the object can be accessed from the session by using the same String till the session is active. setAttribute and getAttribute are the two most frequently used methods while dealing with session in JSP.
2.  getAttribute(String name) – The object stored by setAttribute method is fetched from session using getAttribute method. For example if we need to access userid on every jsp page till the session is active then we should store the user-id in session using setAttribute method and can be accessed using getAttribute method whenever needed.
3.  removeAttribute(String name) – The objects which are stored in session can be removed from session using this method. Pass the unique string identifier as removeAttribute’s method.
4.  getAttributeNames – It returns all the objects stored in session. Basically, it results in an enumeration of objects.
5.  getCreationTime – This method returns the session creation time, the time when session got initiated (became active).
6.  getId – Servlet container assigns a unique string identifier to session while creation of it. getIdmethod returns that unique string identifier.
7.  isNew() – Used to check whether the session is new. It returns Boolean value (true or false). Mostly used to track whether the cookies are enabled on client side. If cookies are disabled the session.isNew() method would always return true.
8.  invalidate() – It kills a session and breaks the association of session with all the stored objects.
9.  getMaxInactiveInterval – Returns session’s maximum inactivate time interval in seconds.
10.  getLastAccessedTime – Generally used to know the last accessed time of a session.

Session Implicit Object Example

The below html page would display a text box along with a submit button. The submit action would transfer the control to session.jsp page.

index.html

<html>

<head>

<title>Welcome Page: Enter your name</title>

</head>

<body>

<form  action="session.jsp">

<input  type="text"  name="inputname">

<input  type="submit"  value="click here!!"><br/>

</form>

</body>

</html>

The session.jsp page displays the name which user has entered in the index page and it stores the the same variable in the session object so that it can be fetched on any page until the session becomes inactive.

session.jsp

<html>

<head>

<title>Passing the input value to a session variable</title>

</head>

<body>

<%

String uname=request.getParameter("inputname");

out.print("Welcome "+ uname);

session.setAttribute("sessname",uname);

%>

<a  href="output.jsp">Check Output Page Here </a>

</body>

</html>

In this page we are fetching the variable’s value from session object and displaying it.

output.jsp

<html>

<head>

<title>Output page: Fetching the value from session</title>

</head>

<body>

<%

String name=(String)session.getAttribute("sessname");

out.print("Hello User: You have entered the name: "+name);

%>

</body>

</html>

Output Screens:

![](Images/image00382.jpeg)

![](Images/image00383.jpeg)

Application Implicit Object

Application Implicit Object in JSP with examples

Application implicit object is an instance of javax.servlet.ServletContext. It is basically used for getting initialization parameters and for sharing the attributes & their values across the entire JSP application, which means any attribute set by application implicit object would be available to all the JSP pages.

Methods:

*   Object getAttribute(String attributeName)
*   void setAttribute(String attributeName, Object object)
*   void removeAttribute(String objectName)
*   Enumeration getAttributeNames()
*   String getInitParameter(String paramname)
*   Enumeration getInitParameterNames()
*   String getRealPath(String value)
*   void log(String message)
*   URL getResource(String value)
*   InputStream getResourceAsStream(String path)
*   String getServerInfo()
*   String getMajorVersion()
*   String getMinorVersion()

1.Object getAttribute(String attributeName): It returns the object stored in a given attribute name. For example the below statement would return the object stored in attribute “MyAttr”.

String s = (String)application.getAttribute("MyAttr");

2.Void setAttribute(String attributeName, Object object): It sets the value of an attribute or in other words it stores an attribute and its value in application context, which is available to use across JSP application. Example –

application.setAttribute(“MyAttribute”, “This  is the value of Attribute”);

The above statement would have stored the attribute and its value. What would be the value of ‘s’ if we use the below statement in any of the JSP page?

String s= (String) application.getAttribute(“MyAttribute”);

String s value would be “This is the value of Attribute” since we have set it using setAttribute method.

3.Void removeAttribute(String objectName): This method is used for removing the given attribute from the application. For e.g. – It would remove the Attribute “MyAttr” from the application. If we try to get the value of a removed attribute using getAttribute method, it would return Null.

application.removeAttribute(“MyAttr”);

4.Enumeration getAttributeNames(): This method returns the enumeration of all the attribute names stored in the application implicit object.

Enumeration e= application.getAttributeNames();

5.String getInitParameter(String paramname): It returns the value of Initialization parameter for a given parameter name. Example –web.xml

 <web-app>

    …

 <context-param>

 <param-name>parameter1</param-name>

 <param-value>ValueOfParameter1</param-value>

 </context-param>

 </web-app>

Suppose above is my web.xml file

 String s=application.getInitParameter(“parameter1”);

The value of s will be “ValueOfParameter1”. Still confused where did it come from? See the param-value tag in web.xml file.

6.Enumeration getInitParameterNames(): It returns the enumeration of all the Initialization parameters.

 Enumeration e= application.getinitParameterNames();

7.String getRealPath(String value): It converts a given path to an absolute path in the file system.

 String abspath = application.getRealPath(“/index.html”);

The value of abspath would be a complete http URL based on the existing file system.

8.Void log(String message): This method writes the given message to the JSP Engine’s (JSP container’s) default log file associated to the application.

    application.log(“This  is error 404  Page  not found”);

The above call would write the message “This is error 404 Page not found” to the default log file.

9.String getServerInfo(): This method returns the name and version of JSP container (JSP Engine).

    application.getServerInfo();

Application Implicit object Example

A JSP page to capture number of hits using application. In this example we are counting the number of hits to a JSP page using application implicit object.

counter.jsp

<%@ page import="java.io.*,java.util.*" %>

<html>

<head>

<title>Application Implicit Object Example</title>

</head>

<body>

<%

 //Comment: This would return null for the first time

 Integer counter= (Integer)application.getAttribute("numberOfVisits");

 if( counter ==null || counter == 0 ){

 //Comment: For the very first Visitor

counter = 1;

 }else{

 //Comment: For Others

counter = counter+ 1;

 }

application.setAttribute("numberOfVisits", counter);

%>

<h3>Total number of hits to this Page is: <%= counter%></h3>

</body>

</html>

Screenshots of output:

Number of hits is 1 for the first time visitor.

![](Images/image00384.jpeg)

Number of hits got increased when I refreshed the page.

![](Images/image00385.jpeg)

NOTE:

GET BACK FROM HERE:

[Expressions](#part0000.xhtml_EXPRESSION)

Exception Implicit Object

Exception Implicit Object in JSP with examples

In this tutorial, we will discuss exception implicit object of JSP. It is an instance of java.lang. Throwable and the frequently used for exception handling in JSP. This object is only available for error pages, which means a JSP page should have isErrorPage to true in order to use exception implicit object. Let’s understand this with the help of below example –

### Exception implicit Object Example

In this example we are taking two integer inputs from user and then we are performing division between them. We have used exception implicit object to handle any kind of exception in the below example.

index.html

<html>

<head>

<title>Enter two Integers for Division</title>

</head>

<body>

<form  action="division.jsp">

Input First Integer:<input  type="text"  name="firstnum"  />

Input Second Integer:<input  type="text"  name="secondnum"  />

<input  type="submit"  value="Get Results"/>

</form>

</body>

</html>

Here we have specified exception.jsp as errorPage which means if any exception occurs in this JSP page, the control will immediately transferred to the exception.jsp JSP page. Note: We have used errorPage attribute of Page Directive to specify the exception handling JSP page (<%@ page errorPage=”exception.jsp” %>).

division.jsp

<%@ page errorPage="exception.jsp" %>

<%

String num1=request.getParameter("firstnum");

String num2=request.getParameter("secondnum");

int v1= Integer.parseInt(num1);

int v2= Integer.parseInt(num2);

int res= v1/v2;

out.print("Output is: "+ res);

%>

In the below JSP page we have set isErrorPage to true which is also an attribute of Page directive, used for making a page eligible for exception handling. Since this page is defined as a exception page in division.jsp, in case of any exception condition this page will be invoked. Here we are displaying the error message to the user using exception implicit object.

exception.jsp

<%@ page isErrorPage="true" %>

Got this Exception: <%= exception %>

Please correct the input data.

Output:

Screen with two input fields for two integer numbers.

![](Images/image00386.jpeg)

Arithmetic Exception message when we have provided the second integer as zero.

![](Images/image00387.jpeg)

This is one of the most frequently used implicit object while building an application in JSP. As an alternative, you can also handle exceptions in JSP by using try catch within JSP scriptlet.

NOTE:

GET BACK FROM HERE:

[JSP Directives](#part0000.xhtml_JSPDEERIVATIVE)

PageContext Implicit Object

PageContext Implicit Object in JSP with examples

It is an instance of javax.servlet.jsp.PageContext. Using this object you can find attribute, get attribute, set attribute and remove attribute at any of the below levels –

1.  JSP Page – Scope: PAGE_CONTEXT
2.  HTTP Request – Scope: REQUEST_CONTEXT
3.  HTTP Session – Scope: SESSION_CONTEXT
4.  Application Level – Scope: APPLICATION_CONTEXT

Methods of pageContext Implicit Object

1.  Object findAttribute (String AttributeName): This method searches for the specified attribute in all four levels in the following order – Page, Request, Session and Application. It returns NULL when no attribute found at any of the level.
2.  Object getAttribute (String AttributeName, int Scope): It looks for an attribute in the specified scope. This method is similar to findAttribute method; the only difference is that findAttribute looks in all the four levels in a sequential order while getAttribute looks in a specified scope. For e.g. – In the below statement the getAttribute method would search for the attribute “JavaBook” in Session scope (or Session level/layer). If it finds the attribute it would assign it to Object obj else it would return Null.

Object obj = pageContext.getAttribute("JavaBook", PageContext.SESSION_CONTEXT);

Similarly the method can be used for other scopes too –

 Object obj = pageContext.getAttribute("JavaBook", PageContext. REQUEST_CONTEXT);

 Object obj = pageContext.getAttribute("JavaBook", PageContext. PAGE_CONTEXT);

 Object obj = pageContext.getAttribute("JavaBook", PageContext. APPLICATION_CONTEXT);

3.  Void removeAttribute(String AttributeName, int Scope): This method is used to remove an attribute from a given scope. For example – The below JSP statement would remove an Attribute “MyAttr” from page scope.

    pageContext.removeAttribute(“MyAttr”, PageContext. PAGE_CONTEXT);

4.  Void setAttribute(String AttributeName, Object AttributeValue, int Scope): It writes an attribute in a given scope. Example – Below statement would store an Attribute “mydata” in application scope with the value “This is my data”.

    pageContext.setAttribute(“mydata”, “This  is  my data”, PageContext. APPLICATION_CONTEXT);

Similarly this would create an attribute named attr1 in Request scope with value “Attr1 value”.

    pageContext.setAttribute(“attr1”, “Attr1 value”, PageContext. REQUEST_CONTEXT);

PageContext Implicit Object Example

index.html

Here we are simply asking user to enter login details.

<html>

<head>

<title> User Login Page – Enter details</title>

</head>

<body>

<form  action="validation.jsp">

Enter User-Id: <input  type="text"  name="uid"><br>

Enter Password: <input  type="text"  name="upass"><br>

<input  type="submit"  value="Login">

</form>

</body>

</html>

validation.jsp

In this page we are storing user’s credentials using pageContext implicit object with the session scope, which means we will be able to access the details till the user’s session is active. We can also store the attribute using other scope parameters such as page, application and request.

<html>

<head>  <title> Validation JSP Page</title>

</head>

<body>

<%

String id=request.getParameter("uid");

String  pass=request.getParameter("upass");

out.println("hello "+id);

pageContext.setAttribute("UName", id, PageContext.SESSION_SCOPE);

pageContext.setAttribute("UPassword", pass, PageContext.SESSION_SCOPE);

%>

<a  href="display.jsp">Click here to see what you have entered </a>

</body>

</html>

display.jsp

In this JSP page we are fetching the stored attributes using getAttribute method. The point to note here is that we have stored the attributes with session scope so we must need to specify scope as session in order to fetch those attribute’s value.

<html>

<head>

<title>Displaying User Details</title>

</head>

<body>

<%

String username= (String) pageContext.getAttribute("UName", PageContext.SESSION_SCOPE);

String userpassword= (String) pageContext.getAttribute("UPassword", PageContext.SESSION_SCOPE);

out.println("Hi "+username);

out.println("Your Password is: "+userpassword);

%>

</body>

</html>

Screenshots of the example’s output:

Login page where we are receiving User-Id and Password from user.

![](Images/image00388.jpeg)

A page with details page link –

![](Images/image00389.jpeg)

User Credentials display page which we have passed from login page to this page through pageContext instance.

![](Images/image00390.jpeg)

Config Implicit Object

Config Implicit Object in JSP with examples

It is an instance of javax.servlet.ServletConfig. Config Implicit object is used for getting configuration information for a particular JSP page. Using application implicit object we can get application-wide initialization parameters, however using Config we can get initialization parameters of an individual servlet mapping.

Methods of Config Implicit Object

1.  String getInitParameter(String paramname) – Same what we discussed in application implicit object tutorial.
2.  Enumeration getInitParameterNames() – Returns enumeration of Initialization parameters.
3.  ServletContext getServletContext() – This method returns a reference to the Servlet context.
4.  String getServletName() – It returns the name of the servlet which we define in the web.xml file inside <servlet-name> tag.

Config Implicit Object Example

web.xml

Let’s say below is my web.xml file. I’m just defining servlet name and servlet mapping in it. Later, I would fetch few details from this file using config implicit object.

<web-app>

<servlet>

<servlet-name>JavaBookServlet</servlet-name>

<jsp-file>/index.jsp</jsp-file>

</servlet>

<servlet-mapping>

<servlet-name>JavaBookServlet</servlet-name>

<url-pattern>/index</url-pattern>

</servlet-mapping>

</web-app>

index.jsp

In this JSP page we are calling getServletName() method of config object for fetching the servlet name from web.xml file.

<html>

<head>  <title> Config Implicit Object</title>

</head>

<body>

<%

String sname=config.getServletName();

out.print("Servlet Name is: "+sname);

%>

</body>

</html>

Output:

This is the output screen for the above JSP page.

![](Images/image00391.jpeg)

EXPRESSION LANGUAGE

Expression language (EL) in JSP

Expression language(EL)  – We can easily access the data of variables, bean components and expressions using Expression language. Must read this tutorial for JSP Java.

Expression language (EL) has been introduced in JSP 2.0\. The main purpose of it to simplify the process of accessing data from [bean](#part0000.xhtml_BEAN) properties and from [implicit objects](#part0000.xhtml_JSPIMPLICITOBBJ). EL includes arithmetic, relational and logical operators too.

Syntax of EL:

${expression}

Whatever present inside braces gets evaluated at runtime and being sent to the output stream.

Example 1: Expression laungage evaluates the expressions

In this example we are evaluating the expressions with the help of EL.

<html>

<head>

 <title>Expression language example1</title>

</head>

<body>

${1<2}

${1+2+3}

</body>

</html>

Output:

![](Images/image00392.jpeg)

Example 2: Value fetch using param variable of expression language

In this example we are prompting user to enter name and roll number. On the other JSP page we are fetching the entered details using param variable of EL.

index.jsp

<html>

<head>

 <title>Expression language example2</title>

</head>

<body>

<form  action="display.jsp">

Student Name: <input  type="text"  name="stuname"  /><br>

Student RollNum:<input  type="text"  name="rollno"  /><br>

<input  type="submit"  value="Submit Details!!"/>

</form>

</body>

</html>

display.jsp

<html>

<head>

<title>Display Page</title>

</head>

<body>

Student name is ${ param.stuname } <br>

Student Roll No is ${ param.rollno }

</body>

</html>

Output:

![](Images/image00393.jpeg)

![](Images/image00394.jpeg)

Example 3: Getting values from application object.

In this example we have set the attributes using application implicit object and on the display page we have got those attributes using applicationScope of Expression language.

index.jsp

<html>

 <head>

 <title>EL example3</title>

 </head>

 <body>

 <%

application.setAttribute("author", "Chandu");

application.setAttribute("Site", "JavaBook.com");

%>

 <a  href="display.jsp">Click</a>

 </body>

 </html>

display.jsp

<html>

 <head>

 <title>Display Page</title>

 </head>

 <body>

${applicationScope.author}<br>

${applicationScope.Site}

 </body>

 </html>

Output:

![](Images/image00395.jpeg)

![](Images/image00396.jpeg)

EL predefined variables:

Similar to implicit objects in JSP we have predefined variables in EL. In the above examples we have used param and applicationScope, they are also the part of these variables.

PageScope: It helps in getting the attribute stored in Page scope.

EL predefined variables:

Similar to implicit objects in JSP we have predefined variables in EL. In the above examples we have used param and applicationScope, they are also the part of these variables.

PageScope: It helps in getting the attribute stored in Page scope.

PageContext: Same as JSP PageContext object.

SessionScope: Fetches attributes from session scope, set by session object.

RequestScope: It used for getting the attributes from request scope. The attribute which are set by the request implicit object.

Param: Similar to ServletRequest.getParameter. Refer Example 2.

ApplicationScope: Used for getting Applicaton level attributes. Same what we see in Example 3.

Header: It helps in getting HTTP request headers as Strings.

HeaderValues: Used for fetching all the HTTP request headers.

InitParam: It links to context initialization parameters.

ParamValues: Same as ServletRequest.getParmeterValues.

Cookie: It maps to Cookie object.

Note:

GO BACK HERE:

[JSP include action with parameter example](#part0000.xhtml_INCLUDEACTION)

[JSTL](#part0000.xhtml_JSTL)

EXCEPTION HANDLING

Exception handling

Exception handling in JSP – A complete tutorial to learn exception handling in the JSP. We have shared two methods to handle exceptions.

Before going through exception handling in JSP, let us understand what is exception and how it is different from errors.

Exception: These are nothing but the abnormal conditions which interrupts the normal flow of execution. Mostly they occur because of the wrong data entered by user. It is must to handle exceptions in order to give meaningful message to the user so that user would be able to understand the issue and take appropriate action.

Error: It can be an issue with the code or a system related issue. We should not handle errors as they are meant to be fixed.

Methods of handling exceptions:

We can handle exceptions using the below two methods.

*   Exception handling using exception implicit object
*   Exception handling using try catch blocks within scriptlets

Exception handling using exception implicit object

In the below example – we have specified the exception handling page using errorPage attribute of Page directive. If any exception occurs in the main JSP page the control will be transferred to the page mentioned in errorPage attribute.

The handler page should have isErrorPage set to true in order to use exception implicit object. That is the reason we have set the isErrorPage true for errorpage.jsp.

index.jsp

<%@ page errorPage="errorpage.jsp" %>

<html>

<head>

 <title>JSP exception handling example</title>

</head>

<body>

<%

 //Declared and initialized two integers

 int num1 = 122;

 int num2 = 0;

 //It should throw Arithmetic Exception

 int div = num1/num2;

%>

</body>

</html>

errorpage.jsp

<%@ page isErrorPage="true" %>

<html>

<head>

 <title>Display the Exception Message here</title>

</head>

<body>

 <h2>errorpage.jsp</h2>

 <i>An exception has occurred in the index.jsp Page.

   Please fix the errors. Below is the error message:</i>

 <b><%= exception %></b>

</body>

</html>

Output:

![](Images/image00397.jpeg)

Exception handling using try catch blocks within scriptlets

We have handled the exception using try catch blocks in the below example. Since try catch blocks are java code so it must be placed inside sciptlet. In the below example I have declared that an array of length 5 and tried to access the 7th element which does not exist. It caused Array Index out of bounds exception.

error.jsp

<html>

 <head>

 <title>Exception handling using try catch blocks</title>

 </head>

 <body>

 <%

 try{

 //I have defined an array of length 5

 int arr[]={1,2,3,4,5};

 //I'm assinging 7th element to int num

 //which doesn't exist

 int num=arr[6];

 out.println("7th element of arr"+num);

 }

 catch (Exception exp){

 out.println("There is something wrong: " + exp);

 }

%>

 </body>

 </html>

Output of example 2:

![](Images/image00398.jpeg)

CUSTOM TAGS

Custom Tags

*   Custom tags in JSP
*   How to access the body of custom tags

JSP Custom tags with example

User-defined tags are known as custom tags. In this tutorial we will see how to create a custom tag and use it in JSP.

To create a custom tag we need three thing:

1) Tag handler class: In this class we specify what our custom tag will do when it is used in a JSP page.
2) TLD file: Tag descriptor file where we will specify our tag name, tag handler class and tag attributes.
3) JSP page: A JSP page where we will be using our custom tag.

Example:
In the below example we are creating a custom tag MyMsg which will display the message “This is my own custom tag” when used in a JSP page.

Tag handler class:

A tag handler class should implement Tag/IterationTag/ BodyTag interface or it can also extend TagSupport/BodyTagSupport/SimpleTagSupport class. All the classes that support custom tags are present inside javax.servlet.jsp.tagext. In the below we are extending the class SimpleTagSupport.

Details.java

package javabook.com;

import javax.servlet.jsp.tagext.*;

import javax.servlet.jsp.*;

import java.io.*;

public  class  Details  extends  SimpleTagSupport {

 public  void doTag() throws  JspException, IOException {

 /*This is just to display a message, when

       * we will use our custom tag. This message

       * would be displayed

       */

 JspWriter  out = getJspContext().getOut();

 out.println("This is my own custom tag");

   }

}

TLD File
This file should present at the location: Project Name/WebContent/WEB-INF/ and it should have a .tld extension.

Note:
<name> tag:custom tag name. In this example we have given it as MyMsg
<tag-class> tag: Fully qualified class name. Our tag handler class Details.java is in package javabook.com so we have given the value as javabook.com.Details.

message.tld

<taglib>

 <tlib-version>1.0</tlib-version>

 <jsp-version>2.0</jsp-version>

 <short-name>My Custom Tag</short-name>

 <tag>

 <name>MyMsg</name>

 <tag-class>Javabook.com.Details</tag-class>

 <body-content>empty</body-content>

 </tag>

</taglib>

Using custom tag in JSP:

Above we have created a custom tag named MyMsg. Here we will be using it.

Note: taglib directive should have the TLD file path in uri field. Above we have created the message.tld file so we have given the path of that file.

Choose any prefix and specify it in taglib directive’s prefix field. Here we have specified it as myprefix.

Custom tag is called like this: <prefix:tagName/>. Our prefix is myprefix and tag name is MyMsg so we have called it as <myprefix:MyMsg/> in the below JSP page.

<%@ taglib prefix="myprefix" uri="WEB-INF/message.tld"%>

<html>

 <head>

 <title>Custom Tags in JSP Example</title>

 </head>

 <body>

 <myprefix:MyMsg/>

 </body>

</html>

Output:

This  is  my own custom tag

How to access body of Custom tags

In this tutorial we will see how to access the body of custom tag. For e.g. If our custom tag is xyz then we would learn to access the content between <prefix: xyz> and </prefix:xyz>

<prefix: xyz>

Body of custom tag: This is what we will access in the below example

</prefix:xyz>

Example:
In this example or custom tag will append a String to its own body and will display the result.

Tag handler class: Details.java

package javabook.com;

import javax.servlet.jsp.tagext.*;

import javax.servlet.jsp.*;

import java.io.*;

public  class  Details  extends  SimpleTagSupport {

 //StringWriter object

 StringWriter sw = new  StringWriter();

 public  void doTag() throws  JspException, IOException

   {

       getJspBody().invoke(sw);

 JspWriter  out = getJspContext().getOut();

 out.println(sw.toString()+"Appended Custom Tag Message");

   }

}

TLDfile: message.tld
Remember to have this file in WEB-INF folder.

<taglib>

<tlib-version>1.0</tlib-version>

<jsp-version>2.0</jsp-version>

<short-name>My Custom Tag: MyMsg</short-name>

<tag>

<name>MyMsg</name>

<tag-class>javabook.com.Details</tag-class>

<body-content>scriptless</body-content>

</tag>

</taglib>

JSP Page: index.jsp

<%@ taglib prefix="myprefix" uri="WEB-INF/message.tld"%>

<html>

<head>

 <title>Accessing Custom Tag Body Example</title>

</head>

<body>

 <myprefix:MyMsg>

 Test String

 </myprefix:MyMsg>

</body>

</html>

Output:

Test  String  Appended  Custom  Tag  Message

JSP DIRECTIVES

JSP Directives

JSP Directives – Page and TagLib

Directives control the processing of an entire JSP page. It gives directions to the server regarding processing of a page.

Syntax of Directives:

<%@ directive name [attribute name=“value” attribute name=“value” ........]%>

There are three types of Directives in JSP:

1) Page Directive

2) Include Directive

3) TagLib Directive

1) Page Directive

There are several attributes, which are used along with Page Directives and these are –

1) import

2) session

3) isErrorPage

4) errorPage

5) ContentType

6) isThreadSafe

7) extends

8) info

9) language

10) autoflush

11) buffer

1. Import:

This attribute is used to import packages. While doing coding you may need to include more than one packages, In such scenarios this page directive’s attribute is very useful as it allows you to mention more than one packages at the same place separated by commas (,). Alternatively you can have multiple instances of page element each one with different package.

Syntax of import attribute –

<%@page  import="value"%>

Here value is package name.

Example of import-  The following is an example of how to import more than one package using import attribute of page directive.

<%@page  import="java.io.*%>

 <%@page  import="java.lang.*%>

 <%--Comment: OR Below  Statement: Both are Same--%>

 <%@page  import="java.io.*, java.lang.*"%>

2. Session:

Generally while building a user interactive JSP application, we make sure to give access to the user to get hold of his/her personal data till the session is active. Consider an example of logging in into your bank account, we can access all of your data till we signout (or session expires). In order to maintain session for a page the session attribute should be true.

This attribute is to handle HTTP sessions for JSP pages. It can have two values: true or false. Default value for session attribute is true, which means if you do not mention this attribute, server may assume that HTTP session is required for this page.

Default value for this attribute: true

Syntax:

<%@ page session="value"%>

Here value is either true OR false.

Examples of session:

<%@ page session="true"%>

The above code would allow a page to have session implicit objects.

<%@ page session="false"%>

If this code is specified in a JSP page, it means session objects will not be available for that page. Hence session cannot be maintained for that page.

3. isErrorPage:

This attribute is used to specify whether the current JSP page can be used as an error page for another JSP page. If value of isErrorPage is true it means that the page can be used for exception handling for another page. Generally this page has error/warning messages OR exception handling codes and being called by another JSP page when there is an exception occurred there.

There is another use of isErrorPage attribute – The [exception implicit object](#part0000.xhtml_exceptionimplicit) can only be available to those pages which has isErrorPage set to true. If the value is false, the page cannot use exception implicit object.

Default value: false

Syntax:

<%@ page isErrorPage="value"%>

Here value is either true OR false.

Example of isErrorPage:

<%@ page isErrorPage="true"%>

This makes a JSP page, a exception handling page.

4. ErrorPage:

As I stated above, when isErrorPage attribute is true for a particular page then it means that the page can be called by another page in case of an exception.  errorPage attribute is used to specify the URL of a JSP page which has isErrorPage attrbute set to true. It  handles the un-handled exceptions in the page.

Syntax:

<%@ page errorPage="value"%>

Here value is a JSP page name which has exception handling code (and isErrorPage set to true).

Example of errorPage:

<%@ page errorPage="ExceptionHandling.jsp"%>

This means if any exception occurs on the JSP page where this code has been placed, the ExceptionHandling.jsp (this page should have isErrorPage true) page needs to be called.

5. ContentType:

This attribute is used to set the content type of a JSP page.

Default value: text/html

Syntax:

<%@ page contentType="value"%>

here value of content type can be anything such as: text/html, text/xml etc.

Example of contentType:

Below code can be used for text/html pages.

<%@ page contentType="text/html"%>

for text/xml based pages:

<%@ page contentType="text/xml"%>

6. isThreadSafe:

Let us understand this with an example. Suppose you have created a JSP page and mentioned isThreadSafe as true, it means that the JSP page supports multithreading (more than one thread can execute the JSP page simultaneously). On the other hand if it is set to false then JSP engine won’t allow multithreading which means only single thread will execute the page code.

Default value for isThreadSafe attribute: true.

Syntax:

<%@ page isThreadSafe="value"%>

Here value can be true OR false.

Example of isThreadSafe:

<%@ page isThreadSafe="false"%>

Only one thread will be responsible for JSP page execution.

7. Buffer:

This attribute is used to specify the buffer size. If you specify this to none during coding then the output would directly written to Response object by JSPWriter. And, if you specify a buffer size then the output first written to buffer then it will be available for response object.

Syntax: 

<%@ page buffer="value"%>

Value is size in kb or none.

Example of buffer:

No buffer for this page:

<%@ page buffer="none"%>

5 kb buffer size for the page, which has below code:

<%@ page buffer="5kb"%>

8. Extends:

Like java, here also this attribute is used to extend(inherit) the class.

Syntax:

<%@ page extends="value"%>

Value is package_name.class_name.

Example of extends:

The below code will inherit the SampleClass from package: mypackage

<%@ page extends="mypackage.SampleClass"%>

9\. Info:

It provides a description to a JSP page. The string specified in info will return when we will call getServletInfo() method.

Syntax:

<%@ page info="value"%>

Here value is Message or Description

Example of info attribute:

<%@ page info="This code is given by Chandru Prasad"%>

10. language:

It specifies the scripting language( underlying language) being used in the page.

Syntax of language:

<%@ page language="value"%>

Value is scripting language here.

Example of language attribute:

<%@ page language="java"%>

11. AutoFlush:

If it is true it means the buffer should be flushed whenever it is full. false will throw an exception when buffer overflows.

Default value: True

Syntax of autoFlush:

<%@ page autoFlush="value"%>

Value can be true or false.

Example of autoFlush attribute:

Buffer will be flushed out when it is full –

<%@ page autoFlush="true"%>

It will throw an exception when buffer is full due to overflow condition

<%@ page autoFlush="true"%>

12. isScriptingEnabled:

It has been dropped and not in use.

13. isELIgnored:

This attribute specify whether expressions will be evaluated or not.

Default value: true

Syntax of isELIgnored:

<%@ page isELIgnored="value"%>

value can be true or false.

Example of is ELIgnored attribute:

Any expression present inside JSP page will not be evaluated –

<%@ page isELIgnored="false"%>

Expression will be evaluated (true is a default value so no need to specify)-

<%@ page isELIgnored="true"%>

Include Directive

2) Include Directive

Include directive is used to copy the content of one JSP page to another. It’s like including the code of one file into another.

Syntax:

<%@include file ="value"%>

Here value is the JSP file name which needs to be included. If the file is in the same directory then just specify the file name otherwise complete URL (or path) needs to be mentioned in the value field.

Note:  It can be used anywhere in the page.

Example:

<%@include file="myJSP.jsp"%>

You can use the above code in your JSP page to copy the content of myJSP.jsp file. However in this case both the JSP files must be in the same directory. If the myJSP.jsp is in the different directory then instead of just file name you would need to specify the complete path in above code.

Must Read:

Include Directive in detail in JSP

Include directive is used for merging external files to the current JSP page during translation phase (The phase where JSP gets converted into the equivalent Servlet).

Why we need to use the include directive? Can’t we simply add the file’s content in the current JSP instead of using the directive?

We can copy the content of external file and paste it in the main JSP,however it would not be a good practice. Let’s understand this with the help of an example – I have 100 external files and 1 main JSP file. If I just copy the content of all files in the main JSP then I have to edit it whenever there is a change in any of the external file, instead we can include all files using directive and edit the particular file whenever needed.

Also, by using include directive you can enhance the code re-usability – Suppose there is a certain code or data which needs to be there in all the JSP pages of your application then you can simply have that code/data in one file and include the file in all the JSP pages.

The above two reasons can be considered as advantages of using include directive.

Syntax:

This is the syntax of include directive in JSP.

<%@ include file="URL of the file" %>

We must need to specify relative URL –

If file is in the same folder where the current JSP page resides then we can just mention the file name else the relative path to the file needs to be specified.

Include Directive Example

index.jsp

<html>

<head>

<title>Main JSP Page</title>

</head>

<body>

<%@ include file="file1.jsp" %>

Main JSP Page: Content between two include directives.

<%@ include file="file2.jsp" %>

</body>

</html>

file1.jsp

<p  align="center">

This is my File1.jsp and I will include it in index.jsp using include directive

</p>

file2.jsp

<p  align="center">

This is File2.jsp

</p>

Output:  The output would look like this when you run the above code. As you can see we have included the content of file1 and file2 in out main JSP page with the help of include directive.

![Include-Directive-example-output](Images/image00399.jpeg)

3) Taglib Directive

This directive basically allows user to use Custom tags in JSP. we shall discuss about Custom tags in detail in coming JSP tutorials. Taglib directive helps you to declare custom tags in JSP page.

Syntax:

<%@taglib uri ="taglibURI" prefix="tag prefix"%>

Where URI is uniform resource locator, which is used to identify the location of custom tag and tag prefix is a string which can identify the custom tag in the location identified by uri.

Example of Targlib:

<%@ taglib uri="http://www.sample.com/mycustomlib" prefix="demotag" %>

<html>

<body>

<demotag:welcome/>

</body>

</html>

As you can see that uri is having the location of custom tag library and prefix is identifying the prefix of custom tag.

Note:  In above example – <demotag: welcome> has a prefix demotag.

JSTL

JSTL functions and Core Tags-JSTL (JSP Standard Tag Lib) Tutorial

JSTL stands for JSP standard tag Library which is a collection of very useful core tags and functions. These tags and functions will help you write JSP code efficiently.

## JSTL Core Tags

Below is the collection of tutorials on JSTL core tags. Each tutorial is explained with the help of screenshots and proper examples. The following line of statement must be present in your JSP in order to use the JSTL core Tags.

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>

1\. <c:out> tag:  It is used for displaying the content on client after escaping XML and HTML markup tags. Main attributes are default and escapeXML.

# JSTL <c:out> Core Tag

<c:out> is a JSTL core tag, which is used for displaying server-side variables and hardcoded values on the browser (client). You may be wondering that a variable’s value and data can be displayed using Expression language(EL)  and out implicit object too then why do we need <c:out> jstl tag? the difference is that the <c:out> tag escapes HTML/XML tags but others don’t, refer the example to understand this.

Tag <c:out> Example

In this example we are displaying a string on the browser, however we are using html tags in the value and we want to see what would be the result and how it is gonna HTML tags.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>c:out Tag Example</title>

</head>

<body>

<c:out value="${'<b>This is a <c:out> example </b>'}"/>

</body>

</html>

Output:
<b>This is a <c:out> example </b>

EscapeXml attribute of <c:out> tag

Let us say I modify the above code like this – I have just added escapeXML attribute in the tag and marked it false. By default the value of escapeXML attribute is true. Since we have marked it as false it would not escape HTML/XML tags and the tags will work.

<c:out value="${'<b>This is a <c:out> example </b>'}" escapeXml="false"/>

Output:

![](Images/image00400.jpeg)

Attribute “default” of <c:out> tag

Above we have seen escapeXML attribute of the <c:out> tag. There is another attribute “default” for this tag, which is used to display the fallback or default value in case the value of the <c:out> tag is null. Here is the example where we are trying to print the value of string str using the tag and since the string str value is null, the tag is printing the value set in default attribute.

<%! String str = null; %>

<c:out  value="${str}"  default="default value of c:out"/>

![](Images/image00401.jpeg)

2\. <c:set> tag:  This tag is useful for setting up a variable value in a specified scope. It basically evaluates an expression and sets the result in given variable.

# JSTL <c:set> Core Tag

<c:set> core JSTL tag is used for assigning a value to an object or variable within a specified scope. Let’s understand this with an example.

Here I’m assigning a string value to a variable name within application scope (it will let me access my variable in any of the JSP page across application). On the other page (display.jsp) I have printed the value on browser using <c:out> tag  and [EL.(expression language)](#part0000.xhtml_EXPRESSIONLNG)

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>Example of c:set tag</title>

</head>

<body>

<c:set  var="name"  scope="application"  value="Chandru Pratap Prasad"/>

<a  href="display.jsp">Display</a>

</body>

</html>

display.jsp

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<c:out  value="${name}"/>

Output:
Below are the screenshots of the above example’s output.

![](Images/image00402.jpeg)

![](Images/image00403.jpeg)

Attributes of <c:set> tag

1) Value: It can be a hardcoded value or an expression. for e.g. below are the allowed variations of <c:set> tag –

The value of the variable myvar would be stored in the object name.

<c:set  var="name"  scope="application"  value="${myvar}"/>

The result of the expression would be stored in the object.

<c:set  var="sum"  scope="application"  value="${1+3+6}"/>

2) Var: It holds the variable/object name.

3) Scope:  It can be request, session, page and application. In the above example we have specified the scope as application, however it can be anything out of the mentioned four. It all depends on the requirements.

3\. <c:remove> tag:  It is used for removing an attribute from a specified scope or from all scopes (page, request, session and application). By default remove from all.

# JSTL <c:remove> Core Tag

<c:remove> tag is used for removing an attribute from a specified scope or from all scopes (page, request, session and application).

Example:

In the below example, first I have set two variables using <c:set> tag and then I have removed one of them using <c:remove> tag. As you can see in the output screenshot – when I tried to display both the variables, for the second attribute the page didn’t get any value and printed the default value using default attribute of <c:out> tag.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>Example of c:remove tag</title>

</head>

<body>

<c:set  var="Site"  scope="session"  value="JavaBook.com"/>

<c:set  var="author"  scope="session"  value="Chandru"/>

<c:remove  var="author"/>

<a  href="display.jsp">check attributes</a>

</body>

</html>

display.jsp

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<c:out  value="${Site}"/><br>

<c:out  value="${author}"  default="Attribute has no value"/>

![](Images/image00404.jpeg)

![](Images/image00405.jpeg)

## Scope attribute of <c:remove> tag

Above we have coded like this

<c:remove  var="author"/>

This above code removes an attribute from all the scopes (page, session, application, request). In order to be specific we must need to specify the scope attribute inside <c:remove>  tag, like I did below – The below JSTL statement will remove the variable var from session scope.

<c:remove  var="author"  scope="session"/>

4.<c: if> tag:  This JSTL core tag is used for testing conditions. There are two other optional attributes for this tag which are var and scope, test is mandatory.

JSTL <c:if> Core Tag

<c:if> is a JSTL core tag which is used for testing conditions. It is more or like a if statement in java which evaluates a condition and executes a block of code if the result is true.

Syntax:

This is the basic syntax of <c:if> core tag. The set of statements enclosed within <c:if> tag gets executed if test=”true”. For using this tag we generally use expression language to evaluate an relational expression. We use EL because it returns boolean value(true/false) after evaluating the condition and we need the boolean value for test attribute.

<c:if  test="${condition}">

...

..

</c:if>

## Example of <c:if> tag

In this example we have defined age variable using <c:set> tag and then we are checking the eligibility of voting by using <c:if> tag.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>JSTL c:if Tag Example</title>

</head>

<body>

<c:set  var="age"  value="26"/>

<c:if  test="${age >= 18}">

 <c:out  value="You are eligible for voting!"/>

</c:if>

<c:if test="${age < 18}">

 <c:out  value="You are not eligible for voting!"/>

</c:if>

</body>

</html>

Output:

![](Images/image00406.jpeg)

## <c:if> attributes

Above we have seen the basic usage of <c:if> where we have used only the test attribute. However there are two other optional attributes for this tag which are var and scope. Using these attributes you can simply store the test results in a variable within a specified scope.

*   var: Variable name in which the test result would be stored.
*   scope: It defines the scope for storing the value. For e.g. if its session the stored var value can be accessed till the session is active.

## An example of var and scope attribute

Storing the test result in variable res in request scope. For printing the value we have given requestScope.res as the variable is stored in request however you can even give variable name(res) alone, it would work fine.

<c:if  test="${17 >= 18}" var="res" scope="request">

</c:if>

<c:out  value="${requestScope.res}"/>

![](Images/image00407.jpeg)

5. <c:choose> tag:  It’s like switch statement in Java.

JSTL <c:choose>, <c:when>, <c:otherwise> Core Tags

In this article we are discussing <c:choose>, <c:when> and <c:otherwise> core tags of JSTL. These tags are used together like switch-case and default statements in java. <c:choose> is the one which acts like switch, <c:when> like case which can be used multiple times inside <c:choose> for evaluating different-2 conditions. <c:otherwise> is similar to default statement which works when all the <c:when> statements holds false.

Syntax:

The basic structure looks like this –

<c:choose>

 <c:when  test="${condition1}">

       //do something if condition1 is true

 </c:when>

 <c:when  test="${condition2}">

        //do something if condition2 is true

 </c:when>

 <c:otherwise>

//Statements which gets executed when all <c:when> tests are false.

 </c:otherwise>

</c:choose>

## Example:

In this example we have three numbers and we are comparing them using these three core tags. Example is pretty simple to understand. Screenshot of output is provided after the example’s code.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>c:choose, c:when and c:otherwise Tag Example</title>

</head>

<body>

<c:set  var="number1"  value="${222}"/>

<c:set  var="number2"  value="${12}"/>

<c:set  var="number3"  value="${10}"/>

<c:choose>

<c:when test="${number1 < number2}">

     ${"number1 is less than number2"}

 </c:when>

<c:when test="${number1 <= number3}">

     ${"number1 is less than equal to number2"}

 </c:when>

 <c:otherwise>

     ${"number1 is largest number!"}

 </c:otherwise>

</c:choose>

</body>

</html>

Output:

![](Images/image00408.jpeg)

6\. <c:when> tag: It’s like case statement in Java.

Note: Read the same full example from 5

7. <c:otherwise> tag:  It works like default attribute in switch-case statements.

Note: Read the same full example from 5

8. <c:catch>tag: This tag is used in exception handling. In this post we have discussed exception handling using <c:catch> core tag.

# JSTL <c:catch> Core Tag

<c:catch> JSTL tag is used in exception handling. Earlier we shared how to do exception handling in JSP – the two ways. Here we are gonna discuss exception handling using <c:catch> core tag.

#### Syntax:

<c:catch  var ="variable_name">

//Set of statements in which exception can occur

</c:catch>

variable_name can be any variable in which exception message would be stored. If there is an exception occurs in the statements enclosed in <c:catch> then this variable contains the exception message. Let us understand this with the help of an example.

#### Example

In this example we are intentionally throwing arithmetic exception by dividing an integer with zero and then we are printing the errormsg variable (which contains the exception message) using Expression language (EL).

Note: If there is no exception in the block of statements in <c:catch> then the variable (in example it’s errormsg) should have null value. That’s the reason we are checking errormsg!=null before printing the variable’s value.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>JSTL c:catch Core Tag Example</title>

</head>

<body>

<%!

int num1=10;

int num2=0; %>

<c:catch  var ="errormsg">

<% int res = num1/num2;

 out.println(res);%>

</c:catch>

<c:if  test = "${errormsg != null}">

 <p>There has been an exception raised in the above

  arithmetic operation. Please fix the error.

  Exception is: ${errormsg}</p>

</c:if>

</body>

</html>

Output:

![](Images/image00409.jpeg)

9. <c:import> tag:  This JSTL core tag is used for importing the content from another file/page to the current JSP page. Attributes – var, URL and scope.

# JSTL <c:import> Core Tag

JSTL <c:import> tag is used for importing the content from another file/page to the current JSP page.

#### Syntax:

<c:import  var="variable_name"  url="relative_url"/>

Here variable_name is a variable which stores the data imported from another url.
relative_url is the address of the file/page which needs to be imported.

#### Attributes of <c:import>

*   url: It’s mandatory attribute and needs to be mentioned always.
*   var: It is an optional attribute if this is not specified then the imported data will be printed on the current page. For e.g. the statement <c:import url=”/file.jsp” /> would print the data of file.jsp on the client (browser).
*   scope: It is also optional. If we are using var attribute then scope can be used along with it to specify the scope of the data stored in the variable.

#### Example:

This is a page which has some data. We will import this page in index.jsp page.

display.jsp

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<c:out  value="Chandru"/>

<c:out  value="JavaBook.com"  />

<c:out  value="This is just a String"  />

index.jsp

Here we are importing the data from display.jsp into a variable mydata and then we are displaying it on browser using <c:out> tag.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title> JSTL c:import Tag Example</title>

</head>

<body>

<c:import  var="mydata"  url="/display.jsp"/>

<c:out  value="${mydata}"/>

</body>

</html>

Output:

Chandru javabook.com This is just a string

10. <c:forEach> tag:  This tag in JSTL is used for executing the same set of statements for a finite number of times.

JSTL <c:forEach> and <c:forTokens> Core Tags

<c:forEach> tag in JSTL is used for executing the same set of statements for a finite number of times. It is similar to the for loop in java. This is basically used when we need to perform (execute) set of statements again and again for a specified number of times.

<c:forTokens> is also used for iteration but it only works with delimiter which means using this tag we can break the input data into multiple parts based on the delimiter. We will understand this with the help of an example in this post.

## <c:forEach> Tag

#### Syntax of <c:forEach>

<c:forEach  var="counter_variable_name"  begin="intial_value"  end="final_limit">

    //Block of statements

</c:forEach>

The below are the three main attributes of <c:forEach> tag.

begin: The initial counter value.
end: The final limit till which the loop will execute.
var: Counter variable name.

#### Example

In this example we are printing value of variable counter in loop using <c:forEach> tag. The loop is starting from value 1 (mentioned in begin attribute) and ending at value 10 (value of end attribute).

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>Example c:forEach tag in JSTL</title>

</head>

<body>

<c:forEach  var="counter"  begin="1"  end="10">

 <c:out  value="${counter}"/>

</c:forEach>

</body>

</html>

Output:

![](Images/image00410.jpeg)

## <c:forTokens> tag

#### Syntax of <c:forEach>

<c:forTokens  items="value(s)"  delims="delimiter"  var="variable_name">

//Set of statements

</c:forTokens>

The below are the three main attributes of <c:forTokens> tag.

items: Set of data value(s).
delims: The delimiter can have any value. It can be a number, string or special character.
var: variable name which stores the sub strings.

#### Example

In this example we are splitting the strings into multiple substrings using delimter dot(‘.’).

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>Example c:forTokens tag in JSTL</title>

</head>

<body>

<c:forTokens  items="www.javabook.com"  delims="."  var="site">

 <c:out  value="${site}"/>

</c:forTokens>

</body>

</html>

Output:

www

javabook

com

11. <c:forTokens> tag: It is used for iteration but it only works with delimiter.

Note:Read the same full example from 10

12.<c:param> tag:  This JSTL tag is mostly used with <c:url> and <c:redirect> tags. It adds parameter and their values to the output of these tags.

# JSTL <c:param> Core Tag

<c:param> JSTL tag is mostly used with <c:url> and <c:redirect> tags. Basically it adds parameter and their values to the output of these tags. In this tutorial we will see how the <c:param> tag can be used with  <c:url> and <c: redirect> tags.

#### Syntax:

<c:param  name="parameter_name"  value="parameter_value"/>

#### Attributes of <c:param> tag

*   name: To specify the name of the parameter.
*   value: To specify the value of the parameter.

#### Example:

In this example we are using <c:param> tag for adding parameters to the resultant URL.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>JSTL c:param Tag Example</title>

</head>

<body>

<c:url  value="/mypage.jsp"  var="completeURL">

 <c:param  name="Id"  value="736"/>

 <c:param  name="user"  value="chandru"/>

</c:url>

${completeURL}

</body>

</html>

Output:

/Javabook/mypage.jsp?Id=736&user=chandru

Example 2: <c:param> use in <c:redirect> tag

Here we are passing parameters along with the redirect url using <c:param> tag and then we are displaying those parameters on the redirected page using param variable of expression language.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>c:param Example2</title>

</head>

<body>

<c:redirect  url="/display.jsp"  >

 <c:param  name="UserId"  value="222"/>

 <c:param  name="UserName"  value="ChandruBabu"/>

</c:redirect>

${completeURL}

</body>

</html>

display.jsp

USER ID IS: ${param.UserId}

USER NAME IS: ${param.UserName}

Output:

USER ID IS: 222 SUER NAME IS:ChandruBabu

13\. <c:url> tag:  It is used for url formatting or url encoding. It converts a relative url into a application context url. Optional attributes var, context and scope.

# JSTL <c:url> Core Tag

<c:url> JSTL tag is used for url formatting or you can say url encoding. This is mainly used when we need to open a JSP page based on the user input or based on the value of a variable. It basically converts a relative url into a application context’s url. It may sound confusing now but follow the given examples in this tutorial and you will be able to grasp it quite easy.

#### Syntax:

Basic syntax looks like this – The attribute “value” is a required attribute for the <c:url> tag

<c:url  value="/file1.jsp"  />

There are three other optional attributes exist for this tag which are as follows –

*   var: Variable name to store the formatted url (resultant url).
*   context: Used for specifying the application (or project name). Don’t get it? We will see this with the help of an example later.
*   scope: The scope in which the var attribute would be stored. It can be request, page, application or session.

Let us understand the use of this tag and attributes with the help of an example –

#### Example 1: value attribute of <c:url>

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title>JSTL c:url Tag Example</title>

</head>

<body>

<c:url  value="/file1.jsp"/>

</body>

</html>

Output: The above code produced below output. 

/JavaBook/file1.jsp

Note: JavaBook is my basics book name (in other words JSP application name).

#### Example 2: var attribute of <c:url> tag

Let’s modify the example 1 like this. We have added a variable myurl in <c:url>. Now the result of <c:url> would be stored in variable myurl.

<c:url  var="myurl"  value="/file1.jsp"/>

${myurl}

Output:

/JavaBook/file1.jsp

#### Example 3: context attribute

By default this tag takes the current application as the context, however we can explicitly specify the context in c url as shown in the below example –

Note: The value of the context should always starts with “/” otherwise you will get the below exception message –
HTTP Status 500 – javax.servlet.ServletException: javax.servlet.jsp.JspTagException: In URL tags, when the “context” attribute is specified, values of both “context” and “url” must start with “/”.

<c:url  var="myurl"  value="/file1.jsp"  context="/MyJSPProject"/>

${myurl}

Output:

/MyJSPProject/file1.jsp

Example 4: Scope attribute

<c:url var="myurl" value="/file1.jsp" context="/MyJSPProject" scope="session"/>

${requestScope.myurl}

Output:  Output screen will be blank as we have stored the myurl in session scope and we are trying to print the value after fetching from requestScope.

Correct usage: This is how it should be coded. Here we have stored in session and fetching from sessionScope so it would work fine.

<c:url  var="myurl"  value="/file1.jsp"  context="/MyJSPProject"  scope="session"/>

${sessionScope.myurl}

Output:

/MyJSPProject/file1.jsp

14.<c:redirect> tag: It is used for redirecting the current page to another URL, provide the relative address in the URL attribute of this tag and the page will be redirected to the url.

# JSTL <c:redirect> Core Tag

<c:redirect> is used for redirecting the current page to another URL.

#### Syntax:

<c:redirect  url="http://www.anydomainhere.com/samplepage.jsp"/>

This is how the <c:redirect> tag looks like. We just need to provide the relative address in the URL attribute of this tag and the page will automatically be redirected the URL provided when it gets loaded.

#### Example

Here we are redirecting the page to a different url based on the value of the variable myurl. If the value is 1 page will be redirected to http://javabook.com and for 2 it will go to http://www.google.com.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<html>

<head>

<title> JSTL c:redirect Tag Example</title>

</head>

<body>

 <c:set  var="myurl"  value="2"  scope="request"/>

  <c:if test="${myurl<1}">

 <c:redirect  url="http://javabook.com"/>

 </c:if>

 <c:if  test="${myurl>1}">

 <c:redirect  url="http://www.google.com"/>

 </c:if>

</body>

</html>

Output: Since the value of the variable myurl is 2 the page gets directed to the http://www.google.com.

JSTL Functions

Following are the tutorial links for useful JSTL functions with examples. Following Taglib directive should be included in the JSP page in order to use the JSTL functions.

<%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>

1\. fn:contains function: This function checks whether the given string is present in the input as sub-string. It does a case sensitive check.

# fn:contains() – JSTL Function

fn:contains() function checks whether the given string is present in the input as sub-string. It does a case sensitive check, which means it considers the case while checking for the sub-string.

#### Syntax:

boolean fn:contains(String inputstring, String checkstring)

The return type of this function is boolean. It returns true when the checkstring is present in inputstring else it returns false. It has two string arguments – first one has input string and second argument has the string which needs to be checked in input string.

#### Example of fn:contains()

In this example we are checking whether the new password contains old password as a sub-string, if it does then we are displaying a message to the user.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:contains example</title>

</head>

<body>

<c:set  var="oldPassword"  value="HelloPass"/>

<c:set  var="newPassword"  value="HelloPassNew"  />

<c:if  test="${fn:contains(newPassword, oldPassword)}">

 <c:out  value="New Password should not contain old password as substring"/>

</c:if>

</body>

</html>

Output:

New Password should not contain old password as substring

2. fn:containsIgnoreCase(): It does a case insensitive check to see whether the provided string is a sub-string of input.

# fn:containsIgnoreCase() – JSTL Function

In this post we are going to see fn:containsIgnoreCase() function which does a case insensitive check to see whether the provided string is a sub-string of input or not.

#### Syntax:

boolean fn:containsIgnoreCase(String input, String checkstring)

The return type of this function is boolean. Like fn:contains() function it also receives two string arguments and it checks whether the second string is present in the first string(first argument). It doesn’t consider the case during evaluation.

#### Example of fn:containsIgnoreCase()

In this example we are having two strings – string1 & string2\. We are checking whether the string2 is present in string1\. If the result is true then we are displaying a message.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:containsIgnoreCase() example</title>

</head>

<body>

<c:set  var="string1"  value="Hi This is CHANDRU from JavaBook.com"/>

<c:set  var="string2"  value="chandru"  />

<c:if  test="${fn:containsIgnoreCase(string1, string2)}">

 <c:out  value="Case Insensitive Check: String1 contains string2"/>

</c:if>

</body>

</html>

Output:

Case Insensitive Check:String1 contains string2

3. fn:indexOf():  It is used for finding out the start position of a string in the provided string. Function returns -1 when string is not found in the input.

# fn:indexOf() – JSTL Function

fn:indexOf() function is used for finding out the start position (index) of a string in the provided string.

#### Syntax:

int indexOf(String,  String )

The return type of this function is int. It returns the starting position (or index) of the second string (second argument of the function) in the first string (first argument of the function).

Points to Note:

*   The function returns -1 when the string is not found in the input string.
*   Function is case sensitive. It treats uppercase and lowercase character of same alphabet as different.
*   It returns the index of first occurrence which means if the string is present in input more than once than the function would return the index of first occurrence. Refer example.

#### Example of fn:indexOf() function

In this example we are finding out the index of few strings and displaying them using EL

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:indexOf() example</title>

</head>

<body>

${fn:indexOf("My name is Chandru pratap", "chandru")}

${fn:indexOf("My name is Chandru pratap", "Chandru")}

${fn:indexOf("This is an example", "is")}

${fn:indexOf("JSTL function - indexOf function", "function")}

</body>

</html>

Output:

-1 11 2 5

4. fn:escapeXML(): It is used for HTML/XML character escaping which means it treats html/xml tags as a string. Similar to the escapeXml attribute of <c:out> tag.

fn:escapeXml() – JSTL Function

fn:escapeXml() JSTL function is used for HTML/XML character escaping which means it treats html/xml tags as a string rather than markup tags.

#### Syntax:

String escapeXml(String input_string)

Convert the input_string into the output string after escaping html/xml markup tags.

*   function return type is String
*   Argument: input String

#### fn:escapeXml() Example

Here we have two Strings which have html tags bold(<b>) and italic (<i>). We are processing them using fn:escapeXml() function.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:escapeXml() example</title>

</head>

<body>

Message1: <b>Hi This is just a message</b>

<br>Message2: <i>This is an example</i>

<br>Message1 and fn:escapeXml(): ${fn:escapeXml("<b>Hi This is just a message</b>")}

<br>Message2 and fn:escapeXml(): ${fn:escapeXml("<i>This is an example</i>")}

</body>

</html>

Output:

As you can see when we used the function on input strings, the html tags didn’t work and get printed as it is, just like another normal string.

![](Images/image00411.jpeg)

5\. fn:join() and fn:split() functions: JSTL functions: fn:join() concatenates the strings with a given separator and returns the output string. fn:split() splits a given string into an array of substrings.

# fn:join() and fn:split() JSTL Functions

### fn:join()

It concatenates the strings with a given separator and returns the output string.

#### Syntax:

String fn:join(String arrayofstrings, String separator)

It concatenates all the elements of the input array along with the provided separator in between. The return type of this function is String, it returns the output string after concatenation.

#### Example – Join strings using fn:join() function

In this example we are having an array of strings and we are joining them using the separator (‘ & ‘).

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:join() example</title>

</head>

<body>

<%

String arr[]={"Chandru", "Rahul", "Ajith"};

session.setAttribute("names", arr);

%>

${fn:join(names, " & ")}

</body>

</html>

Output:

As you can see all the three names got concatenated having ‘ &’ in between.

Chandru & Rahul & Ajith

### fn:split()

It splits a given string into an array of substrings. Splitting process considers the delimiter string which we provide during function call. I.e. we provide the string and delimiter as arguments to the function and it returns the array of strings after splitting the input based on the delimiter string.

#### Syntax:

String[] fn:split(String inputstring, String delimiterstring)

#### Example – Join strings using fn:split() function

In this example we are having a input string which has few space characters in between. We have split the string using space as delimiter using fn:split() function. The function returned the array of the sub-strings.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:split() example</title>

</head>

<body>

<c:set  var="msg"  value="This is an example of JSTL function"/>

<c:set  var="arrayofmsg"  value="${fn:split(msg,' ')}"/>

<c:forEach  var="i"  begin="0"  end="6">

arrayofmsg[${i}]: ${arrayofmsg[i]}<br>

</c:forEach>

</body>

</html>

Output:

![](Images/image00412.jpeg)

6. fn:length():  The JSTL function fn:length() is used for computing the length of a string or to find out the number of elements in a collection. It returns the length of the object.

# fn:length() – JSTL Function

The JSTL function fn:length() is used for computing the length of a string or to find out the number of elements in a collection.

Syntax:

int length(Object)

Return type of this function is int. It returns the length of the object provided in it as an argument.

#### Example of fn:length()

Here we are computing the length of the three different strings using the function.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:length() example</title>

</head>

<body>

<c:set  var="string1"  value="This is String1"/>

<c:set  var="string2"  value="Hi"/>

<c:set  var="string3"  value="string3"/>

Length of String1 is: ${fn:length(string1)}<br>

Length of String2 is: ${fn:length(string2)}<br>

Length of String3 is: ${fn:length(string3)}

</body>

</html>

Output:

![](Images/image00413.jpeg)

7. fn:startsWith():  It checks the specified string is a prefix of given string.

# fn:trim() and fn:startsWith() JSTL Functions

In this post we are discussing two functions which operates on strings. These functions are fn:trim() and fn:startsWith(). Function fn:trim() removes spaces from beginning and end of a string and fn:startsWith() checks whether the specified string is a prefix of given string.

#### JSTL fn:trim() Function

It removes the space characters from start and end of the provided string.

Syntax:

String fn:trim(String input)

The function returns the string after removing the white spaces from start and end of the inputString.

#### Example:

In this example we have a string which has few space characters appended at the start and end of the string “mymsg” and we are truncating those spaces using the function.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:trim() example in JSTL</title>

</head>

<body>

<c:set  var="mymsg"  value=" This is the test String       "/>

${fn:trim(mymsg)}

</body>

</html>

Output Screenshot:

![](Images/image00414.jpeg)

#### fn:startsWith() function in JSTL

It checks whether the given string starts with a particular string value.

Syntax:

boolean fn:startsWith(String input, String prefix)

This function returns a boolean value. It gives true when the string starts with the given prefix else it returns false.

#### Example

Here we have one long string and two substrings of it and we are checking whether the string starts with any of those substrings.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:startsWith example</title>

</head>

<body>

<c:set  var="mymsg"  value="Example of JSTL function"/>

The string starts with "Example": ${fn:startsWith(mymsg, 'Example')}

<br>The string starts with "JSTL": ${fn:startsWith(mymsg, 'JSTL')}

</body>

</html>

Output: 

PFB the output screenshot for above example.

![](Images/image00415.jpeg)

8. fn:endsWith():  fn:endsWith() JSTL function is used for checking the suffix of a string. It checks whether the given string ends with a particular string.

# fn:endsWith() – JSTL Function

fn:endsWith() function is used for checking the suffix of a string. It checks whether the given string ends with a particular string. The validation is case sensitive.

#### Syntax:

boolean fn:endsWith(input_string, suffix_string)

It validates whether the input_string ends with suffix_string. If the test is successful then the function returns true else it gives false. The return type of the function is boolean and it receives both the strings as arguments.

Note: It considers the case while doing the check.

#### Example of fn:endsWith()

In the example we have a input string “JavaBook.com” and 4 other strings. We are verifying whether the input string ends with given four strings.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:endsWith() example</title>

</head>

<body>

String ends with ".com": ${fn:endsWith("JavaBook.com", "com")}

<br>String ends with "book.com": ${fn:endsWith("JavaBook.com", "book.com")}

<br>String ends with "Book.com": ${fn:endsWith("JavaBook.com", "Book.com")}

<br>String ends with "Book.co": ${fn:endsWith("JavaBook.com", "Book.co")}

</body>

</html>

Output:

![](Images/image00416.jpeg)

9. fn:substring():  This JSTL function is used for getting a substring from the provided string.

# fn:substring(), fn:substringAfter() & fn:substringBefore() Functions

In this tutorial we will discuss fn:substring(),fn:substringAfter() and fn:substringBefore() functions of JSTL. All of these functions are used for getting a part of the string from a given input string. The way of getting the output is different in all three functions.

### fn:substring ()

This function returns a substring of given input string as per the given start and end position.

#### Syntax:

String fn:substring(String inputstring, int start, int  end)

*   Return type of function: String
*   inputstring: The string from which a substring needs to be taken
*   start: Starting position of substring
*   end: end position of substring

#### Example – fn:substring() function

In this example we are fetching a substring from a given string by providing the starting and end positions of the substring.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:substring() example</title>

</head>

<body>

<c:set  var="msg"  value="This is an example of JSTL function"/>

${fn:substring(msg, 10, 26)}

</body>

</html>

Output:

example of JSTL

### fn:substringAfter()

It returns the part of a given string which lies after a provided string value.

#### Syntax

String fn:substringAfter(String input, String afterstring)

Whatever is present in the input after the “afterstring” is being returned by this function. Refer the below example to have the more clarity on this topic.

#### Example of fn:substringAfter()

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:substringAfter() example</title>

</head>

<body>

<c:set  var="name"  value="Rahul Pratap Prasad"/>

${fn:substringAfter(name, "Pr")}

</body>

</html>

Output:

atap Prasad

### fn:substringBefore()

It is just opposite of fn:substringAfter function. It returns the the part of original string which lies before a specified string value.

#### Syntax:

String fn:substringBefore(String input, String beforestring)

The part of “input” before the “beforestring” will be returned as the output of this function

#### Example of fn:substringBefore()

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:substringBefore() example</title>

</head>

<body>

<c:set  var="justastring"  value="Hi, How are you??"/>

${fn:substringBefore(justastring, "are")}

</body>

</html>

Output:

Hi, How

10. fn:substringAfter(): It is used for getting a substring which is present in the input string before a specified string.

Note: Read it full from example 9

11. fn:substringBefore():  It gets a substring from input which comes after a specified string.

Note: Read it full from example 9

12\. fn:trim(): JSTL Function fn:trim() removes spaces from beginning and end of a string and function.

# fn:trim() and fn:startsWith() JSTL Functions

In this post we are discussing two functions which operate on strings. These functions are fn:trim() and fn:startsWith(). Function fn:trim() removes spaces from beginning and end of a string and fn:startsWith() checks whether the specified string is a prefix of given string.

#### JSTL fn:trim() Function

It removes the space characters from start and end of the provided string.

Syntax:

String fn:trim(String input)

The function returns the string after removing the white spaces from start and end of the inputString.

#### Example:

In this example we have a string which has few space characters appended at the start and end of the string “mymsg” and we are truncating those spaces using the function.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:trim() example in JSTL</title>

</head>

<body>

<c:set  var="mymsg"  value=" This is the test String       "/>

${fn:trim(mymsg)}

</body>

</html>

Output:

This is the test String

#### fn:startsWith() function in JSTL

It checks whether the given string starts with a particular string value.

Syntax:

boolean fn:startsWith(String input, String prefix)

This function returns a boolean value. It gives true when the string starts with the given prefix else it returns false.

#### Example:

Here we have one long string and two substrings of it and we are checking whether the string starts with any of those substrings.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:startsWith example</title>

</head>

<body>

<c:set  var="mymsg"  value="Example of JSTL function"/>

The string starts with "Example": ${fn:startsWith(mymsg, 'Example')}

<br>The string starts with "JSTL": ${fn:startsWith(mymsg, 'JSTL')}

</body>

</html>

Output: PFB the output screenshot for above example.

![](Images/image00417.jpeg)

13. fn:toUpperCase():  It is just opposite of fn:toLowerCase() function. It converts input string to a uppercase string.

# fn:toUpperCase() – JSTL Function

It is just opposite of  [fn:toLowerCase() function](#part0000.xhtml_LOWERCASE). It converts input string to a uppercase string. All the characters of input string gets replaced with corresponding uppercase characters. The string which needs to be changed is provided as an argument to the function and the converted string is being returned by the function. We can pass the string as a variable or simply hard-coding it during function call.

#### Syntax:

String fn:toUpperCase(String input)

It returns the String after converting the input string to uppercase.

#### Example of fn:toUpperCase()

Here we are converting few strings to their uppercases using the function.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:toUpperCase() example</title>

</head>

<body>

 <c:set  var="site"  value="JavaBook.com"/>

 <c:set  var="author"  value="Chandru"/>

  Hi This is ${fn:toUpperCase(author)} from ${fn:toUpperCase(site)}.

</body>

</html>

Output:

The strings author and site got replaced with all uppercase alphabets.

Hi This is CHANDRU from JAVABOOK.COM.

14. fn:toLowerCase():  This function is used for converting an input string to a lower case string.

# fn:toLowerCase() – JSTL Function

This function converts a string into lowercase string. Any upper case character in the input string is replaced with the corresponding lowercase character.

#### Syntax:

String fn:toLowerCase(String input)

Return type: String; Argument: Single argument of String type.It returns a String after converting the input string to lowercase.

#### Example 0f fn:toLowerCase()

In this example we are applying this function on two strings – one is a string variable and another is a hard-coded string which is given as an argument to the function. As you can see in the output that it has replaced the variable value and hard-coded string value to lowercase. Screenshot of the output is provided just after this code.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>fn:toLowerCase() example</title>

</head>

<body>

<c:set  var="message"  value="This is An Example of JSTL Function"/>

${fn:toLowerCase(message)}

${fn:toLowerCase("HELLO")}

</body>

</html>

Output:

This is an Example of jstl function hello

15. fn:replace():  fn:replace() function search for a string in the input and replace it with the provided string. It does case sensitive processing.

# fn:replace() – JSTL Function

It search for a string in the input and replace it with the provided string. The following is the basic syntax of fn:replace() function.

#### Syntax:

String fn:replace(String input, String search_for, String replace_with)

Three string arguments and return type is also String. It searches the search_for string in input and replaces it with replace_with string. If the string is not found it returns the actual input as it is.

Note: It does case sensitive processing.

#### Example

In this example we are using fn:replace() function on two input strings.

<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@ taglib uri="http://java.sun.com/jsp/jstl/functions" prefix="fn" %>

<html>

<head>

<title>JSTL fn:replace() example</title>

</head>

<body>

<c:set  var="author"  value="Chandru Babu"/>

<c:set  var="randomstring"  value="abc def abc ghi ABC"/>

${fn:replace(author, "Chandru", "Rahul")}

${fn:replace(randomstring, "abc", "hello")}

</body>

</html>

Output:

Rahul Babu hello def hello ghi ABC

Observe the output you would find that the “ABC” in randomstring variable remains as it is while the other “abc” substrings got replaced with “hello”. It happened because of the case sensitive match, we are replacing lowercase “abc” in the above example.

JSON TUTORIAL

JSON Tutorial: Learn JSON in 10 Minutes

JSON Tutorial: Learn JSON in 10 Minutes

JSON stands for JavaScript Object Notation. JSON objects are used for transferring data between server and client, XML serves the same purpose. However JSON objects have several advantages over XML and we are going to discuss them in this tutorial along with JSON concepts and its usages.

Let us have a look at the piece of a JSON data: It basically has key-value pairs.

var chandru = {

 "firstName" : "Chandru",

 "lastName" : "babu",

 "age" :"28"

};

Features of JSON:

*   It is light-weight
*   It is language independent
*   Easy to read and write
*   Text based, human readable data exchange format

## Why use JSON?

Standard Structure: As we have seen so far that JSON objects are having a standard structure that makes developers job easy to read and write code, because they know what to expect from JSON.

Light weight: When working with AJAX, it is important to load the data quickly and asynchronously without requesting the page re-load. Since JSON is light weighted, it becomes easier to get and load the requested data quickly.

Scalable: JSON is language independent, which means it can work well with most of the modern programming language. Let’s say if we need to change the server side language, in that case it would be easier for us to go ahead with that change as JSON structure is same for all the languages.

## JSON vs. XML

Let see how JSON and XML look when we store the records of 4 students in a text based format so that we can retrieve it later when required.

JSON style:

{"students":[

   {"name":"John", "age":"23", "city":"Agra"},

   {"name":"Steve", "age":"28", "city":"Delhi"},

   {"name":"Peter", "age":"32", "city":"Chennai"},

   {"name":"Chandru", "age":"28", "city":"Bangalore"}

]}

XML style:

<students>

 <student>

 <name>John</name> <age>23</age>  <city>Agra</city>

 </student>

 <student>

 <name>Steve</name> <age>28</age>  <city>Delhi</city>

 </student>

 <student>

 <name>Peter</name> <age>32</age>  <city>Chennai</city>

 </student>

 <student>

 <name>Chandru</name> <age>28</age>  <city>Bangalore</city>

 </student>

</students>

As you can clearly see JSON is much more light-weight compared to XML. Also, in JSON we take advantage of arrays that is not available in XML.

## JSON data structure types and how to read them:

1.  JSON objects
2.  JSON objects in array
3.  Nesting of JSON objects

#### 1) JSON objects:

var chandru = {

 "name" : "Chandru",

 "age" : "28",

 "website" : "javasbook"

};

The above text creates an object that we can access using the variable chandru. Inside an object we can have any number of key-value pairs like we have above. We can access the information out of a JSON object like this:

document.writeln("The name is:  " +chandru.name);

document.writeln("his age is: " + chandru.age);

document.writeln("his website is: "+ chandru.website);

#### 2) JSON objects in array

In the above example we have stored the information of one person in a JSON object suppose we want to store the information of more than one person; in that case we can have an array of objects.

var students = [{

 "name" : "Steve",

 "age" : "29",

 "gender" : "male"

},

{

 "name" : "Peter",

 "age" : "32",

 "gender" : "male"

},

{

 "name" : "Sophie",

 "age" : "27",

 "gender" : "female"

}];

To access the information out of this array, we do write the code like this:

document.writeln(students[0].age); //output would be: 29

document.writeln(students[2].name); //output: Sophie

You got the point, right? Let’s carry on with the next type.

#### 3) Nesting of JSON objects:

Another way of doing the same thing that we have done above.

var students = {

 "steve" : {

 "name" : "Steve",

 "age" : "29",

 "gender" : "male"

},

"pete" : {

 "name" : "Peter",

 "age" : "32",

 "gender" : "male"

},

"sop" : {

 "name" : "Sophie",

 "age" : "27",

 "gender" : "female"

}

}

Do like this to access the info from above nested JSON objects:

document.writln(students.steve.age); //output: 29

document.writeln(students.sop.gender); //output: female

## JSON & JavaScript:

JSON is considered as a subset of JavaScript but that does not mean that JSON cannot be used with other languages. In fact it works well with PHP, Perl, Python, Ruby, Java, Ajax and many more.

Just to demonstrate how JSON can be used along with JavaScript, here is an example:
If you have gone though the above tutorial, you are familiar with the JSON structures. A JSON file type is .json

How to read data from json file and convert it into a JavaScript object?

We have two ways to do this.

1) Using eval function, but this is not suggested due to security reasons (malicious data can be sent from the server to the client and then eval in the client script with harmful effects).
2) Using JSON parser: No security issues plus it is faster than eval. Here is how to use it:

var chandru = {

"name" : "Chandru",

"age" : "28",

"website" : "Javabook"

};

We are converting the above JSON object to javascript object using JSON parser:

var myJSObject = JSON.parse(Chandru);

How to convert JavaScript object to JSON text?

By using method stringify

var jsonText= JSON.stringify(myJSObject);

I guess the 10 minutes are over.

SERVLET TUTORIAL

Servlet Introduction

Servlet is a java program that runs inside JVM on the web server. It is used for developing dynamic web applications.

Before we proceed further let us understand what is dynamic web application? A web application can be described as collection of web pages (e.g. a website) and when we call it dynamic, it simply means that the web pages are not same for all the users, web pages would be generated on server side based on the request made by client(user’s browser).

The main difference between static and dynamic web page is that static page as name suggests remains same for all users however a dynamic web page changes based on the request from client (user’s browser). For example, consider a web application that shows you two input fields & an add button and when you enter two numbers and click add, it shows you another web page that has the result of addition of two numbers, this web application is dynamic in nature as the second web page that shows you the result changes based on the user input, it is not static for all users.

However you can very well say that what a servlet does can be done by CGI (Common Gateway Interface), well its true but here is the thing – CGI has several limitations such as performance, scalability, reusability etc. that a servlet does not have. I am not going to discuss CGI in detail but I am going to tell you, how a servlet is better than CGI.

### Limitations of CGI

Server has to create a new CGI process for every client request. For example, If 100 users are accessing the web application, then the server has to create 100 CGI processes to handle the request made by them. Since a server has limited resources, creating new process every time for a new request is not a viable option, this imposed the limitation on server, due to that the server cannot handle more than a specified number of users at the same time.

### How Servlet is better than CGI

CGI programs are handled by a new process every time a new request has been made. Unlike CGI, the servlet programs are handled by separate threads that can run concurrently more efficiently.

CGI program can be written in any programming language that makes it mostly platform dependent as not all programming languages are platform independent. Servlet only uses Java as programming language that makes it platform independent and portable. Another benefit of using java is that the servlet can take advantage of the object oriented programming features of java.

#### How Servlet Works

As I mentioned above that concurrent requests to the server are handled by threads, here is the graphical representation of the same –

![](Images/image00418.jpeg)

## Features of Servlet

Now that we have understood what is a servlet and for what purpose it is being used. Let’s proceed further and discuss its main features.

1.Portable:
As I mentioned above that Servlet uses Java as a programming language, Since java is platform independent, the same holds true for servlets. For example, you can create a servlet on Windows operating system that users GlassFish as web server and later run it on any other operating system like Unix, Linux with Apache tomcat web server, this feature makes servlet portable and this is the main advantage servlet has over CGI.

2\. Efficient and scalable:

Once a servlet is deployed and loaded on a web server, it can instantly start fulfilling request of clients. The web server invokes servlet using a lightweight thread so multiple client requests can be fulling by servlet at the same time using the multithreading feature of Java. Compared to CGI where the server has to initiate a new process for every client request, the servlet is truly efficient and scalable.

3.Robust:
By inheriting the top features of Java (such as Garbage collection, Exception handling, Java Security Manager etc.) the servlet is less prone to memory management issues and memory leaks. This makes development of web application in servlets secure and less error prone.

# Servlet API

You need to use Servlet API to create servlets. There are two packages that you must remember while using API, the javax.servlet package that contains the classes to support generic servlet (protocol-independent servlet) and the javax.servlet.http package that contains classes to support http servlet. You may be wondering what is generic and http servlet, I have explained them later in this post.

Let us see the hierarchy of packages:

java.lang.Object

|_extended byjavax.servlet.GenericServlet

 |_extended byjavax.servlet.http.HttpServlet

Every Servlet must implement the java.servlet.Servletinterface, you can do it by extending one of the following two classes: javax.servlet.GenericServlet or javax.servlet.http.HttpServlet. The first one is for protocol independent Servlet and the second one for http Servlet.

How servlet works?

![](Images/image00419.jpeg)

## Generic Servlet

As I mentioned above, if you are creating a Generic Servlet then you must extend javax.servlet.GenericServlet class. GenericServlet class has an abstract service() method. Which means the subclass of GenericServlet should always override the service() method.

Signature of service() method:

public  abstract  void service(ServletRequest request, ServletResponse response)

 throws  ServletException, java.io.IOException

The service() method accepts two arguments ServletRequest object and ServletResponse object. The request object tells the servlet about the request made by client while the response object is used to return a response back to the client.

![](Images/image00420.jpeg)

## HTTP Servlet

If you creating Http Servlet you must extend javax.servlet.http.HttpServlet class,which is an abstract class. Unlike Generic Servlet, the HTTP Servlet doesn’t override the service() method. Instead it overrides one or more of the following methods. It must override at least one method from the list below:

*   doGet() – This method is called by servlet service method to handle the HTTP GET request from client. The Get method is used for getting information from the server
*   doPost() – Used for posting information to the Server
*   doPut() – This method is similar to doPost method but unlike doPost method where we send information to the server, this method sends file to the server, this is similar to the FTP operation from client to server
*   doDelete() – allows a client to delete a document, webpage or information from the server
*   int() and destroy() – Used for managing resources that are held for the life of the servlet
*   getServletInfo() – Returns information about the servlet, such as author, version, and copyright.

In Http Servlet there is no need to override the service() method as this method dispatches the Http Requests to the correct method handler, for example if it receives HTTP GET Request it dispatches the request to the doGet() method.

![](Images/image00421.jpeg)

#### Interfaces in javax.servlet package

*   Servlet
*   ServletRequest
*   ServletResponse
*   ServletConfig
*   ServletContext
*   SingleThreadModel
*   RequestDispatcher
*   ServletRequestListener
*   ServletRequestAttributeListener
*   ServletContextListener
*   ServletContextAttributeListener
*   Filter
*   FilterConfig
*   FilterChain

#### Classes in javax.servlet package

*   GenericServlet
*   ServletInputStream
*   ServletOutputStream
*   ServletException
*   ServletRequestWrapper
*   ServletRequestEvent
*   ServletResponseWrapper
*   ServletContextEvent
*   ServletRequestAttributeEvent
*   ServletContextAttributeEvent
*   UnavailableException

#### Interfaces in javax.servlet.http package

*   HttpSession
*   HttpServletRequest
*   HttpServletResponse
*   HttpSessionAttributeListener
*   HttpSessionListener
*   HttpSessionBindingListener
*   HttpSessionActivationListener
*   HttpSessionContext

#### Classes in javax.servlet.http package

*   HttpServlet
*   Cookie
*   HttpSessionEvent
*   HttpSessionBindingEvent
*   HttpServletRequestWrapper
*   HttpServletResponseWrapper
*   HttpUtils

Servlet Interface

# Servlet Interface explained with Example

# In my last guide about Servlet API, I have explained that to create any Servlet you must implement the Servlet interface directly or indirectly (indirectly implementation means extending those classes that implements Servlet interface, These classes are GenericServlet and HttpServlet).

# If you are creating protocol dependent servlet such as http servlet then you should extend HttpServlet class else for protocol independent Servlet you extend GenericServlet class.

# In this guide I am not going to explain GenericServlet and HttpServlet in detail as I have covered them in the separate guide.

# Edit: Here are the links of those guides: [GenericServlet](#part0000.xhtml_generic) | [HttpServlet](#part0000.xhtml_httpservlet).

# In short you have 3 ways  to create a servlet:
1) By extending HttpServlet class
2) By extending GenericServlet class
3) By implementing Servlet interface
Note:  However you should always prefer the first way of creating servlet i.e. by extending HttpServlet class.

### Servlet Interface methods

Here is the list of methods available in Servlet interface.

# 1) Void destroy(): This method is called by Servlet container at the end of [servlet life cycle.](#part0000.xhtml_servletlife)  Unlike service() method that gets called multiple times during life cycle, this method is called only once by Servlet container during the complete life cycle. Once destroy() method is called the servlet container does not call the service() method for that servlet.

2) Void init(ServletConfig config): When Servlet container starts up (that happens when the web server starts up) it loads all the servlets and instantiates them. After this init() method gets called for each instantiated servlet, this method initializes the servlet.

3) Void service(ServletRequest req, ServletResponse res): This is the only method that is called multiple times during servlet life cycle. This methods serves the client request, it is called every time the server receives a request.

4) ServletConfig getServletConfig(): Returns a ServletConfig object, which contains initialization and startup parameters for this servlet.

5) Java.lang.String getServletInfo(): Returns information about the servlet, such as author, version, and copyright.

## Example:

In this example we have created a servlet class by extending Servlet interface.

index.html

<a  href="welcome">Click here to call the servlet</a>

DemoServlet.java

import java.io.*;

import javax.servlet.*;

public  class  DemoServlet  implements  Servlet{

 ServletConfig config=null;

 public  void init(ServletConfig config){

 this.config=config;

 System.out.println("Initialization complete");

   }

 public  void service(ServletRequest req,ServletResponse res)

 throws  IOException,ServletException{

       res.setContentType("text/html");

 PrintWriter pwriter=res.getWriter();

       pwriter.print("<html>");

       pwriter.print("<body>");

       pwriter.print("<h1>Servlet Example Program</h1>");

       pwriter.print("</body>");

       pwriter.print("</html>");

   }

 public  void destroy(){

 System.out.println("servlet life cycle finished");

   }

 public  ServletConfig getServletConfig(){

 return config;

   }

 public  String getServletInfo(){

 return  "A Demo program written by Chandru";

   }

}

web.xml

<web-app>

<servlet>

 <servlet-name>Javabook</servlet-name>

 <servlet-class>DemoServlet</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>Javabook</servlet-name>

 <url-pattern>/welcome</url-pattern>

</servlet-mapping>

</web-app>

# GenericServlet Class

# GenericServlet Class with example

# While discussing Servlet API, I have discussed little bit about Generic Servlet. In this article, I will discuss Generic Servlet in detail.

# A generic servlet is a protocol independent Servlet that should always override the service() method to handle the client request. The service() method accepts two arguments ServletRequest object and ServletResponse object. The request object tells the servlet about the request made by client while the response object is used to return a response back to the client.

### How Generic Servlet works?

# ![](Images/image00422.jpeg)

### Hierarchy of Generic Servlet

java.lang.Object

|_extended byjavax.servlet.GenericServlet

GenericServlet is an abstract class and it has only one abstract method, which is service(). That’s why when we create Generic Servlet by extending GenericServlet class, we must override service() method.

Pros of using Generic Servlet:
1\. Generic Servlet is easier to write
2\. Has simple lifecycle methods
3\. To write Generic Servlet you just need to extend javax.servlet.GenericServlet and override the service() method (check the example below).

Cons of using Generic Servlet:
Working with Generic Servlet is not that easy because we don’t have convenience methods such as doGet(), doPost(), doHead() etc in Generic Servlet that we can use in Http Servlet.
In Http Servlet we need to override particular convenience method for particular request, for example if you need to get information then override doGet(), if you want to send information to server override doPost(). However in Generic Servlet we only override service() method for each type of request which is cumbersome.

I would always recommend you to use HttpServlet instead of the GenericServlet. HttpServlet is easier to work with, and has more methods to work with than GenericServlet.

### Example of GenericServlet

I am using Eclipse IDE for this example. Create New “Dynamic Web Project” from the Eclipse file menu.

Note:

Go back from here

[Servlet Interface](#part0000.xhtml_servletinter)

Note:I have explained all the steps for creating Servlet in Eclipse IDE, however if you are unfamiliar with Eclipse and don’t have it installed on your system then refer this guide: [How to Install Eclipse, configure tomcat and run your First Servlet Application using Eclipse.](#part0000.xhtml_createndrun)

Project structure (or you can hierarchy) would look like this, once you are done creating all the following files in IDE.

# ![](Images/image00423.jpeg)

index.html
We are creating an html file that would call the servlet once we click on the link on web page. Create this file in WebContent folder. The path of the file should look like this: WebContent/index.html

index<!DOCTYPE html>

<html>

<head>

<meta charset="UTF-8">

<title>Http  Servlet  Demo</title>

</head>

<body>

<a href="welcome">Click to call Servlet</a>

</body>

</html>

ExampleGeneric.java
Now, we are creating a Generic Servlet by extending GenericServlet class. When creating a GenericServlet you should always override service() method. Right click on the src folder and create a new class file, name the file as ExampleGeneric. The file path should look like this: Java Resouces/src/default package/ExampleGeneric.java

import java.io.*;

import javax.servlet.*;

public  class  ExampleGeneric  extends  GenericServlet{

 public  void service(ServletRequest req,ServletResponse res)

throws  IOException,ServletException{

   res.setContentType("text/html");

 PrintWriter pwriter=res.getWriter();

   pwriter.print("<html>");

   pwriter.print("<body>");

   pwriter.print("<h2>Generic Servlet Example</h2>");

   pwriter.print("<p>Hello JavaBook Readers!</p>");

   pwriter.print("</body>");

   pwriter.print("</html>");

 }

}

web.xml
This file can be found at this path WebContent/WEB-INF/web.xml. In this file we will map the Servlet with the specific URL. Since we are calling welcome page upon clicking the link on index.html page so we are mapping the welcome page to the Servlet class we created above.

<web-app>

<display-name>JavaBookServlet</display-name>

<welcome-file-list>

<welcome-file>index.html</welcome-file>

<welcome-file>index.htm</welcome-file>

<welcome-file>index.jsp</welcome-file>

<welcome-file>default.html</welcome-file>

<welcome-file>default.htm</welcome-file>

<welcome-file>default.jsp</welcome-file>

</welcome-file-list>

<servlet>

<servlet-name>MyHttpServlet</servlet-name>

<servlet-class>ExampleHttpServlet</servlet-class>

</servlet>

<servlet-mapping>

<servlet-name>MyHttpServlet</servlet-name>

<url-pattern>/welcome</url-pattern>

</servlet-mapping>

</web-app>

Run the project:
Right click on the index.html, run on server.

Output:

# ![](Images/image00424.jpeg)

# Screen after you click the link in first screen:

# Generic Servlet Example

# Hello Javabook Readers

## Methods of GenericServlet class:

Here is the list of all the methods of GenericServlet class.

1. public void init(): it is a convenient method. This method can be overridden so that there’s no need to call super.init(config).

2. public void init(ServletConfig config): Called by the servlet container to indicate that the servlet is being placed into service, this method is used for initializing the servlet.

3. public String getInitParameter(String name): Returns a String containing the value of the given initialization parameter, or null if the parameter does not exist.

4. public Enumeration getInitParameterNames(): Returns the names of all the parameters defined in the web.xml file or null if web.xml does’t have any parameter.

5. public abstract void service(ServletRequest request, ServletResponse response): Called by the Servlet container to allow servlet to respond to the requests made by client.

6. public void destroy(): It is called by servlet container once at the end of servlet life cycle to indicate that servlet is being destroyed.

7. public ServletConfig getServletConfig(): Return the ServletConfig object that initialized this servlet.

8. public String getServletInfo(): Returns information about servlet.

9. public ServletContext getServletContext(): Return ServletContext object, passed to this servlet by the init method.

10. public String getServletName(): Returns the name of the servlet instance.

11. public void log(String msg): Writes the given message in the servlet log file.

12. public void log(String msg,Throwable t): Writes the explanatory message in the servlet log file including a String that describes the error or exception.

HttpServlet class with example

Unlike Generic Servlet, the HTTP Servlet doesn’t override the service() method. Instead it overrides the doGet() method or doPost() method or both. The doGet() method is used for getting the information from server while the doPost() method is used for sending information to the server.

In Http Servlet there is no need to override the service() method because this method dispatches the Http Requests to the correct method handler, for example if it receives HTTP GET Request it dispatches the request to the doGet() method.

## How Http Servlet works?

As you can see in the diagram below that client (user’s browser) make requests. These requests can be of any type, for example – Get Request, Post Request, Head Request etc. Server dispatches these requests to the servlet’s service() method, this method dispatches these requests to the correct handler for example if it receives Get requests it dispatches it to the doGet() method.

![](Images/image00425.jpeg)

## Hierarchy of Http Servlet

java.lang.Object

|_extended byjavax.servlet.GenericServlet

 |_extended byjavax.servlet.http.HttpServlet

I have already discussed in the Generic Servlet article that you should always use HttpServlet instead of the GenericServlet. HttpServlet is easier to work with, and has more methods to work with than GenericServlet.

## Http Servlet example

I am using Eclipse IDE for this example. Create New “Dynamic Web Project” from the Eclipse file menu.

Note:I have explained all the steps for creating Servlet in Eclipse IDE, however if you are unfamiliar with Eclipse and don’t have it installed on your system then refer this guide: [How to Install Eclipse, configure tomcat and run your First Servlet Application using Eclipse.](#part0000.xhtml_createndrun)

Project structure (or you can hierarchy) would look like this, once you are done creating all the following files in IDE.

![](Images/image00426.jpeg)

index.html
We are creating an html file that would call the servlet once we click on the link on web page. Create this file in WebContent folder. The path of the file should look like this: WebContent/index.html

index<!DOCTYPE html>

<html>

<head>

<meta charset="UTF-8">

<title>Http  Servlet  Demo</title>

</head>

<body>

<a href="welcome">Click to call Servlet</a>

</body>

</html>

ExampleHttpServlet.java

Now, we are creating a Http Servlet by extending HttpServlet class. Right click on the src folder and create a new class file, name the file as ExampleHttpServlet. The file path should look like this: Java Resources/src/default package/ExampleHttpServlet.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

// Creating Http Servlet by Extending HttpServlet class

public  class  ExampleHttpServlet  extends  HttpServlet

{    

 private  String mymsg;

 public  void init() throws  ServletException

    {     

mymsg = "Http Servlet Demo";   

    }

 public  void doGet(HttpServletRequest request,

 HttpServletResponse response)throws  ServletException,

 IOException

    {           

 // Setting up the content type of web page     

        response.setContentType("text/html");

 // Writing the message on the web page     

 PrintWriter  out = response.getWriter();

 out.println("<h1>" + mymsg + "</h1>");     

 out.println("<p>" + "Hello Friends!" + "</p>");   

    }

 public  void destroy()

    {     

 // Leaving empty. Use this if you want to perform  

 //something at the end of Servlet life cycle.   

    }

}

web.xml

This file can be found at this path WebContent/WEB-INF/web.xml. In this file we will map the Servlet with the specific URL. Since we are calling welcome page upon clicking the link on index.html page so we are mapping the welcome page to the Servlet class we created above.

<web-app>

<display-name>JavaBookServlet</display-name>

<welcome-file-list>

<welcome-file>index.html</welcome-file>

<welcome-file>index.htm</welcome-file>

<welcome-file>index.jsp</welcome-file>

<welcome-file>default.html</welcome-file>

<welcome-file>default.htm</welcome-file>

<welcome-file>default.jsp</welcome-file>

</welcome-file-list>

<servlet>

<servlet-name>MyHttpServlet</servlet-name>

<servlet-class>ExampleHttpServlet</servlet-class>

</servlet>

<servlet-mapping>

<servlet-name>MyHttpServlet</servlet-name>

<url-pattern>/welcome</url-pattern>

</servlet-mapping>

</web-app>

Run the project:
Right click on the index.html, run on server.

Output:

![](Images/image00424.jpeg)

Screen after you click the link in first screen:

Http Servlet Demo

Hello Friends

## Methods of HttpServlet class

1. protected void doGet(HttpServletRequest req, HttpServletResponse resp): This method is called by servlet service method to handle the HTTP GET request from client. When overriding this method, read the request data, write the response headers, get the response’s writer or output stream object, and finally, write the response data.

2. protected long getLastModified(HttpServletRequest req): Returns a long integer specifying the time the HttpServletRequest object was last modified, in milliseconds since midnight, January 1, 1970 GMT, or -1 if the time is not known

3. protected void doHead(HttpServletRequest req, HttpServletResponse resp): This method is called by servlet service method to handle the HTTP HEAD request from client. The client sends a HEAD request when it wants to see only the headers of a response, such as Content-Type or Content-Length

4. protected void doPost(HttpServletRequest req, HttpServletResponse resp): This method is called by servlet service method to handle the POST request from client. The HTTP POST method allows the client to send data of unlimited length to the Web server a single time and is useful when posting information to the server. Unlike, doGet where we get information from the sever this method is used when we are transferring information from client to the server.

5. protected void doPut(HttpServletRequest req, HttpServletResponse resp): This method is called by servlet service method to handle the PUT request from client. This method is similar to doPost method but unlike doPost method where we send information to the server, this method sends file to the server, this is similar to the FTP operation from client to server.

6. protected void doDelete(HttpServletRequest req, HttpServletResponse resp): Called by servlet service() method to handle the DELETE request from client that allows a client to delete a document, webpage or information from the server.

7. protected void doOptions(HttpServletRequest req, HttpServletResponse resp): Called by the service method to allow a servlet to handle a OPTIONS request. The OPTIONS request determines which HTTP methods the server supports and returns an appropriate header.

8. protected void doTrace(HttpServletRequest req, HttpServletResponse resp): This method is called by service() method for handling TRACE request. Used for debugging purposes.

9. protected void service(HttpServletRequest req, HttpServletResponse resp): There is no need to override this method, this method receives the HTTP request from client and forwards them to the corresponding doXXX methods such as doGet(), doPost(), doHEAD() etc.

10. public void service(ServletRequest req, ServletResponse res): Forwards client request to the protected service method. There’s no need to override this method as well.

# Note:

Go back from here

[Servlet Interface](#part0000.xhtml_servletinter)

How to create and run Servlet in Eclipse IDE

This is a complete guide for installing Eclipse, setting up apache tomcat server and running your first hello world servlet application.

Note:

Get back from here:

[Generic Servlet](#part0000.xhtml_generic)

[HttpServlet class](#part0000.xhtml_http)

## Download Eclipse IDE

Install Eclipse on Windows

Go to this link https://www.eclipse.org/downloads. Under “Get Eclipse Oxygen”❯Click “Download Packages”❯ Download “Eclipse IDE for Java Developers”. You would see two options on the right side (32 bit and 64 bit), click on 32 bit if you system is 32 bit else click on 64 bit. This will download a zipped file on your system.

To install Eclipse, unzip the downloaded file and copy the unzipped folder to the desired location

Install Eclipse on Mac OS X

Go to this link https://www.eclipse.org/downloads. Under “Get Eclipse Oxygen”❯Click “Download Packages”❯ Download “Eclipse IDE for Java Developers”. To download click on 64 bit and it would download a TAR file.

Once download is finished double click on the TAR file, it would extract the contents of the file to a folder. Drag the folder to “Applications” folder.

To launch the Eclipse, click on Eclipse icon in the Eclipse folder. Mac users can drag this to the dock area to quickly launch Eclipse from desktop, similarly Windows can create a shortcut of Eclipse on desktop.

## Installing and configuring Apache tomcat server in Eclipse

In order to run Servlet in Eclipse IDE, you need to have Apache tomcat Server configured in Eclipse IDE.

If you don’t have it then refer this tutorial: [How to download and configure Apache Tomcat Server in Eclipse IDE.](#part0000.xhtml_apacheconfigure)

Note:  The link I have provided above belongs to JSP tutorials but the steps are same for Servlets as well.

## Creating Servlet in Eclipse IDE

### Step 1: Create a Project:

Lets create a Servlet application in Eclipse. Open Eclipse and then click File❯New❯ Click Dynamic Web Project.

![](Images/image00427.jpeg)

If you do not see dynamic web project option in Eclipse then refer this tutorial[: How to fix “Dynamic Web project” missing in Eclipse issue](#part0000.xhtml_dynammic)

Give Project name and click Next.

![Give project name](Images/image00428.jpeg)

Tick the checkbox that says Generate web.xml deployment descriptor

![Generate web xml](Images/image00429.jpeg)

Initial Project structure:

Upon creation of project, the hierarchy (project structure) would look like this:

![Initial Project hierarchy in Eclipse](Images/image00430.jpeg)

### Step 2: Create a Servlet class:

We are creating the Http Servlet by extending HttpServlet class. Right click on the src folder and create a new class file, name the file as MyServletDemo. The file path should look like this: Java Resources/src/default package/MyServletDemo.java

![New Servlet Class](Images/image00431.jpeg)

MyServletDemo.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

// Extend HttpServlet class to create Http Servlet

public  class  MyServletDemo  extends  HttpServlet {

 private  String mymsg;

 public  void init() throws  ServletException {

mymsg = "Hello World!";

   }

 public  void doGet(HttpServletRequest request,

 HttpServletResponse response)

 throws  ServletException, IOException

   {

 // Setting up the content type of webpage

      response.setContentType("text/html");

 // Writing message to the web page

 PrintWriter  out = response.getWriter();

 out.println("<h1>" + mymsg + "</h1>");

   }

 public  void destroy() {

 /* leaving empty for now this can be

       * used when we want to do something at the end

       * of Servlet life cycle

       */

   }

}

### Step 3: Create an html page to call the servlet class on a webpage

We are creating an html file that would call the servlet once we click on the link on web page. Create this file in WebContent folder. The path of the file should look like this: WebContent/index.html
index.html

<!DOCTYPE html>

<html>

<head>

<meta  charset="UTF-8">

<title>JavaBook Servlet Demo</title>

</head>

<body>

<a  href="welcome">Click to call Servlet</a>

</body>

</html>

Edit web.xml file

This file can be found at this path WebContent/WEB-INF/web.xml. In this file we will map the Servlet with the specific URL. Since we are calling welcome page upon clicking the link on index.html page so we are mapping the welcome page to the Servlet class we created above.

<web-app>

<display-name>JavaBookDemo</display-name>

<welcome-file-list>

<welcome-file>index.html</welcome-file>

<welcome-file>index.htm</welcome-file>

<welcome-file>index.jsp</welcome-file>

<welcome-file>default.html</welcome-file>

<welcome-file>default.htm</welcome-file>

<welcome-file>default.jsp</welcome-file>

</welcome-file-list>

<servlet>

<servlet-name>MyHttpServletDemo</servlet-name>

<servlet-class>MyServletDemo</servlet-class>

</servlet>

<servlet-mapping>

<servlet-name>MyHttpServletDemo</servlet-name>

<url-pattern>/welcome</url-pattern>

</servlet-mapping>

</web-app>

Final Project Structure

![](Images/image00432.jpeg)

Run the project:
Right click on the index.html, run on server.

![Run on Apache tomcat server](Images/image00433.jpeg)

Click Add All to deploy the Project on Server. Click Finish

![Add all projects](Images/image00434.jpeg)

Output:

![](Images/image00435.jpeg)

Upon clicking the link you would get this screen:

![](Images/image00436.jpeg)

How to configure Apache Tomcat Server in Eclipse IDE

To run JSP in Eclipse, you need a Server. In this tutorial we will see how to download and configure Apache tomcat server in Eclipse IDE.

Step 1: Download

Go to this link: http://tomcat.apache.org/download-80.cgi. If you are on Mac then click the zip file (first option under core). If you are on Windows then you have two options, 32 bit and 64 bit, depending on your operating system type click on the zip file, for example if you are on 64 bit windows then click on the 64-bit Windows zip.

![Apache Tomcat Download location](Images/image00437.jpeg)

In this tutorial, I’m downloading Apache tomcat version 8.0.44

Step 2: Extract the downloaded zip folder
Extract the zipped folder to any desired location.

Step 3: Select the Server in Eclipse IDE
Open Eclipse IDE❯Click on the Servers tab located at the bottom❯right click❯New❯ click on Server

![configuring_tomcat_server_in_Eclipse_IDE](Images/image00438.jpeg)

Select Apache and then select the appropriate version of tomcat server, for example, I’ve downloaded the tomcat version 8.0.44 so I’m selecting Tomcat v8.0 Server. After selecting, click next.

Note:If you don’t see the apache option in the add server list that means you are missing few adapters in Eclipse, refer this tutorial to fix the issue: [How to fix “no apache tomcat adapter in Eclipse” issue](#part0000.xhtml_noapache)

![configuring_tomcat_server_in_Eclipse_IDE_2](Images/image00439.jpeg)

You will be presented with a window as shown in the image below. Click browse and select the the folder that you have extracted from the zip file in Step 2.

![configuring_tomcat_server_in_Eclipse_IDE_3](Images/image00440.jpeg)

Click finish.

![Browse_Downloaded_Tomcat_dir](Images/image00441.jpeg)

That’s it you have successfully configured the tomcat server in Eclipse, you can now run the JSP in Eclipse.

How to fix Dynamic Web Project missing in Eclipse issue

It is frustrating when you want to create your First JSP project in Eclipse and don’t find the “dynamic web project” option under project list. Well, in this tutorial, we will see step by step solution to this problem.

Step 1: Click on Help and then click on “Install New Software”.

![](Images/image00442.jpeg)

Step 2: In Work with paste this link: http://download.eclipse.org/releases/mars

Please note that the link I have provided would work on Eclipse mars only so change the link according to your Eclipse version, for example for the Eclipse Kepler the link would be http://download.eclipse.org/releases/kepler

![https://beginnersbook.com/wp-content/uploads/2017/06/no_dynamic_web_project_solution_2-1024x452.png](Images/image00443.jpeg)

Step 3: Scroll down to find “Web, XML, Java EE and OSGI Enterprise Development” option and expand it.

![https://beginnersbook.com/wp-content/uploads/2017/06/no_dynamic_web_project_solution_3-1024x407.png](Images/image00444.jpeg)

Step 4: Select the following three options under “Web, XML, Java EE and OSGI Enterprise Development”

*   Eclipse Java EE Developer Tools
*   Eclipse Java Web Developer Tools
*   Eclipse Web Developer Tools

![https://beginnersbook.com/wp-content/uploads/2017/06/no_dynamic_web_project_solution_4-1024x398.png](Images/image00445.jpeg)

Step 5: Click next and you would see that the software are installing. Wait for some time and then a popup would ask your permission to restart the Eclipse. Restart it and you would find the dynamic web project option under project list.

![https://beginnersbook.com/wp-content/uploads/2017/06/no_dynamic_web_project_solution_5-1024x412.png](Images/image00446.jpeg)

Note:

Get back from here:

[How to create and run Servlet in Eclipse IDE](#part0000.xhtml_createndrun)

Solution – No Apache Tomcat Adapter option in Eclipse IDE

Sometimes you don’t find the Apache option when you try to add the tomcat server first time in the Eclipse. It happens when you are missing few adapters. In this tutorial, I will tell you how to fix this issue.

Step 1: Go to Help❯ Install New Software

![https://beginnersbook.com/wp-content/uploads/2017/06/no_dynamic_web_project_solution-1024x783.png](Images/image00447.jpeg)

Step 2:In Work with field paste http://download.eclipse.org/releases/mars

Use the above link only when you are using Eclipse mars version,
else give the link as per your Eclipse version. For example, Eclipse Kepler users would give this link in the Work with field: http://download.eclipse.org/releases/kepler

Scroll down until you see “Web, XML, Java EE and OSGi Enterprise Development”, then expand this and add the following adapters:

*   JST Server Adapters
*   JST Server Adapters Extensions

![https://beginnersbook.com/wp-content/uploads/2017/06/no_Apache_Tomcat_adapter_in_Eclipse-1024x764.png](Images/image00448.jpeg)

Step 3: Click Next and you would see the following screen. Click next again.

![https://beginnersbook.com/wp-content/uploads/2017/06/no_Apache_Tomcat_adapter_in_Eclipse_2-1024x767.png](Images/image00449.jpeg)

Step 4: Accept the agreement and click Finish

![https://beginnersbook.com/wp-content/uploads/2017/06/no_Apache_Tomcat_adapter_in_Eclipse_3-1024x770.png](Images/image00450.jpeg)

That’s it. It would ask you to restart the Eclipse after installation, choose restart. You would now be able to see Apache when you try to add the server in Eclipse.

Note:

Get back from here

[How to configure Apache Tomcat Server in Eclipse IDE](#part0000.xhtml_apache)

# Servlet Life Cycle

Servlet life cycle can be described as a series of steps through which a servlet goes during its life span, starting from loading till it gets destroyed.

Before I start explaining the life cycle of Servlet, lets discuss few terminologies that you will encounter while reading this guide. It is important to learn what each term means, this will help you understand things faster.

Web Server: It is also known as HTTP Server, it can handle HTTP Requests send by client and responds the request with an HTTP Response.

Web Container: Also known as Servlet Container and Servlet Engine. It is a part of Web Server that interacts with Servlets. This is the main component of Web Server that manages the life cycle of Servlets.

Note: The servlet tutorials you find in this website uses apache tomcat web server. Although I mentioned it as web server, it is in fact a web server and web container both. (As mentioned above web container is a part of web server).

## Life Cycle of Servlet

Servlet life cycle contains five steps: 1) Loading of Servlet 2) Creating instance of Servlet 3) Invoke init() once 4) Invoke service() repeatedly for each client request 5) Invoke destroy()

For those who are wondering what is instance and invoke means: Instance and objects are same thing. Invoking a method means calling a method, it is just a fancy word that we use in programming world in place of calling :)

Let’s back to the main topic. Here are the five steps of servlet life cycle.

Step 1: Loading of Servlet
When the web server (e.g. Apache Tomcat) starts up, the servlet container deploy and loads all the servlets.

Step 2: Creating instance of Servlet
Once all the Servlet classes loaded, the servlet container creates instances of each servlet class. Servlet container creates only once instance per servlet class and all the requests to the servlet are executed on the same servlet instance.

Step 3: Invoke init() method

Once all the servlet classes are instantiated, the init() method is invoked for each instantiated servlet. This method initializes the servlet. There are certain init parameters that you can specify in the deployment descriptor (web.xml) file. For example, if a servlet has value >=0 then its init() method is immediately invoked during web container startup.

You can specify the element in web.xml file like this:

<servlet>

 <servlet-name>MyServlet</servlet-name>

 <servlet-class>com.Javabook.MyServletDemo</servlet-class>

 <load-on-startup>1</load-on-startup>

</servlet>

Now the init() method for corresponding servlet class com.Javabook.MyServletDemo would be invoked during web container startup.

Note: The init() method is called only once during the life cycle of servlet.

Step 4: Invoke service() method
Each time the web server receives a request for servlet, it spawns a new thread that calls service() method. If the servlet is GenericServlet then the request is served by the service() method itself, if the servlet is HttpServlet then service() method receives the request and dispatches it to the correct handler method based on the type of request.

For example if its a Get Request the service() method would dispatch the request to the doGet() method by calling the doGet() method with request parameters. Similarly the requests like Post, Head, Put etc. are dispatched to the corresponding handlers doPost(), doHead(), doPut() etc. by service() method of servlet.

# ![](Images/image00451.jpeg)

Note: Unlike init() and destroy() that are called only once, the service() method can be called any number of times during servlet life cycle. As long as servlet is not destroyed, for each client request the service() method is invoked.

Out of all the 5 steps in life cycle, this is the only step that executes multiple times.

Step 5: Invoke destroy() method
When servlet container shuts down(this usually happens when we stop the web server), it unloads all the servlets and calls destroy() method for each initialized servlets.

Note:

Go back from here:

[Servlet Interface](#part0000.xhtml_servletinter)

# Working of Servlet

Before I start explaining how the servlet works, lets get familiar with these three terms.
Web Server: it can handle HTTP Requests send by clients and responds the request with an HTTP Response.

Web Application(webapp): I would refer this as webapp in this guide. Basically the project is your web application, it is the collection of servlets.

Web Container: Also known as Servlet Container and Servlet Engine. It is a part of Web Server that interacts with Servlets. This is the main component of Web Server that manages the life cycle of Servlets.

# You will find that some part of this guide is already covered in the servlet life cycle guide, however this guide focuses on the working of a servlet application (webapp)

# rather than the steps of life cycle. I would highly recommend you to read this to have in depth knowledge of how the servlet actually works.

## How Servlet Works?

1) When the web server (e.g. Apache Tomcat) starts up, the servlet container deploy and loads all the servlets. During this step Servlet container creates ServletContext object. ServletContext is an interface that defines the set of methods that a servlet can use to communicate with the servlet container.

Note: There is only one ServletContext per webapp which is common to all the servlets. ServletContext has several useful methods such as addListener(), addFilter() etc. For now I am not explaining them as I will cover them in a separate text about ServletContext.

2) Once the servlet is loaded, the servlet container creates the instance of servlet class. For each instantiated servlet, its init() method is invoked.

3) Client (user browser) sends an Http request to web server on a certain port. Each time the web server receives a request, the servlet container creates HttpServletRequest and HttpServletResponse objects. The HttpServletRequest object provides the access to the request information and the HttpServletResponse object allows us to format and change the http response before sending it to the client.

The servlet container spawns a new thread that calls service() method for each client request. The service() method dispatches the request to the correct handler method based on the type of request.

For example if server receives a Get Request the service() method would dispatch the request to the doGet() method by calling the doGet() method with request parameters. Similarly the requests like Post, Head, Put etc. are dispatched to the corresponding handlers doPost(), doHead(), doPut() etc. by service() method of servlet.

# ![](Images/image00452.jpeg)

# 4) When servlet container shuts down, it unloads all the servlets and calls destroy() method for each initialized servlets.

# Welcome-file-list tag in web.xml file of Project

Have you ever seen <welcome-file-list> tag in your web.xml file and wondering what it is? In this text, I will explain what is this tag and why we use it.

The tag <welcome-file-list> is used for specifying the files that needs to be invoked by server by default, if you do not specify a file name while loading the project on browser.

For e.g. You have created a project named “MyServletProject” and you have few html pages and servlet classes defined in the project. However in browser you have given the url like this:

http://localhost:8080/MyServletProject

Usually we give the complete path like this:http://localhost:8080/MyServletProject/index.html. However if you have given the path like above then the webserver will look for the <welcome-file-list> tag in your project’s web.xml file. Let say you have the following content in your web.xml file:

<web-app>

....

<welcome-file-list>

 <welcome-file>myhome.htm</welcome-file>

 <welcome-file>myindex.htm</welcome-file>

 <welcome-file>mydefaultpage.htm</welcome-file>

</welcome-file-list>

....

</web-app>

Based on the welcome file list, server would look for the myhome.htm page if this doesn’t exist then the second welcome file myindex.html and so on till it finds a valid welcome file.

Note: If the <welcome-file-list> tag is not defined in web.xml or the welcome files defined in the <welcome-file> tags does not exist then the server would look for the following files in the given sequence:
1) index.html
2) index.htm
3) index.jsp

# Use load-on-startup tag in web.xml file

# How to use load-on-startup tag in web.xml file with Example

By default Servlet is not loaded until servlet container receives a request for the particular servlet. This may cause a delay in accessing the servlet for the first time. To avoid the delay in access time, you can use <load-on-startup> tag in your web.xml file that allows you to force the servlet container to load (instantiated and have its init() called) the servlet as soon as the server starts.

## How to use <load-on-startup>?

Here is a sample web.xml file:

<web-app>

…

<servlet>

<servlet-name>MyServlet</servlet-name>

<servlet-class>com.Javabook.DemoServlet</servlet-class>

<load-on-startup>1</load-on-startup>

</servlet>

…

</web-app>

If I did not specify the <load-on-startup>, the web container would not have loaded the servlet until it receives a request for DemoServlet servlet class. Since I have specified a value >=0, this servlet (DemoServlet class) would be loaded on the startup.

Note:value >= 0 means that the servlet is loaded when the web-app is deployed or when the server starts, if the value < 0 then servlet would be loaded whenever the container feels like.

### How to specify the order of servlet loading using <load-on-startup> tag?

<web-app>

…

<servlet>

<servlet-name>MyServlet1</servlet-name>

<servlet-class>com.Javabook.DemoServlet1</servlet-class>

<load-on-startup>5</load-on-startup>

</servlet>

<servlet>

<servlet-name>MyServlet2</servlet-name>

<servlet-class>com.Javabook.DemoServlet2</servlet-class>

<load-on-startup>0</load-on-startup>

</servlet>

<servlet>

<servlet-name>MyServlet3</servlet-name>

<servlet-class>com.Javabook.DemoServlet3</servlet-class>

<load-on-startup>-2</load-on-startup>

</servlet>

…

</web-app>

In this example we have three Servlets specified in the web.xml file, since servlet classes DemoServlet1 and DemoServlet2 has load-on-startup value >=0, they both will be loaded as soon as the server starts. However servlet class DemoServlet2 would be loaded before the DemoServlet1 class because it has lower load-on-startup value.

Servlet class DemoServlet3 would not be loaded on startup as it has negative load-on-startup value.

# ServletRequest Interface

# ServletRequest Interface with example

When a client sends a request to the web server, the servlet container creates ServletRequest & ServletResponse objects and passes them as an argument to the servlet’s service() method. The request object provides the access to the request information such as header and body information of request data.

First we will see an example and then we will see the list of methods available in the ServletRequest interface:

## Example 1: ServletRequest getParameter() method to display the user input

In this example I am demonstrating the use of getParameter() method that returns the value of the given parameter.

In this html form, we are taking user input (name and age) and storing them in the parameters uname and uage respectively.
index.html

<form  action="details"  method="get">

User Name: <input  type="text"  name="uname"><br>

User Age: <input  type="text"  name="uage"><br>

 <input  type="submit"  value="submit">

</form>

MyServletDemo.java
In this servlet class we are getting the value of the parameters by using getParameter() method, this method belongs to the ServletRequest interface. In this example we have HttpServletRequest as a parameter of doGet() method, HttpServletRequest extends ServletRequest interface thats why the getParameter() method is available to the req object.

After getting the values, we are writing them on the webpage.

import javax.servlet.http.*;

import javax.servlet.*;

import java.io.*;

public  class  MyServletDemo  extends  HttpServlet{

 public  void doGet(HttpServletRequest req,HttpServletResponse res)

 throws  ServletException,IOException

   { 

     res.setContentType("text/html");

 PrintWriter pwriter=res.getWriter();

 String name = req.getParameter("uname");

 String age = req.getParameter("uage");

     pwriter.println("Name: "+name);

     pwriter.println("Age: "+age);

     pwriter.close();

  }

}

Web.xml
This is your deployment descriptor file that maps the servlet to the url. Since our form has details page as action, we mapped the servlet class to the details page.

<web-app>

<display-name>JavaBookDemo</display-name>

 <welcome-file-list>

 <welcome-file>index.html</welcome-file>

 <welcome-file>index.htm</welcome-file>

 <welcome-file>index.jsp</welcome-file>

 <welcome-file>default.html</welcome-file>

 <welcome-file>default.htm</welcome-file>

 <welcome-file>default.jsp</welcome-file>

 </welcome-file-list>

<servlet>

 <servlet-name>JavaBook</servlet-name>

 <servlet-class>MyServletDemo</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>JavaBook</servlet-name>

 <url-pattern>/details</url-pattern>

</servlet-mapping>

</web-app>

Output:
Screen 1:

# ![](Images/image00453.jpeg)

# Screen 2 that appears upon clicking submit:

# ![](Images/image00454.jpeg)

## Example 2: Getting parameter names and values

In this example, we will be using getParameterNames() and getParameter() methods to get parameter names and values.

getParameterNames(): Returns an Enumeration of String objects containing the names of the parameters contained in this request. If the request has no parameters, the method returns an empty Enumeration.

getParameter(): As mentioned above, this returns the value of given parameter.

index.html

<form  action="details"  method="get">

User Name: <input  type="text"  name="uname"><br>

User Age: <input  type="text"  name="uage"><br>

 <input  type="submit"  value="submit">

</form>

MyServletDemo.class

import java.io.IOException;

import java.io.IOException;

import java.io.PrintWriter;

import java.util.Enumeration; 

import javax.servlet.ServletException;

import javax.servlet.http.HttpServlet;

import javax.servlet.http.HttpServletRequest;

import javax.servlet.http.HttpServletResponse;

public  class  MyServletDemo  extends  HttpServlet{    

 public  void doGet(HttpServletRequest req,HttpServletResponse res)

 throws  ServletException,IOException    

   {    

 PrintWriter pwriter=res.getWriter(); res.setContentType("text/html");

 Enumeration en=req.getParameterNames();

 while(en.hasMoreElements())

      {

 Object obj=en.nextElement();

 String param=(String)obj;

 String pvalue=req.getParameter(param);

          pwriter.print("Parameter Name: "+param+  

 " Parameter Value: "+pvalue);

      }

      pwriter.close();  

    }

}

web.xml

<web-app>

<servlet>

 <servlet-name>JavaBook</servlet-name>

 <servlet-class>MyServletDemo</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>JavaBook</servlet-name>

 <url-pattern>/details</url-pattern>

</servlet-mapping>

</web-app>

Output:

# ![](Images/image00455.jpeg)

# Parameter Name:uname Parameter Value:ChandruParameter Name:uage Parameter Value:30

## Example 3: Display Header information

index.html

<h1>Servlet Request Demo</h1>

<body>

<a  href="headinfo">Click Here</a>

</body>

HeaderDetails.java

import java.io.IOException;

import java.io.PrintWriter;

import java.util.Enumeration;

import javax.servlet.ServletException;

import javax.servlet.http.HttpServlet;

import javax.servlet.http.HttpServletRequest;

import javax.servlet.http.HttpServletResponse;

public  class  HeaderDetails  extends  HttpServlet {

 public  void doGet(HttpServletRequest request,

 HttpServletResponse response)

 throws  IOException, ServletException

  {

     response.setContentType("text/html");

 PrintWriter pwriter = response.getWriter();

     pwriter.println("HTTP header Information:<br>");

 Enumeration en = request.getHeaderNames();

 while (en.hasMoreElements()) {

 String hName = (String) en.nextElement();

 String hValue = request.getHeader(hName);

        pwriter.println("<b>"+hName+": </b>"

+hValue + "<br>");

     }

  }

}

web.xml

<web-app>

<welcome-file-list>

 <welcome-file>index.html</welcome-file>

 <welcome-file>index.htm</welcome-file>

 <welcome-file>index.jsp</welcome-file>

 <welcome-file>default.html</welcome-file>

 <welcome-file>default.htm</welcome-file>

 <welcome-file>default.jsp</welcome-file>

 </welcome-file-list>

 <servlet>

 <servlet-name>JavaBook</servlet-name>

 <servlet-class>HeaderDetails</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>JavaBook</servlet-name>

 <url-pattern>/headinfo</url-pattern>

</servlet-mapping>

</web-app>

Output:

# ![](Images/image00456.jpeg)

# ![](Images/image00457.jpeg)

## Methods of ServletRequest interface

String getParameter(String name): It returns the value of the given parameter as String or null if the given parameter does not exist.

Enumeration getParameterNames(): It returns an Enumeration of Strings objects containing the names of parameters in the request.

String[] getParameterValues(String name): It returns an array of Strings containing the all the values, the parameters has, returns null if parameter doesn’t have any value.

String getCharacterEncoding(): Returns the name of the character encoding used in the body of this request. This method returns null if the request does not specify a character encoding.

void setCharacterEncoding(String env): Overrides the character encoding in the body of the request.

int getContentLength(): Returns the length of the request content in bytes.

String getContentType(): Returns the MIME type of the body of the request, or null if the type is not known.

# RequestDispatcher methods

# RequestDispatcher methods with examples in Servlet

The RequestDispatcher interface defines an object that receives the request from client and dispatches it to the resource(such as servlet, JSP, HTML file). This interface has following two methods:

public void forward(ServletRequest request, ServletResponse response): It forwards the request from one servlet to another resource (such as servlet, JSP, HTML file).

public void include(ServletRequest request, ServletResponse response): It includes the content of the resource(such as servlet, JSP, HTML file) in the response.

## Difference between forward() vs include() method

To understand the difference between these two methods, let us take an example: Suppose you have two pages X and Y. In page X you have an include tag, this means that the control will be in the page X till it encounters include tag, after that the control will be transferred to page Y. At the end of the processing of page Y, the control will return back to the page X starting just after the include tag and remain in X till the end.
In this case the final response to the client will be send by page X.

Now, we are taking the same example with forward. We have same pages X and Y. In page X, we have forward tag. In this case the control will be in page X till it encounters forward, after this the control will be transferred to page Y. The main difference here is that the control will not return back to X, it will be in page Y till the end of it.

In this case the final response to the client will be send by page Y.

## Example:

In this example, I will be using both the methods include and forward. Using include method, I will be changing the content of current page and when I’m ready to transfer the control to the next page, I will use forward method.

index.html

<form  action="loginPage"  method="post">

  User Name:<input  type="text"  name="uname"/><br/>

  Password:<input  type="password"  name="upass"/><br/>

 <input  type="submit"  value="SUBMIT"/>

</form>

Validation.java

import java.io.*;

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  Validation  extends  HttpServlet

{    

 public  void doPost(HttpServletRequest request,

 HttpServletResponse response)

 throws  ServletException, IOException

   {       

       response.setContentType("text/html");     

 PrintWriter pwriter = response.getWriter();

 String name=request.getParameter("uname");     

 String  pass=request.getParameter("upass");               

 if(name.equals("Chandru") &&

 pass.equals("Javabook"))

       {         

 RequestDispatcher dis=request.getRequestDispatcher("welcome");         

          dis.forward(request, response);     

       }     

 else

       {     

          pwriter.print("User name or password is incorrect!");         

 RequestDispatcher dis=request.getRequestDispatcher("index.html");         

          dis.include(request, response);                               

       }     

   }    

}  

WelcomeUser.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  WelcomeUser  extends  HttpServlet {

 public  void doPost(HttpServletRequest request,

 HttpServletResponse response)

 throws  ServletException, IOException

 {

    response.setContentType("text/html");

 PrintWriter pwriter = response.getWriter();

 String name=request.getParameter("uname");

    pwriter.print("Hello "+name+"!");

    pwriter.print(" Welcome to Javabook.com");

 }

}

web.xml

<web-app>

 <display-name>JavaBookDemo</display-name>

 <welcome-file-list>

 <welcome-file>index.html</welcome-file>

 </welcome-file-list>

 <servlet>

 <servlet-name>Login</servlet-name>

 <servlet-class>Validation</servlet-class>

 </servlet>

 <servlet>

 <servlet-name>Welcome</servlet-name>

 <servlet-class>WelcomeUser</servlet-class>

 </servlet>

 <servlet-mapping>

 <servlet-name>Login</servlet-name>

 <url-pattern>/loginPage</url-pattern>

 </servlet-mapping>

 <servlet-mapping>

 <servlet-name>Welcome</servlet-name>

 <url-pattern>/welcome</url-pattern>

 </servlet-mapping>

 <welcome-file-list>

 <welcome-file>index.html</welcome-file>

 </welcome-file-list>

</web-app>

Output:
Entering wrong credentials:

![](Images/image00458.jpeg)

Error screen:

# ![](Images/image00459.jpeg)

# Welcome screen on entering correct user name and password:

# Hello Chandru Ị Welcome to javabook.com

ServletConfig Interface

# ServletConfig Interface with example

Servlet Container creates ServletConfig object for each Servlet during initialization, to pass information to the Servlet. This object can be used to get configuration information such as parameter name and values from deployment descriptor file(web.xml).

## Methods of ServletConfig interface

public String getInitParameter(String name): Returns the value of given parameter as String, or null if the given parameter doesn’t exist in web.xml.

public Enumeration getInitParameterNames(): Returns an enumeration of all the parameter names.

public String getServletName(): Returns the name of the servlet instance.

public ServletContext getServletContext(): Returns an object of ServletContext.

## Example:

In this example, we will use two methods getInitParameter() and getInitParameterNames() to get all the parameters from web.xml along with their values.

The getInitParameterNames() method returns an enumeration of all parameters names and by passing those names during the call of getInitParameter() method, we can get the corresponding parameter value from web.xml.

DemoServlet.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

import java.util.Enumeration;

public  class  DemoServlet  extends  HttpServlet {

 protected  void doGet(HttpServletRequest request,

 HttpServletResponse response)

 throws  ServletException, IOException

   {

      response.setContentType("text/html;charset=UTF-8");

 PrintWriter pwriter = response.getWriter();

 ServletConfig sc=getServletConfig();

 Enumeration<String> e=sc.getInitParameterNames();

 String str;

 while(e.hasMoreElements()) {

        str=e.nextElement();

        pwriter.println("<br>Param Name: "+str);

        pwriter.println(" value: "+sc.getInitParameter(str));

      }

   }

}

web.xml

<web-app>

 <display-name>JavaBookDemo</display-name>

 <welcome-file-list>

 <welcome-file>index.html</welcome-file>

 </welcome-file-list>

 <servlet>

 <servlet-name>MyServlet</servlet-name>

 <servlet-class>DemoServlet</servlet-class>

 <init-param>

 <param-name>MyName</param-name>

 <param-value>Chandru</param-value>

 </init-param>

 <init-param>

 <param-name>MyWebsite</param-name>

 <param-value>Javabook.com</param-value>

 </init-param>

 </servlet>

 <servlet-mapping>

 <servlet-name>MyServlet</servlet-name>

 <url-pattern>/scdemo</url-pattern>

 </servlet-mapping>

</web-app>

Output:

Param name:My name value:chandru

Param Name:My Website value:Javabook.com

# ServletContext Interface

The main difference between ServletConfig and ServletContext is that unlike ServletConfig, the ServletContext is being created once per web application, i.e. ServletContext object is common to all the servlets in web application.

This is how we can create ServletContext object. In this code we are creating object in init() method, however you can create the object anywhere you like.

ServletContext sc;

public  void init(ServletConfig scfg)

{

    sc=scfg.getServletContext();

}

Once we have the ServletContext object, we can set the attributes of the ServletContext object by using the setAttribute() method. Since the ServletContext object is available to all the servlets of the Web application, other servlets can retrieve the attribute from the ServletContext object by using the getAttribute() method.

Context Initialization Parameter

Context Initialization parameters are the parameter name and value pairs that you can specify in the deployment descriptor file (the web.xml file). Here you can specify the parameters that will be accessible to all the servlets in the web application.

When we deploy the Web application, the Servlet container reads the initialization parameter from the web.xml file and initializes the ServletContext object with it. We can use the getInitParameter()and getInitParameterNames() methods of the ServletContext interface to get the parameter value and enumeration of parameter names respectively.

For example, here I have specified the parameter email_id with the value, since this is common to all the servlets, you can get the parameter name and value in any servlet.

<context-param>

<param-name>email_id</param-name>

<param-value>javabook@gmail.com</param-value>

</context-param>

#### ServletContext complete example: To get the initialization parameters

In this example we have two context initialization parameters (user name and user email) in web.xml file and we are getting the value in Servlet using getInitParameter() method that returns the value of given parameter.

DemoServlet.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  DemoServlet  extends  HttpServlet{

 public  void doGet(HttpServletRequest request,HttpServletResponse response)

 throws  ServletException,IOException

   {

       response.setContentType("text/html");

 PrintWriter pwriter=response.getWriter();

 //ServletContext object creation

 ServletContext scontext=getServletContext();

 //fetching values of initialization parameters and printing it

 String userName=scontext.getInitParameter("uname");

       pwriter.println("User name is="+userName);

 String userEmail=scontext.getInitParameter("email");

       pwriter.println("Email Id is="+userEmail);

       pwriter.close();

   }

}

web.xml

<web-app>

<servlet>

 <servlet-name>JavaBook</servlet-name>

 <servlet-class>DemoServlet</servlet-class>

</servlet>

<context-param>

 <param-name>uname</param-name>

 <param-value>Chandruprasad</param-value>

</context-param>

<context-param>

 <param-name>email</param-name>

 <param-value>javabook@gmail.com</param-value>

</context-param>

<servlet-mapping>

 <servlet-name>JavaBook</servlet-name>

 <url-pattern>/context</url-pattern>

 </servlet-mapping>

</web-app>

Output:

User name is:Chandruprasad Email Is is:Javabook@gmail.com

## Methods of ServletContext interface

Here is the list of frequently used methods of ServletContext interface.

public String getInitParameter(String param): It returns the value of given parameter or null if the parameter doesn’t exist.

public Enumeration getInitParameterNames(): Returns an enumeration of context parameters names.

public void setAttribute(String name,Object object): Sets the attribute value for the given attribute name.

public Object getAttribute(String name):Returns the attribute value for the given name or null if the attribute doesn’t exist.

public String getServerInfo(): eturns the name and version of the servlet container on which the servlet is running.

public String getContextPath(): Returns the context path of the web application.

# ServletResponse Interface

The servlet container is connected to the web server that receives Http Requests from client on a certain port. When client sends a request to web server, the servlet container creates HttpServletRequest and HttpServletResponse objects and passes them as an argument to the servlet service() method.

The response object allows you to format and send the response back to the client. First we will see the commonly used methods in the ServletReponse interface and then we will see an example.

## Method of ServletResponse interface

1) String getCharacterEncoding(): It returns the name of the MIME charset used in body of the response sent to the client.

2) String getContentType(): It returns the response content type. e.g. text, html etc.

3) ServletOutputStream getOutputStream(): Returns a ServletOutputStream suitable for writing binary data in the response.

4) java.io.PrintWriter getWriter(): Returns the PrintWriter object.

5) void setCharacterEncoding(java.lang.String charset): Set the MIME charset (character encoding) of the response.

6) void setContentLength(int len): It sets the length of the response body.

7) void setContentType(java.lang.String type): Sets the type of the response data.

8) void setBufferSize(int size): Sets the buffer size.

9) int getBufferSize(): Returns the buffer size.

10) void flushBuffer(): Forces any content in the buffer to be written to the client.

11) boolean isCommitted(): Returns a boolean indicating if the response has been committed.

12) void reset(): Clears the data of the buffer along with the headers and status code.

## Example:

In the below example, we have used setContentType() and getWriter() methods of ServletResponse interface.

index.html

<form  action="mydetails"  method="get">

User name: <input  type="text"  name="uname">

<input  type="submit"  value="login">

</form>

MyServletDemo.java

import javax.servlet.http.*;

import javax.servlet.*;

import java.io.*;

public  class  MyServletDemo  extends  HttpServlet{

 public  void doGet(HttpServletRequest req,HttpServletResponse res)

 throws  ServletException,IOException

   {

     res.setContentType("text/html");

 PrintWriter pwriter=res.getWriter();

 String name=req.getParameter("uname");

     pwriter.println("User Details Page:");

     pwriter.println("Hello "+name);

     pwriter.close();

  }

}

web.xml

<web-app>

<servlet>

 <servlet-name>DemoServlet</servlet-name>

 <servlet-class>MyServletDemo</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>DemoServlet</servlet-name>

 <url-pattern>/mydetails</url-pattern>

</servlet-mapping>

</web-app>

Output:

User name:Chandrurasad

# ![](Images/image00460.jpeg)

# Screen 2:

# User Details Page:Hello Chandruprsad

# HttpSession

# HttpSession with example in Servlet

The HttpSession object is used for session management. A session contains information specific to a particular user across the whole application. When a user enters into a website (or an online application) for the first time HttpSession is obtained via request.getSession(), the user is given a unique ID to identify his session. This unique ID can be stored into a cookie or in a request parameter.

The HttpSession stays alive until it has not been used for more than the timeout value specified in tag in deployment descriptor file( web.xml). The default timeout value is 30 minutes, this is used if you don’t specify the value in tag. This means that when the user doesn’t visit web application time specified, the session is destroyed by servlet container. The subsequent request will not be served from this session anymore, the servlet container will create a new session.

This is how you create a HttpSession object.

protected  void doPost(HttpServletRequest req,

 HttpServletResponse res)

 throws  ServletException, IOException {

 HttpSession session = req.getSession();

}

You can store the user information into the session object by using setAttribute() method and later when needed this information can be fetched from the session. This is how you store info in session. Here we are storing username, emailid and userage in session with the attribute name uName, uemailId and uAge respectively.

session.setAttribute("uName", "ChandruPrasad");

session.setAttribute("uemailId", "myemailid@gmail.com");

session.setAttribute("uAge", "30");

This First parameter is the attribute name and second is the attribute value. For e.g. uName is the attribute name and ChandruPrasad is the attribute value in the code above.

TO get the value from session we use the getAttribute() method of HttpSession interface. Here we are fetching the attribute values using attribute names.

String userName = (String) session.getAttribute("uName");

String userEmailId = (String) session.getAttribute("uemailId");

String userAge = (String) session.getAttribute("uAge");

## Methods of HttpSession

public void setAttribute(String name, Object value): Binds the object with a name and stores the name/value pair as an attribute of the HttpSession object. If an attribute already exists, then this method replaces the existing attributes.

public Object getAttribute(String name): Returns the String object specified in the parameter, from the session object. If no object is found for the specified attribute, then the getAttribute() method returns null.

public Enumeration getAttributeNames(): Returns an Enumeration that contains the name of all the objects that are bound as attributes to the session object.

public void removeAttribute(String name): Removes the given attribute from session.

setMaxInactiveInterval(int interval): Sets the session inactivity time in seconds. This is the time in seconds that specifies how long a sessions remains active since last request received from client.

## Session Example

index.html

<form  action="login">

  User Name:<input  type="text"  name="userName"/><br/>

  Password:<input  type="password"  name="userPassword"/><br/>

 <input  type="submit"  value="submit"/>

</form>

MyServlet1.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  MyServlet1  extends  HttpServlet {

 public  void doGet(HttpServletRequest request, HttpServletResponse response){

 try{

      response.setContentType("text/html");

 PrintWriter pwriter = response.getWriter();

 String name = request.getParameter("userName");

 String password = request.getParameter("userPassword");

      pwriter.print("Hello "+name);

      pwriter.print("Your Password is: "+password);

 HttpSession session=request.getSession();

      session.setAttribute("uname",name);

      session.setAttribute("upass",password);

      pwriter.print("<a href='welcome'>view details</a>");

      pwriter.close();

    }catch(Exception exp){

 System.out.println(exp);

     }

  }

}

MyServlet2.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  MyServlet2  extends  HttpServlet {

 public  void doGet(HttpServletRequest request, HttpServletResponse response){

 try{

      response.setContentType("text/html");

 PrintWriter pwriter = response.getWriter();

 HttpSession session=request.getSession(false);

 String myName=(String)session.getAttribute("uname");

 String myPass=(String)session.getAttribute("upass");

      pwriter.print("Name: "+myName+" Pass: "+myPass);

      pwriter.close();

  }catch(Exception exp){

 System.out.println(exp);

   }

  }

}

web.xml

<web-app>

<servlet>

 <servlet-name>Servlet1</servlet-name>

 <servlet-class>MyServlet1</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>Servlet1</servlet-name>

 <url-pattern>/login</url-pattern>

</servlet-mapping>

<servlet>

 <servlet-name>Servlet2</servlet-name>

 <servlet-class>MyServlet2</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>Servlet2</servlet-name>

 <url-pattern>/welcome</url-pattern>

</servlet-mapping>

</web-app>

Output:
First Screen:

# ![](Images/image00461.jpeg)

# After clicking Submit:

# Hello Chandru Your Password is;chandruview details

# After clicking view details:

# Name:Chandru Pass:chandru

# Cookies in Servlet

# Cookies in Servlet with example

Here we will discuss Cookies which is also used for session management. Let’s recall few things here from last tutorial so that we can relate sessions and cookies. When a user visits web application first time, the servlet container crates new HttpSession object by calling request.getSession(). A unique Id is assigned to the session. The Servlet container also sets a Cookie in the header of the HTTP response with cookie name and the unique session ID as its value.

The cookie is stored in the user browser, the client (user’s browser) sends this cookie back to the server for all the subsequent requests until the cookie is valid. The Servlet container checks the request header for cookies and get the session information from the cookie and use the associated session from the server memory.

The session remains active for the time specified in tag in web.xml. If tag in not set in web.xml then the session remains active for 30 minutes. Cookie remains active as long as the user’s browser is running, as soon as the browser is closed, the cookie and associated session info is destroyed. So when the user opens the browser again and sends request to web server, the new session is being created.

## Types of Cookies

We can classify the cookie based on their expiry time:

1.  Session
2.  Persistent

1)SessionCookies:
Session cookies do not have expiration time. It lives in the browser memory. As soon as the web browser is closed this cookie gets destroyed.

2)Persistent Cookies:
Unlike Session cookies they have expiration time, they are stored in the user hard drive and gets destroyed based on the expiry time.

## How to send Cookies to the Client

Here are steps for sending cookie to the client:

1.  Create a Cookie object.
2.  Set the maximum Age.
3.  Place the Cookie in HTTP response header.

#### 1) Create a Cookie object:

Cookie c = new  Cookie("userName","Chandru");

#### 2) Set the maximum Age:

By using setMaxAge () method we can set the maximum age for the particular cookie in seconds.

c.setMaxAge(1800);

#### 3) Place the Cookie in HTTP response header:

We can send the cookie to the client browser through response.addCookie() method.

response.addCookie(c);

## How to read cookies

Cookie c[]=request.getCookies();

//c.length gives the cookie count

for(int i=0;i<c.length;i++){ 

 out.print("Name: "+c[i].getName()+" & Value: "+c[i].getValue());

}

## Example of Cookies in java servlet

index.html

<form  action="login">

User Name:<input  type="text"  name="userName"/><br/>

Password:<input  type="password"  name="userPassword"/><br/>

 <input  type="submit"  value="submit"/>

</form>

MyServlet1.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  MyServlet1  extends  HttpServlet

{

 public  void doGet(HttpServletRequest request,

 HttpServletResponse response) {

 try{

          response.setContentType("text/html");

 PrintWriter pwriter = response.getWriter();

 String name = request.getParameter("userName");

 String password = request.getParameter("userPassword");

          pwriter.print("Hello "+name);

          pwriter.print("Your Password is: "+password);

 //Creating two cookies

 Cookie c1=new  Cookie("userName",name);

 Cookie c2=new  Cookie("userPassword",password);

 //Adding the cookies to response header

          response.addCookie(c1);

          response.addCookie(c2);

          pwriter.print("<br><a href='welcome'>View Details</a>");

          pwriter.close();

   }catch(Exception exp){

 System.out.println(exp);

    }

  }

}

MyServlet2.java

import java.io.*;

import javax.servlet.*;

import javax.servlet.http.*;

public  class  MyServlet2  extends  HttpServlet {

 public  void doGet(HttpServletRequest request,

 HttpServletResponse response){

 try{

       response.setContentType("text/html");

 PrintWriter pwriter = response.getWriter();

 //Reading cookies

 Cookie c[]=request.getCookies();

 //Displaying User name value from cookie

       pwriter.print("Name: "+c[1].getValue());

 //Displaying user password value from cookie

       pwriter.print("Password: "+c[2].getValue());

       pwriter.close();

    }catch(Exception exp){

 System.out.println(exp);

     }

  }

}

web.xml

<web-app>

<display-name>JavaBookDemo</display-name>

 <welcome-file-list>

 <welcome-file>index.html</welcome-file>

 </welcome-file-list>

<servlet>

 <servlet-name>Servlet1</servlet-name>

 <servlet-class>MyServlet1</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>Servlet1</servlet-name>

 <url-pattern>/login</url-pattern>

</servlet-mapping>

<servlet>

 <servlet-name>Servlet2</servlet-name>

 <servlet-class>MyServlet2</servlet-class>

</servlet>

<servlet-mapping>

 <servlet-name>Servlet2</servlet-name>

 <url-pattern>/welcome</url-pattern>

</servlet-mapping>

</web-app>

Output:
Welcome Screen:

![](Images/image00462.jpeg)

After clicking Submit:

Hello Chandruprasad your Password is:Javabook View Details

After clicking View Details:

Name:ChandruprasadPassword:Javabook

## Methods of Cookie class

public void setComment(String purpose): This method is used for setting up comments in the cookie. This is basically used for describing the purpose of the cookie.

public String getComment(): Returns the comment describing the purpose of this cookie, or null if the cookie has no comment.

public void setMaxAge(int expiry): Sets the maximum age of the cookie in seconds.

public int getMaxAge(): Gets the maximum age in seconds of this Cookie.
By default, -1 is returned, which indicates that the cookie will persist until browser shutdown.

public String getName(): Returns the name of the cookie. The name cannot be changed after creation.

public void setValue(String newValue): Assigns a new value to this Cookie.

public String getValue(): Gets the current value of this Cookie.