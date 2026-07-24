![](Image00001.jpg)

Copyright © All rights reserved

No part of this book may be reproduced, or stored in a retrieval system, or transmitted in any form or by any means, electronic, mechanical, photocopying, recording, or otherwise, without express written permission of the publisher.

I would like to dedicate the book to the students who will be using it. I wish you future career success and hope you never stop learning.

TABLE OF CONTENT

[Overview](#text00003.html_id_Toc72405791)

[Environment Setup](#text00004.html_id_Toc72405792)

[Basic Mapping](#text00005.html_id_Toc72405793)

[Custom Mapping](#text00006.html_id_Toc72405794)

[Mapping Multiple Objects](#text00007.html_id_Toc72405795)

[Mapping Nested Bean](#text00008.html_id_Toc72405796)

[Mapping Direct Fields](#text00009.html_id_Toc72405797)

[Using Builder](#text00010.html_id_Toc72405798)

[Implicit Type Conversion](#text00011.html_id_Toc72405799)

[Using number Format](#text00012.html_id_Toc72405800)

[Using date Format](#text00013.html_id_Toc72405801)

[Using expression](#text00014.html_id_Toc72405802)

[Using constant](#text00015.html_id_Toc72405803)

[Using default Value](#text00016.html_id_Toc72405804)

[Using default Expression](#text00017.html_id_Toc72405805)

[Mapping List](#text00018.html_id_Toc72405806)

[Mapping Map](#text00019.html_id_Toc72405807)

[Mapping Stream](#text00020.html_id_Toc72405808)

[Mapping Enum](#text00021.html_id_Toc72405809)

[Throwing Exception](#text00022.html_id_Toc72405810)

[Using Custom Mapper](#text00023.html_id_Toc72405811)

# Overview

MapStruct is an annotation processor which is plugged into Java Compiler. Once plugged in, it can be used by command line tools like maven, gradle to process the mapping annotation to create a mapper class at compile time.

## When Mapping is required?

In multilayered applications, data objects are used to fetch data from database and UI interacts with Models. Now data fetched into data models is required to map to Model or java beans to be passed to UI.Consider the following case.

Entity class connected with database.

StudentEntity.java

@Entity

class StudentEntity {

String id ;

String name ;

}

Model class connected with UI.

Student.java

class Student {

String id ;

String name ;

}

## How MapStruct Works?

MapStruct automates the process of creating a mapper to map data objects with model objects using annotations. It creates a mapper implementation at compile time which helps developer to figure out error during development and make is easy to understand. For example −

StudentMapper.java

@Mapper

class StudentMapper {

StudentMapper INSTANCE = Mappers . getMapper ( StudentMapper . class );

StudentEntity modelToEntity ( Student student );

}

Now StudentMapper.INSTANCE can be used to get mapped objects easily.

StudentEntity studentEntity = StudentMapper.INSTANCE.modelToEntity(student);

# Environment Setup

MapStruct is a Java based library, so the very first requirement is to have JDK installed on your machine.

## Step 1 - Setup Java Development Kit (JDK)

You can download the latest version of SDK from Oracle's Java site − **Java SE Downloads.**  You will find instructions for installing JDK in downloaded files, follow the given instructions to install and configure the setup. Finally set PATH and JAVA_HOME environment variables to refer to the directory that contains java and javac, typically java_install_dir/bin and java_install_dir respectively.

If you are running Windows and have installed the JDK in C:\jdk-9.0.1, you would have to put the following line in your C:\autoexec.bat file.

set PATH=C:\jdk-9.0.1\bin;%PATH%

set JAVA_HOME=C:\jdk-9.0.1

Alternatively, on Windows NT/2000/XP, you will have to right-click on My Computer, select Properties → Advanced → Environment Variables. Then, you will have to update the PATH value and click the OK button.

On Unix (Solaris, Linux, etc.), if the SDK is installed in /usr/local/jdk-9.0.1 and you use the C shell, you will have to put the following into your .cshrc file.

setenv PATH /usr/local/jdk-9.0.1/bin:$PATH

setenv JAVA_HOME /usr/local/jdk-9.0.1

Alternatively, if you use an Integrated Development Environment (IDE) like Borland JBuilder, Eclipse, IntelliJ IDEA, or Sun ONE Studio, you will have to compile and run a simple program to confirm that the IDE knows where you have installed Java. Otherwise, you will have to carry out a proper setup as given in the document of the IDE.

## Step 2 - Install mapstruct library along with dependencies

Download following jars from **MVNRepository**  and use them in your classpath.

*   mapstruct-1.3.1.Final.jar
*   mapstruct-processor-1.3.1.Final.jar

Make sure you set your CLASSPATH variable on this directory properly otherwise you will face a problem while running your application.

## Step 3 - Setup Eclipse IDE

All the examples in this tutorial have been written using Eclipse IDE. So we would suggest you should have the latest version of Eclipse installed on your machine.

To install Eclipse IDE, download the latest Eclipse binaries from **https://www.eclipse.org/downloads/** . Once you download the installation, unpack the binary distribution into a convenient location. For example, in C:\eclipse on Windows, or /usr/local/eclipse on Linux/Unix and finally set PATH variable appropriately.

Eclipse can be started by executing the following commands on Windows machine, or you can simply double-click on eclipse.exe

%C:\eclipse\eclipse.exe

Eclipse can be started by executing the following commands on Unix (Solaris, Linux, etc.) machine −

$/usr/local/eclipse/eclipse

After a successful startup, if everything is fine then it should display the following result −

![Image](Image00000.jpg)

## Step 4 - Create a Maven Project

C:\MVN>mvn archetype:generate

-DgroupId = com.tutorialspoint.mapping

-DartifactId = mapping

-DarchetypeArtifactId = maven-archetype-quickstart

-DinteractiveMode = false

It will create a maven project. Now update the pom.xml file as follows −

<project xmlns = "http://maven.apache.org/POM/4.0.0" xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation = "http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd" >

<modelVersion> 4.0.0 </modelVersion>

<groupId> com.tutorialspoint.mapping </groupId>

<artifactId> mapping </artifactId>

<packaging> jar </packaging>

<version> 1.0-SNAPSHOT </version>

<name> mapping </name>

<url> http://maven.apache.org </url>

<dependencies>

<dependency>

<groupId> org.junit.jupiter </groupId>

<artifactId> junit-jupiter-engine </artifactId>

<version> 5.0.0 </version>

<scope> test </scope>

</dependency>

<dependency>

<groupId> org.mapstruct </groupId>

<artifactId> mapstruct </artifactId>

<version> 1.3.1.Final </version>

</dependency>

</dependencies>

<build>

<plugins>

<plugin>

<groupId> org.apache.maven.plugins </groupId>

<artifactId> maven-compiler-plugin </artifactId>

<version> 3.8.1 </version>

<configuration>

<source> 1.9 </source>

<target> 1.9 </target>

<annotationProcessorPaths>

<path>

<groupId> org.mapstruct </groupId>

<artifactId> mapstruct-processor </artifactId>

<version> 1.3.1.Final </version>

</path>

</annotationProcessorPaths>

</configuration>

</plugin>

</plugins>

</build>

</project>

Run the following command to update maven dependencies and build project.

mvn package

Once command is successful. Import the maven based mediaplayer project in Eclipse as a maven project. Rest Eclipse will handle.

# Basic Mapping

Using mapstruct is very easy. To create a mapper use **org.mapstruct.Msapper**  annotation on an interface.

@Mapper

public interface StudentMapper {...}

Now create a conversion method in interface.

@Mapper

public interface StudentMapper {

Student getModelFromEntity ( StudentEntity student );

}

In case both source and target object properties have same name, those properties will be mapped automatically. In case property name is different, use the @Mapping annotation as following −

@Mapper

public interface StudentMapper {

@Mapping ( target = "className" , source = "classVal" )

Student getModelFromEntity ( StudentEntity student );

}

Here className is the property name in Student, a target object and classVal is the property name in StudentEntity, a source object.

## Example

Open project mapping as created in **Environment Setup**  chapter in Eclipse.

Create Student.java with following code −

Student.java

package com . tutorialspoint . model ;

public class Student {

private int id ;

private String name ;

private String className ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassName () {

return className ;

}

public void setClassName ( String className ) {

this . className = className ;

}

}

Create Student.java with following code −

StudentEntity.java

package com . tutorialspoint . entity ;

public class StudentEntity {

private int id ;

private String name ;

private String classVal ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassVal () {

return classVal ;

}

public void setClassVal ( String classVal ) {

this . classVal = classVal ;

}

}

Create StudentMapper.java with following code −

StudentMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . model . Student ;

@Mapper

public interface StudentMapper {

@Mapping ( target = "className" , source = "classVal" )

Student getModelFromEntity ( StudentEntity student );

@Mapping ( target = "classVal" , source = "className" )

StudentEntity getEntityFromModel ( Student student );

}

Create StudentMapperTest.java with following code −

StudentMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . mapper . StudentMapper ;

import com . tutorialspoint . model . Student ;

public class StudentMapperTest {

private StudentMapper studentMapper = Mappers . getMapper ( StudentMapper . class );

@Test

public void testEntityToModel () {

StudentEntity entity = new StudentEntity ();

entity . setClassVal ( "X" );

entity . setName ( "John" );

entity . setId ( 1 );

Student model = studentMapper . getModelFromEntity ( entity );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

}

@Test

public void testModelToEntity () {

Student model = new Student ();

model . setId ( 1 );

model . setName ( "John" );

model . setClassName ( "X" );

StudentEntity entity = studentMapper . getEntityFromModel ( model );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.004 sec

...

# Custom Mapping

We can add custom methods as well to the Mapper created using **org.mapstruct.Mapper**  annotation. We can create abstract class as well intead of an Interface. Mapstruct automatically creates the corresponding mapper class.

Now create a default conversion method in interface.

@Mapper

public interface StudentMapper {

default Student getModelFromEntity ( StudentEntity studentEntity ){

Student student = new Student ();

student . setId ( studentEntity . getId ());

student . setName ( studentEntity . getName ());

student . setClassName ( studentEntity . getClassVal ());

return student ;

}

}

In similar fashion, we can create an abstract class as well as a mapper.

@Mapper

public absgract class StudentMapper {

Student getModelFromEntity ( StudentEntity studentEntity ){

Student student = new Student ();

student . setId ( studentEntity . getId ());

student . setName ( studentEntity . getName ());

student . setClassName ( studentEntity . getClassVal ());

return student ;

}

}

## Example

Open project mapping as updated in **Basic Mapping**  chapter in Eclipse.

Student.java

package com . tutorialspoint . model ;

public class Student {

private int id ;

private String name ;

private String className ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassName () {

return className ;

}

public void setClassName ( String className ) {

this . className = className ;

}

}

StudentEntity.java

package com . tutorialspoint . entity ;

public class StudentEntity {

private int id ;

private String name ;

private String classVal ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassVal () {

return classVal ;

}

public void setClassVal ( String classVal ) {

this . classVal = classVal ;

}

}

StudentMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . model . Student ;

@Mapper

public interface StudentMapper {

default Student getModelFromEntity ( StudentEntity studentEntity ){

Student student = new Student ();

student . setId ( studentEntity . getId ());

student . setName ( studentEntity . getName ());

student . setClassName ( studentEntity . getClassVal ());

return student ;

}

@Mapping ( target = "classVal" , source = "className" )

StudentEntity getEntityFromModel ( Student student );

}

StudentMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . mapper . StudentMapper ;

import com . tutorialspoint . model . Student ;

public class StudentMapperTest {

private StudentMapper studentMapper = Mappers . getMapper ( StudentMapper . class );

@Test

public void testEntityToModel () {

StudentEntity entity = new StudentEntity ();

entity . setClassVal ( "X" );

entity . setName ( "John" );

entity . setId ( 1 );

Student model = studentMapper . getModelFromEntity ( entity );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

}

@Test

public void testModelToEntity () {

Student model = new Student ();

model . setId ( 1 );

model . setName ( "John" );

model . setClassName ( "X" );

StudentEntity entity = studentMapper . getEntityFromModel ( model );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.004 sec

...

# Mapping Multiple Objects

We can add map multiple objects as well. For Example, we want to get a DeliveryAddress Object using Student and Address object.

Now create a mapper interface which can map two objects into one.

@Mapper

public interface DeliveryAddressMapper {

@Mapping ( source = "student.name" , target = "name" )

@Mapping ( source = "address.houseNo" , target = "houseNumber" )

DeliveryAddress getDeliveryAddress ( StudentEntity student , AddressEntity address );

}

## Example

Open project mapping as updated in **Custom Mapping**  chapter in Eclipse.

Create DeliveryAddress.java with following code −

DeliveryAddress.java

package com . tutorialspoint . model ;

public class DeliveryAddress {

private String name ;

private int houseNumber ;

private String city ;

private String state ;

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public int getHouseNumber () {

return houseNumber ;

}

public void setHouseNumber ( int houseNumber ) {

this . houseNumber = houseNumber ;

}

public String getCity () {

return city ;

}

public void setCity ( String city ) {

this . city = city ;

}

public String getState () {

return state ;

}

public void setState ( String state ) {

this . state = state ;

}

}

Create AddressEntity.java with following code −

AddressEntity.java

package com . tutorialspoint . entity ;

public class AddressEntity {

private int houseNo ;

private String city ;

private String state ;

public int getHouseNo () {

return houseNo ;

}

public void setHouseNo ( int houseNo ) {

this . houseNo = houseNo ;

}

public String getCity () {

return city ;

}

public void setCity ( String city ) {

this . city = city ;

}

public String getState () {

return state ;

}

public void setState ( String state ) {

this . state = state ;

}

}

Create DeliveryAddressMapper.java with following code −

DeliveryAddressMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . AddressEntity ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . model . DeliveryAddress ;

@Mapper

public interface DeliveryAddressMapper {

@Mapping ( source = "student.name" , target = "name" )

@Mapping ( source = "address.houseNo" , target = "houseNumber" )

DeliveryAddress getDeliveryAddress ( StudentEntity student , AddressEntity address );

}

Create DeliveryAddressMapperTest.java with following code −

DeliveryAddressMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . AddressEntity ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . mapper . DeliveryAddressMapper ;

import com . tutorialspoint . model . DeliveryAddress ;

public class DeliveryAddressMapperTest {

private DeliveryAddressMapper deliveryAddressMapper = Mappers . getMapper ( DeliveryAddressMapper . class );

@Test

public void testEntityToModel () {

StudentEntity student = new StudentEntity ();

student . setClassVal ( "X" );

student . setName ( "John" );

student . setId ( 1 );

AddressEntity address = new AddressEntity ();

address . setCity ( "Y" );

address . setState ( "Z" );

address . setHouseNo ( 1 );

DeliveryAddress deliveryAddress = deliveryAddressMapper . getDeliveryAddress ( student , address );

assertEquals ( deliveryAddress . getName (), student . getName ());

assertEquals ( deliveryAddress . getCity (), address . getCity ());

assertEquals ( deliveryAddress . getState (), address . getState ());

assertEquals ( deliveryAddress . getHouseNumber (), address . getHouseNo ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.011 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0

...

# Mapping Nested Bean

MapStruct handles nested mapping seemlessly. For example, a Student with Subject as nested bean.

Now create a mapper interface which can map nested objects.

@Mapper

public interface StudentMapper {

@Mapping ( target = "className" , source = "classVal" )

@Mapping ( target = "subject" , source = "subject.name" )

Student getModelFromEntity ( StudentEntity studentEntity );

@Mapping ( target = "classVal" , source = "className" )

@Mapping ( target = "subject.name" , source = "subject" )

StudentEntity getEntityFromModel ( Student student );

}

## Example

Open project mapping as updated in **Mapping Multiple Objects**  chapter in Eclipse.

Create SubjectEntity.java with following code −

SubjectEntity.java

package com . tutorialspoint . entity ;

public class SubjectEntity {

private String name ;

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}       

}

Update StudentEntity.java with following code −

StudentEntity.java

package com . tutorialspoint . entity ;

public class StudentEntity {

private int id ;

private String name ;

private String classVal ;

private SubjectEntity subject ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassVal () {

return classVal ;

}

public void setClassVal ( String classVal ) {

this . classVal = classVal ;

}

public SubjectEntity getSubject () {

return subject ;

}

public void setSubject ( SubjectEntity subject ) {

this . subject = subject ;

}

}

Update Student.java with following code −

Student.java

package com . tutorialspoint . model ;

public class Student {

private int id ;

private String name ;

private String className ;

private String subject ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassName () {

return className ;

}

public void setClassName ( String className ) {

this . className = className ;

}

public String getSubject () {

return subject ;

}

public void setSubject ( String subject ) {

this . subject = subject ;

}

}

Update StudentMapper.java with following code −

StudentMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . model . Student ;

@Mapper

public interface StudentMapper {

@Mapping ( target = "className" , source = "classVal" )

@Mapping ( target = "subject" , source = "subject.name" )

Student getModelFromEntity ( StudentEntity studentEntity );

@Mapping ( target = "classVal" , source = "className" )

@Mapping ( target = "subject.name" , source = "subject" )

StudentEntity getEntityFromModel ( Student student );

}

Update StudentMapperTest.java with following code −

StudentMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . entity . SubjectEntity ;

import com . tutorialspoint . mapper . StudentMapper ;

import com . tutorialspoint . model . Student ;

public class StudentMapperTest {

private StudentMapper studentMapper = Mappers . getMapper ( StudentMapper . class );

@Test

public void testEntityToModel () {

StudentEntity entity = new StudentEntity ();

entity . setClassVal ( "X" );

entity . setName ( "John" );

entity . setId ( 1 );

SubjectEntity subject = new SubjectEntity ();

subject . setName ( "Computer" );

entity . setSubject ( subject );

Student model = studentMapper . getModelFromEntity ( entity );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

assertEquals ( entity . getSubject (). getName (), model . getSubject ());

}

@Test

public void testModelToEntity () {

Student model = new Student ();

model . setId ( 1 );

model . setName ( "John" );

model . setClassName ( "X" );

model . setSubject ( "Science" );

StudentEntity entity = studentMapper . getEntityFromModel ( model );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

assertEquals ( entity . getSubject (). getName (), model . getSubject ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.002 sec

Results :

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0

...

# Mapping Direct Fields

MapStruct handles direct fields mapping easily. For example, a Student with section as private property and StudentEntity with section as public property. To have both getter/setter mapping, a property should be public. In case of public final, only getter method will be present for mapping.

Now create a mapper interface. We'll use @InheritInverseConfiguration annotation to copy reverse configuration now.

@Mapper

public interface StudentMapper {

@Mapping ( target = "className" , source = "classVal" )

@Mapping ( target = "subject" , source = "subject.name" )

Student getModelFromEntity ( StudentEntity studentEntity );

@InheritInverseConfiguration

StudentEntity getEntityFromModel ( Student student );

}

## Example

Open project mapping as updated in **Mapping Nested Objects**  chapter in Eclipse.

Update StudentEntity.java with following code −

StudentEntity.java

package com . tutorialspoint . entity ;

public class StudentEntity {

private int id ;

private String name ;

private String classVal ;

private SubjectEntity subject ;

public String section ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassVal () {

return classVal ;

}

public void setClassVal ( String classVal ) {

this . classVal = classVal ;

}

public SubjectEntity getSubject () {

return subject ;

}

public void setSubject ( SubjectEntity subject ) {

this . subject = subject ;

}

}

Update Student.java with following code −

Student.java

package com . tutorialspoint . model ;

public class Student {

private int id ;

private String name ;

private String className ;

private String subject ;

private String section ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassName () {

return className ;

}

public void setClassName ( String className ) {

this . className = className ;

}

public String getSubject () {

return subject ;

}

public void setSubject ( String subject ) {

this . subject = subject ;

}

public String getSection () {

return section ;

}

public void setSection ( String section ) {

this . section = section ;

}

}

Update StudentMapper.java with following code −

StudentMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . InheritInverseConfiguration ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . model . Student ;

@Mapper

public interface StudentMapper {

@Mapping ( target = "className" , source = "classVal" )

@Mapping ( target = "subject" , source = "subject.name" )

Student getModelFromEntity ( StudentEntity studentEntity );

@InheritInverseConfiguration

StudentEntity getEntityFromModel ( Student student );

}

Update StudentMapperTest.java with following code −

StudentMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . entity . SubjectEntity ;

import com . tutorialspoint . mapper . StudentMapper ;

import com . tutorialspoint . model . Student ;

public class StudentMapperTest {

private StudentMapper studentMapper = Mappers . getMapper ( StudentMapper . class );

@Test

public void testEntityToModel () {

StudentEntity entity = new StudentEntity ();

entity . setClassVal ( "X" );

entity . setName ( "John" );

entity . setId ( 1 );

entity . section = "A" ;

SubjectEntity subject = new SubjectEntity ();

subject . setName ( "Computer" );

entity . setSubject ( subject );

Student model = studentMapper . getModelFromEntity ( entity );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

assertEquals ( entity . getSubject (). getName (), model . getSubject ());

assertEquals ( entity . section , model . getSection ());       

}

@Test

public void testModelToEntity () {

Student model = new Student ();

model . setId ( 1 );

model . setName ( "John" );

model . setClassName ( "X" );

model . setSubject ( "Science" );

model . setSection ( "A" );

StudentEntity entity = studentMapper . getEntityFromModel ( model );

assertEquals ( entity . getClassVal (), model . getClassName ());

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

assertEquals ( entity . getSubject (). getName (), model . getSubject ());

assertEquals ( entity . section , model . getSection ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.002 sec

Results :

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0

...

# Using Builder

MapStruct allows to use Builders. We can use Builder frameworks or can use our custom builder. In below example, we are using a custom builder.

## Example

Open project mapping as updated in **Mapping Direct Fields**  chapter in Eclipse.

Update Student.java with following code −

Student.java

package com . tutorialspoint . model ;

public class Student {

private final String name ;

private final int id ;

protected Student ( Student . Builder builder ) {

this . name = builder . name ;

this . id = builder . id ;

}

public static Student . Builder builder () {

return new Student . Builder ();

}

public static class Builder {

private String name ;

private int id ;

public Builder name ( String name ) {

this . name = name ;

return this ;

}

public Builder id ( int id ) {

this . id = id ;

return this ;

}

public Student create () {

return new Student ( this );

}

}

public String getName () {

return name ;

}

public int getId () {

ret + urn id ;

}

}

Update StudentMapper.java with following code −

StudentMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . model . Student ;

@Mapper

public interface StudentMapper {

Student getModelFromEntity ( StudentEntity studentEntity );

@Mapping ( target = "id" , source = "id" )

@Mapping ( target = "name" , source = "name" )

StudentEntity getEntityFromModel ( Student student );

}

Update StudentMapperTest.java with following code −

StudentMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . entity . SubjectEntity ;

import com . tutorialspoint . mapper . StudentMapper ;

import com . tutorialspoint . model . Student ;

public class StudentMapperTest {

private StudentMapper studentMapper = Mappers . getMapper ( StudentMapper . class );

@Test

public void testEntityToModel () {

StudentEntity entity = new StudentEntity ();

entity . setName ( "John" );

entity . setId ( 1 );

Student model = studentMapper . getModelFromEntity ( entity );

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

}

@Test

public void testModelToEntity () {

Student . Builder builder = Student . builder (). id ( 1 ). name ( "John" );

Student model = builder . create ();

StudentEntity entity = studentMapper . getEntityFromModel ( model );

assertEquals ( entity . getName (), model . getName ());

assertEquals ( entity . getId (), model . getId ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.002 sec

Results :

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0

...

# Implicit Type Conversion

MapStruct handles conversion of type conversions automatically in most of the cases. For example, int to Long or String conversion. Conversion handles null values as well. Following are the some of the important automatic conversions.

*   Between primitive types and Corresponding Wrapper Classes.
*   Between primitive types and String.
*   Between enum types and String.
*   Between BigInt, BigDecimal and String.
*   Between Calendar/Date and XMLGregorianCalendar.
*   Between XMLGregorianCalendar and String.
*   Between Jodas date types and String.

## Example

Open project mapping as updated in **Mapping Using Builder**  chapter in Eclipse.

Update StudentEntity.java with following code −

StudentEntity.java

package com . tutorialspoint . entity ;

public class StudentEntity {

private String id ;

private String name ;

private String classVal ;

private SubjectEntity subject ;

public String section ;

public String getId () {

return id ;

}

public void setId ( String id ) {

this . id = id ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

public String getClassVal () {

return classVal ;

}

public void setClassVal ( String classVal ) {

this . classVal = classVal ;

}

public SubjectEntity getSubject () {

return subject ;

}

public void setSubject ( SubjectEntity subject ) {

this . subject = subject ;

}

}

Student.java is unchanged with following code −

Student.java

package com . tutorialspoint . model ;

public class Student {

private final String name ;

private final int id ;

protected Student ( Student . Builder builder ) {

this . name = builder . name ;

this . id = builder . id ;

}

public static Student . Builder builder () {

return new Student . Builder ();

}

public static class Builder {

private String name ;

private int id ;

public Builder name ( String name ) {

this . name = name ;

return this ;

}

public Builder id ( int id ) {

this . id = id ;

return this ;

}

public Student create () {

return new Student ( this );

}

}

public String getName () {

return name ;

}

public int getId () {

ret + urn id ;

}

}

Update DeliveryAddressMapperTest.java with following code −

DeliveryAddressMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . AddressEntity ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . mapper . DeliveryAddressMapper ;

import com . tutorialspoint . model . DeliveryAddress ;

public class DeliveryAddressMapperTest {

private DeliveryAddressMapper deliveryAddressMapper = Mappers . getMapper ( DeliveryAddressMapper . class );

@Test

public void testEntityToModel () {

StudentEntity student = new StudentEntity ();

student . setClassVal ( "X" );

student . setName ( "John" );

student . setId ( "1" );

AddressEntity address = new AddressEntity ();

address . setCity ( "Y" );

address . setState ( "Z" );

address . setHouseNo ( 1 );

DeliveryAddress deliveryAddress = deliveryAddressMapper . getDeliveryAddress ( student , address );

assertEquals ( deliveryAddress . getName (), student . getName ());

assertEquals ( deliveryAddress . getCity (), address . getCity ());

assertEquals ( deliveryAddress . getState (), address . getState ());

assertEquals ( deliveryAddress . getHouseNumber (), address . getHouseNo ());

}

}

Update StudentMapperTest.java with following code −

StudentMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . StudentEntity ;

import com . tutorialspoint . entity . SubjectEntity ;

import com . tutorialspoint . mapper . StudentMapper ;

import com . tutorialspoint . model . Student ;

public class StudentMapperTest {

private StudentMapper studentMapper = Mappers . getMapper ( StudentMapper . class );

@Test

public void testEntityToModel () {

StudentEntity entity = new StudentEntity ();

entity . setName ( "John" );

entity . setId ( "1" );

Student model = studentMapper . getModelFromEntity ( entity );

assertEquals ( entity . getName (), model . getName ());

assertEquals ( Integer . parseInt ( entity . getId ()), model . getId ());

}

@Test

public void testModelToEntity () {

Student . Builder builder = Student . builder (). id ( 1 ). name ( "John" );

Student model = builder . create ();

StudentEntity entity = studentMapper . getEntityFromModel ( model );

assertEquals ( entity . getName (), model . getName ());

assertEquals ( Integer . parseInt ( entity . getId ()), model . getId ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.002 sec

Results :

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0

...

# Using number Format

MapStruct handles conversion of numbers to String in required format seamlessly. We can pass the required format as numberFormat during @Mapping annotation. For example, consider a case where an amount stored in numbers is to be shown in currency format.

*   **Source**  − Entity has price as 350.
*   **Target**  − Model to show price as $350.00.
*   **numberFormat**  − Use format $#.00

## Example

Open project mapping as updated in **Mapping Implicit Type Conversions**  chapter in Eclipse.

Create CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

public class CarEntity {

private int id ;

private double price ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

}

Create Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

}

Create CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

@Mapper

public interface CarMapper {

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

Car getModelFromEntity ( CarEntity carEntity );

}

Create CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( model . getPrice (), "$345000.00" );

assertEquals ( entity . getId (), model . getId ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Using date Format

MapStruct handles conversion of date to String in required format seamlessly. We can pass the required format as dateFormat during @Mapping annotation. For example, consider a case where a date stored in numbers is to be shown in particular format.

*   **Source**  − Entity has date as GregorianCalendar(2015, 3, 5).
*   **Target**  − Model to show date as 05.04.2015.
*   **dateFormat**  − Use format dd.MM.yyyy

## Example

Open project mapping as updated in **Mapping Using numberFormat**  chapter in Eclipse.

Update CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

import java . util . GregorianCalendar ;

public class CarEntity {

private int id ;

private double price ;

private GregorianCalendar manufacturingDate ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

public GregorianCalendar getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( GregorianCalendar manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

}

Update Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

private String manufacturingDate ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

public String getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( String manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

}

Update CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

@Mapper

public interface CarMapper {

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

@Mapping ( source = "manufacturingDate" , target = "manufacturingDate" , dateFormat = "dd.MM.yyyy" )

Car getModelFromEntity ( CarEntity carEntity );

}

Update CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

entity . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( model . getPrice (), "$345000.00" );

assertEquals ( entity . getId (), model . getId ());

assertEquals ( "05.04.2015" , model . getManufacturingDate ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Using expression

MapStruct allows to call a conversion method for customized logic. We can use expression to achieve the same where we can pass any java object and call its method to do the conversion.

## Syntax

@Mapping(target = "target-property",

expression = "java(target-method())")

Here

*   **target-property**  − the property for which we are doing the mapping.
*   **expression**  − mapper will call the java method written in the expression.
*   **target-method**  − target-method is the method to be called. In case method is present in different class, use new class-name.target-method()

## Example

Open project mapping as updated in **Mapping Using dateFormat**  chapter in Eclipse.

Update CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

import java . util . GregorianCalendar ;

public class CarEntity {

private int id ;

private double price ;

private GregorianCalendar manufacturingDate ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

public GregorianCalendar getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( GregorianCalendar manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

}

Update Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

private String manufacturingDate ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

public String getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( String manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

}

Update CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import java . text . SimpleDateFormat ;

import java . util . Date ;

import java . util . GregorianCalendar ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

@Mapper

public interface CarMapper {

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

@Mapping ( target = "manufacturingDate" ,

expression = "java(getManufacturingDate(carEntity.getManufacturingDate()))" )

Car getModelFromEntity ( CarEntity carEntity );

default String getManufacturingDate ( GregorianCalendar manufacturingDate ) {

Date d = manufacturingDate . getTime ();

SimpleDateFormat sdf = new SimpleDateFormat ( "dd.MM.yyyy" );

return sdf . format ( d );

}

}

Update CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

entity . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( model . getPrice (), "$345000.00" );

assertEquals ( entity . getId (), model . getId ());

assertEquals ( "05.04.2015" , model . getManufacturingDate ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Using constant

MapStruct allows to map a constant value to a property.

## Syntax

@Mapping(target = "target-property", const = "const-value")

Here

*   **target-property**  − the property for which we are doing the mapping.
*   **const-value**  − mapper will map the const-value to target-property.

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Using dateFormat**  chapter in Eclipse.

Update CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

import java . util . GregorianCalendar ;

public class CarEntity {

private int id ;

private double price ;

private GregorianCalendar manufacturingDate ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

public GregorianCalendar getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( GregorianCalendar manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

}

Update Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

private String manufacturingDate ;

private String brand ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

public String getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( String manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getBrand () {

return brand ;

}

public void setBrand ( String brand ) {

this . brand = brand ;

}

}

Update CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

@Mapper

public interface CarMapper {

@Mapping ( target = "brand" , constant = "BMW" )

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

@Mapping ( source = "manufacturingDate" , target = "manufacturingDate" , dateFormat = "dd.MM.yyyy" )

Car getModelFromEntity ( CarEntity carEntity );

}

Update CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

entity . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( model . getPrice (), "$345000.00" );

assertEquals ( entity . getId (), model . getId ());

assertEquals ( "05.04.2015" , model . getManufacturingDate ());

assertEquals ( "BMW" , model . getBrand ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Using default Value

Using Mapstruct we can pass the default value in case source property is null using defaultValue attribute of @Mapping annotation.

## Syntax

@Mapping(target = "target-property", source="source-property"

defaultValue = "default-value")

Here

*   **default-value**  − target-property will be set as default-value in case source-property is null.

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Using Constant**  chapter in Eclipse.

Update CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

import java . util . GregorianCalendar ;

public class CarEntity {

private int id ;

private double price ;

private GregorianCalendar manufacturingDate ;

private String name ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

public GregorianCalendar getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( GregorianCalendar manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

}

Update Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

private String manufacturingDate ;

private String brand ;

private String name ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

public String getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( String manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getBrand () {

return brand ;

}

public void setBrand ( String brand ) {

this . brand = brand ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

}

Update CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

@Mapper

public interface CarMapper {

@Mapping ( source = "name" , target = "name" , defaultValue = "Sample" )

@Mapping ( target = "brand" , constant = "BMW" )

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

@Mapping ( source = "manufacturingDate" , target = "manufacturingDate" , dateFormat = "dd.MM.yyyy" )

Car getModelFromEntity ( CarEntity carEntity );

}

Update CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

entity . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( model . getPrice (), "$345000.00" );

assertEquals ( entity . getId (), model . getId ());

assertEquals ( "05.04.2015" , model . getManufacturingDate ());

assertEquals ( "Sample" , model . getName ());

assertEquals ( "BMW" , model . getBrand ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Using default Expression

Using Mapstruct we can pass a computed value using defaultExpression in case source property is null using defaultExpression attribute of @Mapping annotation.

## Syntax

@Mapping(target = "target-property", source="source-property"

defaultExpression = "default-value-method")

Here

*   **default-value-method**  − target-property will be set as result of default-value-method in case source-property is null.

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Using defaultValue**  chapter in Eclipse.

Update CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

import java . util . GregorianCalendar ;

public class CarEntity {

private int id ;

private double price ;

private GregorianCalendar manufacturingDate ;

private String name ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

public GregorianCalendar getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( GregorianCalendar manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

}

Update Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

private String manufacturingDate ;

private String brand ;

private String name ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

public String getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( String manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getBrand () {

return brand ;

}

public void setBrand ( String brand ) {

this . brand = brand ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

}

Update CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

import java . util . UUID ;

@Mapper ( imports = UUID . class )

public interface CarMapper {

@Mapping ( source = "name" , target = "name" , defaultExpression = "java(UUID.randomUUID().toString())" )

@Mapping ( target = "brand" , constant = "BMW" )

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

@Mapping ( source = "manufacturingDate" , target = "manufacturingDate" , dateFormat = "dd.MM.yyyy" )

Car getModelFromEntity ( CarEntity carEntity );

}

Update CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

entity . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( model . getPrice (), "$345000.00" );

assertEquals ( entity . getId (), model . getId ());

assertEquals ( "05.04.2015" , model . getManufacturingDate ());

assertNotNull ( model . getName ());

assertEquals ( "BMW" , model . getBrand ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Mapping List

Using Mapstruct we can map list in similar fashion as we map primitives. To get a list of objects, we should provide a mapper method which can map an object.

## Syntax

@Mapper

public interface CarMapper {

List<String> getListOfStrings(List<Integer> listOfIntegers);

List<Car> getCars(List<CarEntity> carEntities);

Car getModelFromEntity(CarEntity carEntity);

}

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Using defaultExpression**  chapter in Eclipse.

Update CarEntity.java with following code −

CarEntity.java

package com . tutorialspoint . entity ;

import java . util . GregorianCalendar ;

public class CarEntity {

private int id ;

private double price ;

private GregorianCalendar manufacturingDate ;

private String name ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public double getPrice () {

return price ;

}

public void setPrice ( double price ) {

this . price = price ;

}

public GregorianCalendar getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( GregorianCalendar manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

}

Update Car.java with following code −

Car.java

package com . tutorialspoint . model ;

public class Car {

private int id ;

private String price ;

private String manufacturingDate ;

private String brand ;

private String name ;

public int getId () {

return id ;

}

public void setId ( int id ) {

this . id = id ;

}

public String getPrice () {

return price ;

}

public void setPrice ( String price ) {

this . price = price ;

}

public String getManufacturingDate () {

return manufacturingDate ;

}

public void setManufacturingDate ( String manufacturingDate ) {

this . manufacturingDate = manufacturingDate ;

}

public String getBrand () {

return brand ;

}

public void setBrand ( String brand ) {

this . brand = brand ;

}

public String getName () {

return name ;

}

public void setName ( String name ) {

this . name = name ;

}

}

Update CarMapper.java with following code −

CarMapper.java

package com . tutorialspoint . mapper ;

import org . mapstruct . Mapper ;

import org . mapstruct . Mapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . model . Car ;

import java . util . List ;

import java . util . UUID ;

@Mapper ( imports = UUID . class )

public interface CarMapper {

@Mapping ( source = "name" , target = "name" , defaultExpression = "java(UUID.randomUUID().toString())" )

@Mapping ( target = "brand" , constant = "BMW" )

@Mapping ( source = "price" , target = "price" , numberFormat = "$#.00" )

@Mapping ( source = "manufacturingDate" , target = "manufacturingDate" , dateFormat = "dd.MM.yyyy" )

Car getModelFromEntity ( CarEntity carEntity );

List < String > getListOfStrings ( List < Integer > listOfIntegers );

List < Car > getCars ( List < CarEntity > carEntities );

}

Update CarMapperTest.java with following code −

CarMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import static org . junit . jupiter . api . Assertions . assertNotNull ;

import java . util . Arrays ;

import java . util . GregorianCalendar ;

import java . util . List ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . mapper . CarMapper ;

import com . tutorialspoint . model . Car ;

public class CarMapperTest {

private CarMapper carMapper = Mappers . getMapper ( CarMapper . class );

@Test

public void testEntityToModel () {

CarEntity entity = new CarEntity ();

entity . setPrice ( 345000 );

entity . setId ( 1 );

entity . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

CarEntity entity1 = new CarEntity ();

entity1 . setPrice ( 445000 );

entity1 . setId ( 2 );

entity1 . setManufacturingDate ( new GregorianCalendar ( 2015 , 3 , 5 ));

List < CarEntity > carEntities = Arrays . asList ( entity , entity1 );

Car model = carMapper . getModelFromEntity ( entity );

assertEquals ( "$345000.00" , model . getPrice ());

assertEquals ( entity . getId (), model . getId ());

assertEquals ( "BMW" , model . getBrand ());

assertEquals ( "05.04.2015" , model . getManufacturingDate ());

List < Integer > list = Arrays . asList ( 1 , 2 , 3 );

List < String > listOfStrings = carMapper . getListOfStrings ( list );

List < Car > listOfCars = carMapper . getCars ( carEntities );

assertEquals ( 3 , listOfStrings . size ());

assertEquals ( 2 , listOfCars . size ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.035 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0

...

# Mapping Map

Using Mapstruct we can create mapping of map objects using @MapMapping annotation. Other rules of mapping are same as we've seen so far.

## Syntax

@Mapper

public interface UtilityMapper {

@MapMapping ( valueDateFormat = "dd.MM.yyyy" )

Map < String , String > getMap ( Map < Long , GregorianCalendar > source );

}

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping List**  chapter in Eclipse.

Create UtilityMapper.java with following code −

UtilityMapper.java

package com . tutorialspoint . mapper ;

import java . util . GregorianCalendar ;

import java . util . Map ;

import org . mapstruct . MapMapping ;

import org . mapstruct . Mapper ;

@Mapper

public interface UtilityMapper {

@MapMapping ( valueDateFormat = "dd.MM.yyyy" )

Map < String , String > getMap ( Map < Long , GregorianCalendar > source );

}

Create UtilityMapperTest.java with following code −

UtilityMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import java . util . HashMap ;

import java . util . Map ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . mapper . UtilityMapper ;

public class UtilityMapperTest {

private UtilityMapper utilityMapper = Mappers . getMapper ( UtilityMapper . class );

@Test

public void testMapMapping () {

Map < Long , GregorianCalendar > source = new HashMap <>();

source . put ( 1L , new GregorianCalendar ( 2015 , 3 , 5 ));

Map < String , String > target = utilityMapper . getMap ( source );

assertEquals ( "05.04.2015" , target . get ( "1" ));        

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.327 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.UtilityMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 5, Failures: 0, Errors: 0, Skipped: 0

...

# Mapping Stream

Using Mapstruct we can create mapping of streams in the same way as we did for collections.

## Syntax

@Mapper

public interface UtilityMapper {

Stream<String> getStream(Stream<Integer> source);

}

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Map**  chapter in Eclipse.

Update UtilityMapper.java with following code −

UtilityMapper.java

package com . tutorialspoint . mapper ;

import java . util . GregorianCalendar ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . mapstruct . MapMapping ;

import org . mapstruct . Mapper ;

@Mapper

public interface UtilityMapper {

@MapMapping ( valueDateFormat = "dd.MM.yyyy" )

Map < String , String > getMap ( Map < Long , GregorianCalendar > source );

Stream < String > getStream ( Stream < Integer > source );

}

Update UtilityMapperTest.java with following code −

UtilityMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . GregorianCalendar ;

import java . util . HashMap ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . mapper . UtilityMapper ;

public class UtilityMapperTest {

private UtilityMapper utilityMapper = Mappers . getMapper ( UtilityMapper . class );

@Test

public void testMapMapping () {

Map < Long , GregorianCalendar > source = new HashMap <>();

source . put ( 1L , new GregorianCalendar ( 2015 , 3 , 5 ));

Map < String , String > target = utilityMapper . getMap ( source );

assertEquals ( "05.04.2015" , target . get ( "1" ));        

}

@Test

public void testGetStream () {

Stream < Integer > numbers = Arrays . asList ( 1 , 2 , 3 , 4 ). stream ();

Stream < String > strings = utilityMapper . getStream ( numbers );

assertEquals ( 4 , strings . count ());         

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.327 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.UtilityMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 5, Failures: 0, Errors: 0, Skipped: 0

...

# Mapping Enum

Mapstruct automatically maps enums. Enums with same name are mapped automatically. In case of different name, we can use @ValueMapping annotation to do the mapping.

## Syntax

@Mapper

public interface UtilityMapper {

@ValueMapping(source = "EXTRA", target = "SPECIAL")

PlacedOrderType getEnum(OrderType order);

}

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Stream**  chapter in Eclipse.

Update UtilityMapper.java with following code −

UtilityMapper.java

package com . tutorialspoint . mapper ;

import java . util . GregorianCalendar ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . mapstruct . MapMapping ;

import org . mapstruct . Mapper ;

import org . mapstruct . ValueMapping ;

import com . tutorialspoint . enums . OrderType ;

import com . tutorialspoint . enums . PlacedOrderType ;

@Mapper

public interface UtilityMapper {

@MapMapping ( valueDateFormat = "dd.MM.yyyy" )

Map < String , String > getMap ( Map < Long , GregorianCalendar > source );

Stream < String > getStream ( Stream < Integer > source );

@ValueMapping ( source = "EXTRA" , target = "SPECIAL" )

PlacedOrderType getEnum ( OrderType order );

}

Update UtilityMapperTest.java with following code −

UtilityMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import java . util . Arrays ;

import java . util . GregorianCalendar ;

import java . util . HashMap ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . enums . OrderType ;

import com . tutorialspoint . enums . PlacedOrderType ;

import com . tutorialspoint . mapper . UtilityMapper ;

public class UtilityMapperTest {

private UtilityMapper utilityMapper = Mappers . getMapper ( UtilityMapper . class );

@Test

public void testMapMapping () {

Map < Long , GregorianCalendar > source = new HashMap <>();

source . put ( 1L , new GregorianCalendar ( 2015 , 3 , 5 ));

Map < String , String > target = utilityMapper . getMap ( source );

assertEquals ( "05.04.2015" , target . get ( "1" ));        

}

@Test

public void testGetStream () {

Stream < Integer > numbers = Arrays . asList ( 1 , 2 , 3 , 4 ). stream ();

Stream < String > strings = utilityMapper . getStream ( numbers );

assertEquals ( 4 , strings . count ());         

}

@Test

public void testGetEnum () {

PlacedOrderType placedOrderType = utilityMapper . getEnum ( OrderType . EXTRA );

PlacedOrderType placedOrderType1 = utilityMapper . getEnum ( OrderType . NORMAL );

PlacedOrderType placedOrderType2 = utilityMapper . getEnum ( OrderType . STANDARD );

assertEquals ( PlacedOrderType . SPECIAL . name (), placedOrderType . name ());

assertEquals ( PlacedOrderType . NORMAL . name (), placedOrderType1 . name ());

assertEquals ( PlacedOrderType . STANDARD . name (), placedOrderType2 . name ());

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.256 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.UtilityMapperTest

Tests run: 3, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Results :

Tests run: 7, Failures: 0, Errors: 0, Skipped: 0

...

# Throwing Exception

Mapstruct mapper allows throwing specific exception. Consider a case of custom mapping method where we want to throw our custom exception in case of invalid data.

## Syntax

@Mapper(uses=DateMapper.class)

public interface UtilityMapper {

CarEntity getCarEntity(Car car) throws ParseException;

}

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Enum**  chapter in Eclipse.

Update UtilityMapper.java with following code −

UtilityMapper.java

package com . tutorialspoint . mapper ;

import java . text . ParseException ;

import java . text . SimpleDateFormat ;

import java . util . Date ;

import java . util . GregorianCalendar ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . mapstruct . MapMapping ;

import org . mapstruct . Mapper ;

import org . mapstruct . ValueMapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . enums . OrderType ;

import com . tutorialspoint . enums . PlacedOrderType ;

import com . tutorialspoint . model . Car ;

@Mapper ( uses = DateMapper . class )

public interface UtilityMapper {

@MapMapping ( valueDateFormat = "dd.MM.yyyy" )

Map < String , String > getMap ( Map < Long , GregorianCalendar > source );

Stream < String > getStream ( Stream < Integer > source );

@ValueMapping ( source = "EXTRA" , target = "SPECIAL" )

PlacedOrderType getEnum ( OrderType order );

CarEntity getCarEntity ( Car car ) throws ParseException ;

}

class DateMapper {

public String asString ( GregorianCalendar date ) {

return date != null ? new SimpleDateFormat ( "yyyy-MM-dd" )

. format ( date . getTime () ) : null ;

}

public GregorianCalendar asDate ( String date ) throws ParseException {

Date date1 = date != null ? new SimpleDateFormat ( "yyyy-MM-dd" )

. parse ( date ) : null ;

if ( date1 != null ) {

return new GregorianCalendar ( date1 . getYear (), date1 . getMonth (), date1 . getDay ());

}

return null ;

}

}

Update UtilityMapperTest.java with following code −

UtilityMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import static org . junit . jupiter . api . Assertions . assertTrue ;

import java . text . ParseException ;

import java . util . Arrays ;

import java . util . GregorianCalendar ;

import java . util . HashMap ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . enums . OrderType ;

import com . tutorialspoint . enums . PlacedOrderType ;

import com . tutorialspoint . mapper . UtilityMapper ;

import com . tutorialspoint . model . Car ;

public class UtilityMapperTest {

private UtilityMapper utilityMapper = Mappers . getMapper ( UtilityMapper . class );

@Test

public void testMapMapping () {

Map < Long , GregorianCalendar > source = new HashMap <>();

source . put ( 1L , new GregorianCalendar ( 2015 , 3 , 5 ));

Map < String , String > target = utilityMapper . getMap ( source );

assertEquals ( "2015-04-05" , target . get ( "1" ));        

}

@Test

public void testGetStream () {

Stream < Integer > numbers = Arrays . asList ( 1 , 2 , 3 , 4 ). stream ();

Stream < String > strings = utilityMapper . getStream ( numbers );

assertEquals ( 4 , strings . count ());         

}

@Test

public void testGetEnum () {

PlacedOrderType placedOrderType = utilityMapper . getEnum ( OrderType . EXTRA );

PlacedOrderType placedOrderType1 = utilityMapper . getEnum ( OrderType . NORMAL );

PlacedOrderType placedOrderType2 = utilityMapper . getEnum ( OrderType . STANDARD );

assertEquals ( PlacedOrderType . SPECIAL . name (), placedOrderType . name ());

assertEquals ( PlacedOrderType . NORMAL . name (), placedOrderType1 . name ());

assertEquals ( PlacedOrderType . STANDARD . name (), placedOrderType2 . name ());

}

@Test

public void testGetCar () {

Car car = new Car ();

car . setId ( 1 );

car . setManufacturingDate ( "11/10/2020" );

boolean exceptionOccured = false ;

try {

CarEntity carEntity = utilityMapper . getCarEntity ( car );

} catch ( ParseException e ) {

exceptionOccured = true ;

}

assertTrue ( exceptionOccured );

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.256 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.UtilityMapperTest

Tests run: 4, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Results :

Tests run: 8, Failures: 0, Errors: 0, Skipped: 0

...

# Using Custom Mapper

Mapstruct mapper allows creating a custom mapper method to map an object. To mapper interface, we can add a default method.

## Syntax

@Mapper ( uses = DateMapper . class )

public interface UtilityMapper {

default Car getCar ( CarEntity entity ) {

Car car = new Car ();

car . setId ( entity . getId ());

car . setName ( entity . getName ());

return car ;

}

}

Following example demonstrates the same.

## Example

Open project mapping as updated in **Mapping Enum**  chapter in Eclipse.

Update UtilityMapper.java with following code −

UtilityMapper.java

package com . tutorialspoint . mapper ;

import java . text . ParseException ;

import java . text . SimpleDateFormat ;

import java . util . Date ;

import java . util . GregorianCalendar ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . mapstruct . MapMapping ;

import org . mapstruct . Mapper ;

import org . mapstruct . ValueMapping ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . enums . OrderType ;

import com . tutorialspoint . enums . PlacedOrderType ;

import com . tutorialspoint . model . Car ;

@Mapper ( uses = DateMapper . class )

public interface UtilityMapper {

@MapMapping ( valueDateFormat = "dd.MM.yyyy" )

Map < String , String > getMap ( Map < Long , GregorianCalendar > source );

Stream < String > getStream ( Stream < Integer > source );

@ValueMapping ( source = "EXTRA" , target = "SPECIAL" )

PlacedOrderType getEnum ( OrderType order );

CarEntity getCarEntity ( Car car ) throws ParseException ;

default Car getCar ( CarEntity entity ) {

Car car = new Car ();

car . setId ( entity . getId ());

car . setName ( entity . getName ());

return car ;

}

}

class DateMapper {

public String asString ( GregorianCalendar date ) {

return date != null ? new SimpleDateFormat ( "yyyy-MM-dd" )

. format ( date . getTime () ) : null ;

}

public GregorianCalendar asDate ( String date ) throws ParseException {

Date date1 = date != null ? new SimpleDateFormat ( "yyyy-MM-dd" )

. parse ( date ) : null ;

if ( date1 != null ) {

return new GregorianCalendar ( date1 . getYear (), date1 . getMonth (), date1 . getDay ());

}

return null ;

}

}

Update UtilityMapperTest.java with following code −

UtilityMapperTest.java

package com . tutorialspoint . mapping ;

import static org . junit . jupiter . api . Assertions . assertEquals ;

import static org . junit . jupiter . api . Assertions . assertTrue ;

import java . text . ParseException ;

import java . util . Arrays ;

import java . util . GregorianCalendar ;

import java . util . HashMap ;

import java . util . Map ;

import java . util . stream . Stream ;

import org . junit . jupiter . api . Test ;

import org . mapstruct . factory . Mappers ;

import com . tutorialspoint . entity . CarEntity ;

import com . tutorialspoint . enums . OrderType ;

import com . tutorialspoint . enums . PlacedOrderType ;

import com . tutorialspoint . mapper . UtilityMapper ;

import com . tutorialspoint . model . Car ;

public class UtilityMapperTest {

private UtilityMapper utilityMapper = Mappers . getMapper ( UtilityMapper . class );

@Test

public void testMapMapping () {

Map < Long , GregorianCalendar > source = new HashMap <>();

source . put ( 1L , new GregorianCalendar ( 2015 , 3 , 5 ));

Map < String , String > target = utilityMapper . getMap ( source );

assertEquals ( "2015-04-05" , target . get ( "1" ));        

}

@Test

public void testGetStream () {

Stream < Integer > numbers = Arrays . asList ( 1 , 2 , 3 , 4 ). stream ();

Stream < String > strings = utilityMapper . getStream ( numbers );

assertEquals ( 4 , strings . count ());         

}

@Test

public void testGetEnum () {

PlacedOrderType placedOrderType = utilityMapper . getEnum ( OrderType . EXTRA );

PlacedOrderType placedOrderType1 = utilityMapper . getEnum ( OrderType . NORMAL );

PlacedOrderType placedOrderType2 = utilityMapper . getEnum ( OrderType . STANDARD );

assertEquals ( PlacedOrderType . SPECIAL . name (), placedOrderType . name ());

assertEquals ( PlacedOrderType . NORMAL . name (), placedOrderType1 . name ());

assertEquals ( PlacedOrderType . STANDARD . name (), placedOrderType2 . name ());

}

@Test

public void testGetCarEntity () {

Car car = new Car ();

car . setId ( 1 );

car . setManufacturingDate ( "11/10/2020" );

boolean exceptionOccured = false ;

try {

CarEntity carEntity = utilityMapper . getCarEntity ( car );

} catch ( ParseException e ) {

exceptionOccured = true ;

}

assertTrue ( exceptionOccured );

}

@Test

public void testGetCar () {

CarEntity entity = new CarEntity ();

entity . setId ( 1 );

entity . setName ( "ZEN" );

Car car = utilityMapper . getCar ( entity );

assertEquals ( entity . getId (), car . getId ());

assertEquals ( entity . getName (), car . getName ());        

}

}

Run the following command to test the mappings.

mvn clean test

## Output

Once command is successful. Verify the output.

mvn clean test

[INFO] Scanning for projects...

...

[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ mapping ---

[INFO] Surefire report directory: \mvn\mapping\target\surefire-reports

-------------------------------------------------------

T E S T S

-------------------------------------------------------

Running com.tutorialspoint.mapping.CarMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.256 sec

Running com.tutorialspoint.mapping.DeliveryAddressMapperTest

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Running com.tutorialspoint.mapping.StudentMapperTest

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Running com.tutorialspoint.mapping.UtilityMapperTest

Tests run: 5, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0 sec

Results :

Tests run: 9, Failures: 0, Errors: 0, Skipped: 0

...