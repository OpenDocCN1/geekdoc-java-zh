![](Image00028.jpg)

Reverse Engineering of a Library System 1 st Edition

from Java Code to UML Diagrams

by : MOHAMED HAMDY ABDELLATIF IBRAHIM BILAL

Contents:

| Chapter | Page number |
| Chapter 1 : reverse engineering concepts | 2 : 10 |
| 1.1 maintenance problem and solution | 2 |
| 1.2 system development life cycle (SDLC) | 3 |
| 1.3 architecture of a reverse engineering tool | 4 |
| 1.4 object oriented code analysis | 5 |
| 1.5 pointer analysis | 6 |
| 1.6 object flow graph (OFG) data structure | 7 |
| 1.7 flow propagation algorithm | 8 |
| 1.8 production rules for constructing insensitive and sensitive OFGand making forward and backward flow propagation | 9 : 10 |
| Chapter 2 : reverse engineering by examples | 11 : 16 |
| 2.1 example of object insensitive and sensitive OFG | 11 : 13 |
| 2.2 example of forward and backward flow propagation | 14 : 16 |
| Chapter 3 : reverse engineering in details | 17 : 46 |
| 3.1 details | 17 : 40 |
| 3.2 figures | 41 : 46 |
| Chapter 4 : CASE STUDY (library system) | 47 : 74 |
| 4.1 CASE tools | 47 |
| 4.2 source code | 48 : 65 |
| 4.3 abstract syntax tree (AST) | 66 |
| 4.4 language model | 67 |
| 4.5 OFG, and flow propagation | 68 : 70 |
| 4.6 class diagram | 71 |
| 4.7 object diagram | 72 |
| 4.8 change location | 73 |
| 4.9 impact of the change | 74 |

Chapter 1 : reverse engineering concepts

1.1 maintenance problem and solution

maintenance problem and solution :

problem :

maintenance is very expensive .

Solution :

re-engineering by reverse engineering from code to diagrams

for doing model transformation to restructuring a system

then forward engineering from diagrams to code

for doing code refactoring to restructuring a system .

Benefit :

maintenance is not expensive .

Drawbacks :

can’t capture some types of information are not captured,

and not completely automate of a complex process .

Ways :

object oriented code analysis by pointer analysis

via data structure (object flow graph) and algorithm (flow propagation).

1.2 system development life cycle (SDLC)

system development life cycle (SDLC) :

![](Image00000.jpg)

1.3 architecture of a reverse engineering tool

architecture of a reverse engineering tool :

![](Image00001.jpg) notes :

Model : abstract form of a data

(class model)

(alternative perspectives can be adopted when the source code is analyzed

and different higher level views are extracted from it).

Diagram : concrete form of a data stored in XML file,

this file used for describe data to modify it by programming language

and for data compatibility when transport it between different systems

(class, object, interaction, state, and package diagrams)

(maximum 10 entities in diagram per package to makes a diagram readable)

(a single diagram recovered from the code through reverse engineering is insufficient.

rather, a set of complementary views need to be obtained,

addressing different program understanding needs).

(

1.4 object oriented code analysis

object oriented code analysis :

types :

static :

produces results for all or not input .

Dynamic :

produces results for a single input and possible only for complete, and executable systems .

Static object oriented code analysis :

is data flow sensitive but control flow insensitive.

This mean data flows are represented in OFG but control flow aren’t .

this mean instruction that don’t affect the data flows at all

are safely ignored like control flow statements .

This mean code with the same data flows  and different control flows

are associated with the same analysis results .

Because computational complexity and the nature of the object oriented programs .

1.5 pointer analysis

pointer analysis :

obtain a static approximation of any points-to relationships

that may hold at run-time between pointers and program locations ,

similarly, when object-oriented programs are considered,

the relationship between reference variables and object is analyzed .

1.6 object flow graph (OFG) data structure

object flow graph (OFG) data structure :

is a data structure for represents all the data flows involving objects .

Types:

Object insensitive :

to distinguish 2 location belong to different classes,

used when complete system is not available like class Main .

Object sensitive :

to distinguish 2 location belong to same class

but to difference class instances (objects),

used when complete system is available like class Main,

capture the data flows occurring in the code fragment

more accurately than those in object insensitive

because information is not mixed when propagated along different objects .

1.7 flow propagation algorithm

flow propagation algorithm :

is an algorithm for propagating information via OFG

to analyze the program’s behavior and to recover the design views of interest .

Types :

flow/context insensitive :

different statements can`t be distinguished,

have lower computational complexity

and their performance scale well to large software systems .

flow/context sensitive :

different statements can be distinguished,

have high computational complexity

and their performance doesn`t scale well to large software systems,

produce accurate results than those in flow/context insensitive

because results that hold for every program statement

not for the whole program like flow/context insensitive .

1.8 production rules for constructing insensitive and sensitive OFG

and making forward and backward flow propagation

production rules for constructing insensitive and sensitive OFG

and making forward and backward flow propagation :

allocation statement :

( x = new c (a k) )

===> edges : { (a’k,f’k),(cs’.this,x’) }

===> forward : gen [cs.this] = {c}, gen [x] = {ci}

concrete code :

// class Library, method borrowDocument

Loan Loan = new Loan(user);

first Loan for interface

second Loan for container

third Loan for object (contains method for insert it to container, and extract it from container)

abstract code :

Library.borrowDocument.loan = new Loan (Library.borrowDocument.user)

OFG edges :

{ (Library.borrowDocument.user, Loan.Loan.usr),

(Loan.Loan.this, Library.borrowDocument.loan) }

// insert only if extract reverse it with change the second node .

assignment statement :

( x = (c)y )

===> edges : { y’,x’ }

===> backward : gen[y] = {c}

concrete code :

// class Library, method addLoan

User user = loan.getUser( );

abstract code :

Library.addLoan.user = loan.getUser.return

OFG edges :

{ (loan.getUser.return, Library.addLoan.user) }

method invocation :

( [x=] (c)y.m(ak) )

===> edges : { (y’,m’.this),(a’k,f’k),(m’.return,x’)}

===> backward : gen[m.return] = {c}

concrete code :

// class Library, method borrowDocument

addLoan(loan);

abstract code :

Library.borrowDocument.this.Library.addLoan(Library.borrowDocument.loan)

OFG edges :

{ (Library.borrowDocument.this, Library.addLoan.this),

(Library.borrowDocument.loan, Library.addLoan.loan) }

notes :

* object insensitive OFG without replication (‘), and

object sensitive OFG with replication (‘) .

* c : class name

 cs : class constructor

 (c) : type coercion

 x,y : program locations

 a : class attribute name

 m : method name

 ak :actual parameters

 fk : formal parameters

 gen[n] : generates the set of flow information items

‘ : replication

 ci : object identifier

 in[n],out[n] : incoming and outgoing flow information

 kill[n] : prevents the elements from being further propagated

 n : node

 pred(n) : set of predecessors of node n

 succ(n) : set of successors of node n

Chapter 2 : reverse engineering by examples

2.1 example of object insensitive and sensitive OFG

example of object insensitive and sensitive OFG :

example : construct object insensitive and sensitive OFG for a library system ?

Concrete code :

// class Main

public static void main (String arg[ ]){ //hypothetical method

User u1 = new User(“bilal”, “ “, “ “);

Document d1 = new Document(“software engineering”);

Loan l1 = new Loan (u1,d1);

Document d2 = new Document(“software maintenance”);

Loan l2 = new Loan (u1,d2);

Document doc = l1.getDocument( );

}

abstract code : (object insensitive OFG)

Main.main.u1 = new User ( )

OFG edges : { (User.User.this,Main.main.u1) }

Main.main.d1 = new Document( )

OFG edges : { (Document.Document.this, Main.main.d1) }

Main.main.l1 = new Loan(Main.main.u1, Main.main.d1)

OFG edges : { (Main.main.u1,Loan.Loan.usr), (Main.main.d1,Loan.Loan.doc ),

(Loan.Loan.usr, Loan.user), (Loan.Loan.doc,Loan.document),

(Loan.document, Loan.getDocument.return),

(Loan.Loan.this, Main.main.l1) }

Main.main.d2 = new Document( )

OFG edges : { (Document.Document.this, Main.main.d2) }

Main.main.l2 = new Loan(Main.main.u1, Main.main.d2)

OFG edges : { (Main.main.u1,Loan.Loan.usr), (Main.main.d2,Loan.Loan.doc ),

(Loan.Loan.usr, Loan.user), (Loan.Loan.doc,Loan.document),

(Loan.document, Loan.getDocument.return),

(Loan.Loan.this, Main.main.l2) }

Main.main.doc = l1.getDocument.return

OFG edges { (Main.main.l1, Loan.getDocument.this),

(Loan.getDocument.return, Main.main.doc) }

object insensitive OFG (driver class)

![](Image00002.jpg)

abstract code : (object sensitive OFG)

Main.main.u1 = new User ( )

OFG edges : { (User1.User.this,Main.main.u1) }

Main.main.d1 = new Document( )

OFG edges : { (Document1.Document.this, Main.main.d1) }

Main.main.l1 = new Loan(Main.main.u1, Main.main.d1)

OFG edges : { (Main.main.u1,Loan1.Loan.usr), (Main.main.d1,Loan1.Loan.doc ),

(Loan1.Loan.usr, Loan1.user), (Loan1.Loan.doc,Loan1.document),

(Loan1.document, Loan1.getDocument.return),

(Loan1.Loan.this, Main.main.l1) }

Main.main.d2 = new Document( )

OFG edges : { (Document2.Document.this, Main.main.d2) }

Main.main.l2 = new Loan(Main.main.u1, Main.main.d2)

OFG edges : { (Main.main.u1,Loan2.Loan.usr), (Main.main.d2,Loan2.Loan.doc ),

(Loan2.Loan.usr, Loan2.user), (Loan2.Loan.doc, Loan2.document),

(Loan2.document, Loan2.getDocument.return),

(Loan2.Loan.this, Main.main.l2) }

Main.main.doc = l1.getDocument.return

OFG edges { (Main.main.l1, Loan1.getDocument.this),

(Loan1.getDocument.return, Main.main.doc) }

object sensitive OFG (driver class)

![](Image00003.jpg) boxes : a method body replicated for each allocated object .

2.2 example of forward and backward flow propagation

example of forward and backward flow propagation :

example : making forward and backward flow propagation for a library system ?

Concrete code :

class Main{

Static Library lib = new Library( );

public static void addUser(String cmd) {

String args[] = getArgs (cmd);

if (args.length < 3) return;

User user = new User (args [0] , args[1], args [2] );

lib.addUser(user);

System.out.println("Added user: " + user.getCode() + " - " + user .getName());

}

}

abstract code : (object insensitive OFG)

Main.lib = new Library( )

OFG edges {(Library.Library.this,Main.lib)}

Main.addUser.user = new User( )

OFG edges {(User.User.this,Main.addUser.user)}

Main.lib.addUser(Main.addUser.user)

OFG edges {(Main.addUser.user,Library.addUser.user)}

concrete code : //class Library

public boolean addUser(User user) {

if (!users.containsValue(user)) {

users.put(new Integer(user.getCode()), user);

return true;

}

return false;

}

abstract code :

Library.users = Library.addUser.user

OFG edges {(Library.addUser.user,Library.users)}

concrete code : //class Library

public List searchDocumentByTitle(String title) {

List docsFound = new LinkedList();

Iterator i = documents.values().iterator();

while (i.hasNext()) {

Document doc = (Document)i.next();

if (doc.getTitle().indexOf(title) != -1)

docsFound.add(doc);

}

return docsFound;

}

abstract code :

Library.searchDocumentByTitle.i = Library.documents

OFG edges {(Library.documents,Library.searchDocumentByTitle.i)}

Library.searchDocumentByTitle.doc = (Document)Library.searchDocumentByTitle.i

OFG edges {(Library.searchDocumentByTitle.i,Library.searchDocumentByTitle.doc)}

Library.searchDocumentByTitle.doc.getTitle( )

OFG edges {(Library.searchDocumentByTitle.doc,Document.getTitle.this)}

Library.searchDocumentByTitle.docsFound = Library.searchDocumentByTitle.doc

OFG edges {(Library.searchDocumentByTitle.doc,Library.searchDocumentByTitle.docsFound)}

Library.searchDocumentByTitle.return = Library.searchDocumentByTitle.docsFound

OFG edges {(Library.searchDocumentByTitle.docsFound,Library.searchDocumentByTitle.return)}

object insensitive OFG with forward and backward flow propagation (driver class, and core class)

![](Image00004.jpg)

* the attribute users of class Library contains objects of type class User .

* the attribute documents of class Library contains objects of type class Document .

ce : software evolution and maintenance a practitioner’s approach

chapter 3 : reverse engineering in details

page number 170

It is important to note that software reverse engineering is a complex process

that tools can only support, not completely automate.

There is a need for a good deal of human intervention with any reverse engineering project .

![](Image00005.jpg)

![](Image00006.jpg)

![](Image00007.jpg)

Reference : reverse engineering of object oriented code

Foreword

There has been an ongoing debate on how best to document a software system

ever since the first software system was built. Some would have us writing natural

language descriptions, some would have us prepare formal specifications,

others would have us producing design documents and others would want us

to describe the software thru test cases. There are even those who would have

us do all four, writing natural language documents, writing formal specifications,

producing standard design documents and producing interpretable test

cases all in addition to developing and maintaining the code. The problem

with this is that whatever is produced in the way of documentation becomes

in a short time useless, unless it is maintained parallel to the code. Maintaining

alternate views of complex systems becomes very expensive and highly

error prone . The views tend to drift apart and become inconsistent.

The authors of this book provide a simple solution to this perennial problem.

Only the source code is maintained and evolved. All of the other information

required on the system is taken from the source code. This entails

generating a complete set of UML diagrams from the source . In this way, the

design documentation will always reflect the real system as it is and not the

way the system should be from the viewpoint of the documentor. There can

be no inconsistency between design and implementation. The method used is

that of reverse engineering, the target of the method is object oriented code in

C++, C#, or Java. From the code class diagrams, object diagrams, interaction

diagrams and state diagrams are generated in accordance with the latest

UML standard. Since the method is automated, there are no additional costs.

Design documentation is provided at the click of a button.

This approach, the result of many years of research and development, will

have a profound impact upon the way IT-systems are documented. Besides

the source code itself, only one other view of the system needs to be developed

and maintained, that is the user view in the form of a domain specific language.

Each application domain will have to come up with it’s own language

to describe applications from the view point of the user. These languages may

range from natural languages to set theory to formal mathematical notations.

What these languages will not describe is how the system is or should be constructed.

This is the purpose of UML as a modeling language. The techniques

described in this book demonstrate that this design documentation can and

should be extracted from the code, since this is the cheapest and most reliable

means of achieving this end. There may be some UML documents produced

on the way to the code, but since complex IT systems are almost always developed

by trial and error, these documents will only have a transitive nature.

The moment the code exists they are both obsolete and superfluous. From

then on, the same documents can be produced cheaper and better from the

code itself. This approach coincides with and supports the practice of extreme

programming.

Of course there are several drawbacks , as some types of information are

not captured in the code and, therefore, reverse engineering cannot capture

them . An example is that there still needs to be a test oracle – something to

test against. This something is the domain specific specification from which

the application-oriented test cases are derived. The technical test cases can

be derived from the generated UML diagrams. In this way, the system as

implemented will be verified against the system as specified. Without the

UML diagrams, extracted from the code, there would be no adequate basis of

comparison.

For these and other reasons, this book is highly recommendable to all

who are developing and maintaining Object-Oriented software systems. They

should be aware of the possibilities and limitations of automated post documentation.

It wil l become increasing significant in the years to come, as the

current generation of OO-systems become the legacy systems of the future.

The implementation knowledge they encompass will most likely be only in the

source and there will be no other means of regaining it other than through

reverse engineering.

Preface

Diagrams representing the organization and behavior of an Object Oriented

software system can help developers comprehend it and evaluate the impact of

a modification. However, such diagrams are often unavailable or inconsistent

with the code. Their extraction from the code is thus an appealing option.

This book represents the state of the art of the research in Object Oriented

code analysis for reverse engineering. It describes the algorithms involved

in the recovery of several alternative views from the code and some of the

techniques that can be adopted for their visualization.

During software evolution, availability of high level descriptions is extremely

desirable, in support to program understanding and to change-impact

analysis. In fact, location of a change to be implemented can be guided by

high level views. The dependences among entities in such views indicate the

proportion of the ripple effects.

However, it is often the case that diagrams available during software evolution

are not consistent with the code, or – even more frequently – that no

diagram has altogether been produced. In such contexts, it is crucial to be

able to reverse engineer design diagrams directly from the code. Reverse engineered

diagrams are a faithful representation of the actual code organization

and of the actual interactions among objects. Programmers do not face any

misalignment or gap when moving from such diagrams to the code.

The material presented in this book is based on the techniques developed

during a collaboration we had with CERN (Conseil Européen pour la

Recherche Nucléaire). At CERN, work for the next generation of experiments

to be run on the Large Hadron Collider has started in large advance, since

these experiments represent a major challenge, for the size of the devices,

teams, and software involved. We collaborated with CERN in the introduction

of tools for software quality assurance, among which a reverse engineering

tool.

The algorithms described in this book deal with the reverse engineering of

the following diagrams:

Class diagram: Extraction of inter-class relationships in presence of weakly

typed containers and interfaces, which prevent an exact knowledge of the

actual type of referenced objects.

Object and interaction diagrams: Recovery of the associations among

the objects that instantiate the classes in a system and of the messages

exchanged among them.

State diagram: Modeling of the behavior of each class in terms of states

and state transitions.

Package diagram: Identification of packages and of the dependences among

packages.

All the algorithms share a common code analysis framework. The basic

principle underlying such a framework is that information is derived statically

(no code execution) by performing a propagation of proper data in a graph

representation of the object flows occurring in a program . The data structure

that has been defined for such a purpose is called the Object Flow Graph

(OFG). It allows tracking the lifetime of the objects from their creation along

their assignment to program variables.

UML, the Unified Modeling Language, has been chosen as the graphical

language to present the outcome of reverse engineering. This choice was motivated

by the fact that UML has become the standard for the representation

of design diagrams in Object Oriented development. However, the choice of

UML is by no means restrictive, in that the same information recovered from

the code can be provided to the users in different graphical or non graphical

formats.

A well known concern of most reverse engineering methods is how to filter

the results, when their size and complexity are excessively high. Since

the recovered diagrams are intended to be inspected by a human, the presentation

modes should take into account the cognitive limitations of humans

explicitly. Techniques such as focusing, hierarchical structuring and element

explosion/implosion will be introduced specifically for some diagram types.

The research community working in the field of reverse engineering has

produced an impressive amount of knowledge related to techniques and tools

that can be used during software evolution in support of program understanding.

It is the authors’ opinion that an important step forward would be

to publish the achievements obtained so far in comprehensive books dealing

with specific subtopics.

This book on reverse engineering from Object Oriented code goes exactly

in this direction. The authors have produced several research papers in this

field over time and have been active in the research community. The techniques

and the algorithms described in the book represent the current state of the

art.

Page number  1

Reverse engineering aims at supporting program comprehension, by exploiting

the source code as the major source of information about the organization

and behavior of a program, and by extracting a set of potentially useful views

provided to programmers in the form of diagrams. Alternative perspectives

can be adopted when the source code is analyzed and different higher level

views are extracted from it. The focus may either be on the structure, on

the behavior, on the internal states, or on the physical organization of the

files. A single diagram recovered from the code through reverse engineering

is insufficient. Rather, a set of complementary views need to be obtained,

addressing different program understanding needs.

In this chapter, the role of reverse engineering within the life cycle of a

software system is described. The activities of program understanding and

impact analysis are central during the evolution of an existing system. Both

activities can benefit from sources of knowledge about the program such as

reverse engineered diagrams.

The reverse engineering techniques presented in the following chapters are

described with reference to an example program used throughout the book. In

this chapter, this example program is introduced and commented. Then, some

of the diagrams that are the object of the following chapters are provided for

the example program, showing their usefulness from the programmer’s point

of view. The remaining parts of the book contain the algorithmic details on

how to recover them from the source code.

In the life cycle of a software system, the maintenance phase is the largest

and the most expensive. Starting after the delivery of the first version of the

software [35], maintenance lasts much longer than the initial development

phase. During this time, the software will be changed and enhanced over and

over. So it is more appropriate to speak of software evolution with reference

page number 2

to the whole life cycle, in which the initial development is only a special case

where the existing system is empty.

Software evolution is characterized by the existence of the source code of

the system. Thus, the typical activity in software evolution is the implementation

of a program change, in response to a change request. Changes may

be aimed at correcting the software ( corrective maintenance), at adding a

functionality ( perfective maintenance), at adapting the software to a changed

environment ( adaptive maintenance), or at restructuring it to make future

maintenance easier ( preventive maintenance) [35].

During software evolution, the most reliable and accurate description of

the behavior of a software system is its source code. In fact, design diagrams

are often outdated or missing at all. Such a valuable information repository

may not directly answer all questions about the system. Reverse engineering

techniques provide a way to extract higher level views of the system,

which summarize some relevant aspects of the computation performed by the

program statements. Reverse engineered diagrams support program comprehension,

as well as restructuring and traceability.

When an existing code base is worked on, the micro-process of program

change can be decomposed into localizing the change, assessing the impact,

and implementing the change. All such activities depend on the knowledge

available about the program to be modified. In this respect, reverse engineering

techniques are a useful support. Reverse engineering tools provide useful

high level information about the system being maintained, thus helping programmers

locate the component to be modified. Moreover, the relationships

(dependencies, associations, etc.) that connect the entities in reverse engineered

diagrams provide indications about the impact of a change. By tracing

such relationships the set of entities possibly affected by a change are obtained.

Object Oriented programming poses special problems to software engineers

during the maintenance phase. Correspondingly, reverse engineering

techniques have to be customized to address them. For example, the behavior

of an Object Oriented program emerges from the interactions occurring among

the objects allocated in the program. The related instructions may be spread

across several classes, which individually perform a very limited portion of

the work locally and delegate the rest of it to others. Reverse engineered diagrams

capture such collaborations among classes/objects, summarizing them

in a single, compact view. However, recovering accurate information about

such collaborations represents a special challenge, requiring major improvements

to the available reverse engineering methods [48, 100].

When a software system is analyzed to extract information about it, the

fundamental choice is between static and dynamic analysis. Dynamic analysis

requires a tracer tool to save information about the objects manipulated and

the methods dispatched during program execution. The diagrams that can

be reverse engineered in this way are partial. They hold valid for a single,

given execution of the program, with given input values, and they cannot be

easily generalized to the behavior of the program for any execution with any

page number 3

input. Moreover, dynamic analysis is possible only for complete, executable

systems, while in Object Oriented programming it is typical to produce incomplete

sets of classes that are reused in different contexts. On the contrary,

a static analysis produces results that are valid for all executions and for all

inputs. On the other side, static analyses may be over-conservative. In fact,

it is undecidable to determine if a statically possible path is feasible, i.e., if

there exists an input value allowing its traversal. Static analysis may conservatively

assume that some paths are executable, while they are actually not so.

Consequently, it may produce results for which no input value exists. In the

following chapters, the advantages and disadvantages of the two approaches

will be discussed for each specific diagram, illustrating them on an executable example.

UML (Unified Modeling Language) [7, 69] has become the standard graphical

language used to represent Object Oriented systems in diagrammatic form.

Its specifications have been recently standardized by the Object Management

Group (OMG) [1]. UML has been adopted by several software companies, and

its theoretical aspects are the subject of several research studies. For these reasons,

UML was chosen as the graphical representation that is produced as the

output of the reverse engineering techniques described in this book. However,

the choice of UML is by no means limiting: while the information reverse

engineered from the code can be represented in different graphical (or non

graphical) forms, the basic analysis methods exploited to produce it can be

reused unchanged in alternative settings, with UML replaced by some other

description language.

An important issue reverse engineering techniques must take into account

is usability. Since the recovered views are for humans and not for computers,

they must be compatible with the cognitive abilities of human beings. This

means that diagrams convey useful information only if their size is kept small

(while 10 entities may be fine, 100 starts being too much and 1000 makes a

diagram unreadable). Several approaches can be adopted to support visualization

and navigation modes making reverse engineered information usable.

They range from the possibility to focus on a portion of the system, to the

expand/collapse or zoom in/out operations, or to the availability of an overall

navigation map complemented by a detailed view. In the following chapters,

ad hoc methods will be described with reference to the specific diagrams being

produced.

Page number 4

a programmer aiming

at understanding this application may have the following questions:

What is the overall system organization?

What objects are updated when a document is borrowed?

What classes are responsible to check if a given document can be borrowed

by a given user?

How is the maximum number of loans handled?

What happens to the state of the library when a document is returned?

Let us assume the following change request (perfective maintenance):

When a document is not available for loan, a user can reserve it, if it

has not been previously reserved by another user. When a document

is returned to the library, the user who reserved it is contacted, if

any is associated with the document. The user can either borrow the

document that has become available or cancel the reservation. In both

cases, after this operation the reservation of the document is deleted.

the programmer who is responsible for its implementation may have the following

questions about the system:

Does the overall system organization need any change?

What classes need to collaborate to realize the reservation functionality?

Page number 5

Is there any possible side effect on the existing functionalities?

What changes should be made in the procedure for returning documents

to the library?

How is the new state of a document described?

Is there any interaction between the new rules for document borrowing

and the existing ones?

In the following sections, we will see how UML diagrams reverse engineered

from the code can help answer the program understanding and impact analysis

questions listed above.

Page number 18

Most of the static analyses used to reverse engineer these diagrams share a

common representation of the code called the Object Flow Graph (OFG). Such

a data structure is presented in Chapter 2\. This chapter contains the rules

for the construction of the OFG and introduces a generic flow propagation

algorithm that can be used to infer properties about the program’s objects.

Specializations of the generic algorithm are defined for specific properties.

Page number 21

The Object Flow Graph (OFG) is the basic program representation for the

static analysis described in the following chapters. The OFG allows tracing

the flow of information about objects from the object creation by allocation

statements, through object assignment to variables, up until the storage of

objects in class fields or their usage in method invocations.

The kind of information that is propagated in the OFG varies, depending

on the purposes of the analysis in which it is employed. For example, the

type to which objects are converted by means of cast expressions can be

the information being propagated, when an analysis is defined to statically

determine a more precise object type than the one in the object declaration.

Thus, in this chapter a flow propagation algorithm is described, with a generic

indication of the object information being processed.

In the first section of this chapter, the Java language is simplified into an

abstract language, where all features related to the object flow are maintained,

while the other syntactic details are dropped. This language is the basis for

the definition of the OFG, whose nodes and edges are constructed according

to the rules given in Section 2.2. Objects may flow externally to the analyzed

program. For example, an object may flow into a library container, from which

it is later extracted. Section 2.3 deals with the representation of such external

object flows in the OFG. The generic flow propagation algorithm working

on the OFG is described in Section 2.4\. Section 2.5 considers the differences

between an object insensitive and an object sensitive OFG. Details of OFG

construction are given for the eLib program in the next Section. A discussion

of the related works concludes this chapter.

The static analysis conducted on Java programs to reverse engineer design

diagrams from the code is data flow sensitive, but control flow insensitive. This

means that programs with different control flows and the same data flows are

page number 22

associated with the same analysis results. Data flow sensitivity and control

flow insensitivity are achieved by defining the analyses with reference to a

program representation called the Object Flow Graph (OFG). A consequence

of the control flow insensitivity is that the construction of the OFG can be

described with reference to a simplified, abstract version of the Java language.

All Java instructions that refer to data flows are properly represented in the

abstract language, while instructions that do not affect the data flows at all are

safely ignored. Thus, all control flow statements (conditionals, loops, etc.) are

not part of the simplified language. Moreover, in the abstract language name

resolution is also simplified. All identifiers are given fully scoped name, being

preceded by a dot separated list of enclosing packages, classes and methods.

In this way, no name conflict can ever occur.

The choice of a data flow sensitive/control flow insensitive program representation

is motivated by two main reasons: computational complexity and

the “nature” of the Object Oriented programs. As discussed in Section 2.4,

the theoretical computational complexity and the practical performances of

control flow insensitive algorithms are substantially superior to those of the

control flow sensitive counterparts. Moreover, the Object Oriented code is

typically structured so as to impose more constraints on the data flows than

on the control flows. For example, the sequence of method invocations may

change when moving from an application which uses a class to another one,

while the possible ways to copy and propagate object references remains more

stable. Thus, for Object Oriented code, where the actual method invocation

sequence is unknown, it makes sense to adopt control flow insensitive/data

flow sensitive analysis algorithms, which preserve the way object references

are handled.

Fig. 2.1 shows the abstract syntax of the simplified Java language. A Java

program P consists of zero or more occurrences of declarations ( D ), followed

by zero or more statements ( S ) . The actual ordering of the declarations and of

the statements is irrelevant, due to the control flow insensitivity. The nesting

structure of packages, classes and methods is completely flattened. For example,

statements belonging to different methods are not divided into separate

groups. However, the full scope is explicitly retained in the names (see below).

Consequently, a fine grain identification of the data elements is possible, while

this is not the case for the control elements (control flow insensitivity).

Transformation of a given Java program into its abstract language representation

is an easy task, that can be fully automated. Program transformation

tools can be employed to achieve this aim.

Declarations are of three types: attribute declarations (production (2)), method

declarations (production (3)) and constructor declarations (4).

An attribute declaration consists just of the fully scoped name of the attribute,

that is, a dot-separated list of packages, followed by a dot-separated list of

page number 23

classes, followed by the attribute identifier. A method declaration consists

of the fully scoped method name m (constructed similarly to the class attribute

name a), followed by the list of formal parameters f1,…,fk. In turn,

each formal parameter fi has m (the fully scoped method name) as prefix,

and the parameter identifier as dot-separated suffix. Constructors have an abstract

syntax similar to that of methods, with class names ( <cid > ) instead of

method names ( <mid > ). Declarations do not include type information, since

this is not required for OFG construction.

page number 24

Statements are of three types (see Fig. 2.1): allocation statements (production

(5)), assignment statements (production (6)) and method invocations

(production (7)).

The left hand side x of all statements (optional for method

invocations) is a program location. The right hand side y of assignment statements,

as well as the target of method invocations, is also a program location.

Program locations (<progloc>) are either local variables, class attributes or

method parameters. The former have a structure identical to that of formal

parameters: dot-separated package/class prefix, followed by a method identifier,

followed by variable identifier. Chains of attribute accesses are replaced by

the last field only, fully scoped (e.g., a.b.c becomes B. c , assuming b of class B

and class B containing field c ). The actual parameters a1,…,ak in allocations

and method invocations are also program locations (<progloc>). The variable

identifier (<vid>) that terminates a program location admits two special

values: thi s , to represent the pointer to the current object, and return, to

represent the return value of a method. Program locations (including formal

and actual parameters) of non object type (e.g., int variables) are omitted

in the chosen program representation, in that they are not associated to any

object flow. Class names in allocation statements (production (5)) consist of

a dot-separated list of packages followed by a dot-separated list of classes.

page number 25

Conditional and return statements have been skipped,

Unique names are assumed for all program entities. This is the reason

why in the abstract grammar, package, class, method, and variable identifiers

(<pid>, <cid>, <mid>, <vid>) are indicated instead of their names. Given

the source of a Java program, it is always possible to transform it so as to

make its names unique [30]. Names of overloaded methods belonging to the

same class can be augmented with an incremented integer suffix, to make

them unique. The same can be done for methods of different classes with the

same name. Calling statements are transformed correspondingly. The called

method(s) can be resolved with all statically type-compatible possibilities.

The Object Flow Graph (OFG) is a pair (N, E), comprising of a set of nodes

N and a set of edges E. A node is added to the OFG for each program location

The Object Flow Graph (OFG) is a pair (N, E), comprising of a set of nodes

N and a set of edges E. A node is added to the OFG for each program location

page number 26

(i.e., local variable, attribute or formal parameter, according to the definition

in Fig. 2.1).

Edges are added to the OFG according to the rules specified in Fig. 2.2

(right). They represent the data flows occurring in the analyzed program. The

set of OFG edges E contains all and only the pairs that result from at least

one rule in Fig. 2.2.

When a constructor or a method are invoked (statements (5) and (7),

resp.), edges are built which connect each actual parameter ai to the respective

formal parameter fi. In case of constructor invocation, the newly created

object, referenced by cs.this (with cs the constructor called by new c(…)),

is paired with the left hand side x of the related assignment (see statement

page number 27

(5)). In case of method invocation, the target object y becomes m.this inside the called method, generating the edge (y,m.this), and the value returned by method m (if any) flows to the left hand side x (pair (m.return,x)).

Edges in the OFG account for all data flows occurring in a program. While

some of them are associated with specific Java instructions, such as the assignment

or the method call, others may be related to the usage of library

classes. Each time a library class introduces a data flow from a variable x to

a variable y, an edge (x,y) must be included in the OF G .

A category of library classes that introduces additional, external data flows

is represented by containers.

Page number 28

Abstractly, container objects provide two basic operations that alter the

data flows in a program: insert, to add an object to a container, and extract,

to access an object previously inserted into a container.

Thus, for a program

with containers, the two basic cases that have to be handled in OFG construction

are the following:

(1) c.insert(x);

(2) x = c.extract( );

where c is a container and x is an object. In the first case there is a data flow

from the object x to the container c, while in the second case the data flow is

reversed. Correspondingly, the following edges are introduced in the OFG:

(1) c.insert(x);            (x,c) ∈ E

(2) x = c.extract( );     (c,x) ∈ E

The same edges would be introduced in the OFG in presence of the following

assignments:

(1) c = x;

(2) x = c:

For this reason, in the abstract program representation we have adopted,

insertion and extraction methods associated with container objects are accounted

for by transforming the related statements into assignment statements,

such as those given above.

Page number 30

Other examples of external data flows possibly affecting the nodes and

the edges in the OFG are associated with the usage of dynamic loading (e.g.,

through Java reflection) and with the access to modules written in other

programming languages (e.g., through the Java native interface, JNI). In these

cases, a semi-automated analysis of the data flows can still be conducted,

provided that the external flows are (manually) modeled in a similar way as

done above for the containers. The involvement of the user is required in the

specification of the code fragments where such flows take place and of the

program locations affected by them. Other language features not addressed

explicitly in this section, such as exception handling and multi-threading,

require minor extensions (e.g., identifying the throw-catch chains [76]) that

can be fully automated.

The OFG represents all data flows involving objects. It is thus possible to

exploit it to analyze the program’s behavior, by propagating proper information

according to the same flows along which objects are possibly propagated .

In the next chapters some examples of the kind of information to be propagated

will be given. The type to which an object is cast is one such example.

The allocation of an object at a given program point is another one. However,

in general it can be assumed that some interesting piece of information,

taken from a set V, is propagated along the OF G . Correspondingly, a flow

propagation algorithm can be given, independent of the specific elements in V.

Fig. 2.3 shows the pseudocode of the generic flow propagation algorithm.

It is a specific instance of the flow analysis framework described in [2], applied

to the OFG instead of the control flow graph. Each node n of the OFG

stores the incoming and outgoing flow information respectively inside the sets in[n] and out[n]

which are initially empty. Moreover, each node n generates

the set of flow information items contained in the gen[n] set, and prevents

the elements in the kill[n] set from being further propagated after node n.

Incoming flow information is obtained from the predecessors of node n as the

union of the respective out sets ( forward propagation ). For some analyses, it

may be appropriate to propagate flow information following the OFG edges

in reverse order ( backward propagation ). This is obtained by collecting the

incoming information from the out sets of the successors.

In other words, the

pseudo-statement 7 becomes:

![](Image00008.gif)

in case of backward propagation. Incoming flow information (in[n]) is transformed

into outgoing information out[n] by removing the elements in the set kill[n]

and adding those in gen[n] . Flow information is repeatedly propagated

inside the OFG until the fixpoint is reached: no incoming and no outgoing

information changes, in any OFG node.

Page number 31

Assuming an upper bound for the flow information propagated in the

OFG, the algorithm in Fig. 2.3 is ensured to converge in polynomial time. The

actual performance can be greatly improved by choosing a proper ordering of

the nodes in the OFG. In absence of loops, the best ordering is the partial

order induced by the graph edges. When loops are present, a good strategy

consists of propagating the flow information inside the loop before considering

the nodes following the loop.

The solution produced by the algorithm in Fig. 2.3 has the property of being

valid for all program executions that give rise to the data flows represented

in the OFG. Since the OFG has been defined in order to take into account

all statically possible data flows, the resulting solution is conservative (safe),

in that no data flow can ever occur at run time which is not represented by

a path in the OFG. However, in general it is impossible to decide statically if

a path is feasible or not (i.e., if it can actually be executed for some input).

Thus, the solution produced by the algorithm might be over-conservative, in

that it may permit flow propagation along infeasible paths. Consequently, if

a flow information is present at a node, there may be an execution of the

program that actually produces it, while if it is absent, it is ensured that no

execution can ever produce it.

Page number 32

According to the abstract syntax in Fig. 2.1, class attributes, method names,

program locations, etc., are scoped at the class level. This means that it is

possible to distinguish two locations (e.g., two class attributes) when they

belong to different classes, while this cannot be done when they belong to the

same class but to different class instances (objects) . In other words, the OFG

constructed according to the rules given in Section 2.2 is object insensitive .

While this may be satisfactory for some analyses, in some cases the ability

to distinguish among locations that belong to different objects might improve

the analysis results substantially.

An object sensitive OFG can be built by giving all non-static program

names an object scope instead of a class scope ( static attributes and program

locations that belong to static methods maintain the class scope).

Objects can be identified statically by their allocation points, thus, in an object

sensitive OFG, non-static class attributes and methods (including their

parameters and local variables) are replicated for every statically identified

object. Syntactically, an object allocation point in the code is determined by

statements of the kind (5) in Fig. 2.1\. For each such allocation point, an object

identifier is created, and all attributes and methods in the class of the

allocated object are replicated for it. Replicated program locations become

distinct nodes in the OFG.

Construction of the OFG edges becomes more complicated when locations

are object sensitive. For example, in presence of method calls, sources and

targets of OFG edges can be determined only if the current object (pointed to

by thi s ) and the objects pointed by the reference variable used as invocation

target are known. Chapter 4 provides the details of an algorithm to infer such

an information.

Page number 33

The effect of object sensitivity on the accuracy of the OFG consists of

a finer grain edge construction, resulting in a more precise propagation of

information along the data flows. In fact, information is not mixed when

propagated along different objects, in an object sensitive OF G .

Page number 34

The main difficulty in object sensitive OFG construction is the static estimation

of the objects referenced by variables. This information is necessary

whenever an attribute or a method are accessed/invoked through a reference

variable. In fact, the related edges connect locations scoped by the

pointed objects.

In order to construct an object sensitive OFG, the information about the

objects possibly referenced by program variables can be obtained by defining

a flow propagation on the OFG aiming at statically estimating the referenced

objects. This is the topic of Chapter 4\. However, the algorithm used for this

purpose assumes the availability of the OFG itself. Thus, we have a mutual

dependence. It can be solved by constructing the OFG edges incrementally.

On the contrary, all OFG nodes can be constructed from the very beginning.

Initially, all allocations points are associated to object identifiers, used to

scope the names of non-static program locations. This produces the set of all

OFG nodes. As regards edges, only internal edges can be built at this stage,

that is, edges involving constructor/method parameters or local variables, that

are replicated for every object scope

Invocation of methods and access to class attributes require knowledge

about the objects referenced by variables and by the special location thi s .

Such information is approximated by a first round of flow propagation. At the

page number 35

end of the propagation, edges can be added to the OFG for method calls and

attribute accesses, using the objects pointed to by the related variables, as

determined by the flow propagation. On the new version of the OFG obtained

in this way, including the edges produced by the result of the previous flow

propagation, a better estimate of the objects pointed by variables can be

obtained. Refinement of the OFG can continue, until a stable one is produced

(it should be noted that the incremental construction is monotone, in that

edges are possibly added, but never removed).

Complete construction of an object sensitive OFG is possible only if the

whole program is available (including the mai n ), since all allocation points

of all involved objects must be part of the code under analysis. In Object-

Oriented programming this may not be the case, since incomplete systems

are often produced and classes are often reused in different contexts. In these

situations, an object insensitive OFG construction may be more appropriate.

Page number 40

The OFG and the related flow propagation algorithms are based on research

conducted on pointer analysis

The aim of pointer

analysis is to obtain a static approximation of any points-to relationship that

may hold at run-time between pointers and program locations. Similarly, when

Object-Oriented programs are considered, the relationship between reference

variables and objects is analyzed.

Pointer analysis algorithms can be divided into flow/context sensitive [21,

47, 60] and flow/context insensitive [3, 81]. Flow/context sensitive algorithms

produce fine grained and accurate results, in that a points-to relationship is

determined that holds at every program statement. Moreover, different invocation

contexts can be distinguished. However, the computational complexity

involved in these approaches is high, and in practice their performance does

not scale to large software systems. Flow/context insensitive algorithms have

lower complexity and scale well. On the other side, they produce results that

hold for the whole program, and the points-to relationships they derive cannot

page number 41

be distinguished by statement or invocation context. Flow/context sensitive

analyses are defined with reference to the control flow graph [2] of a program,

while flow/context insensitive algorithms define the analysis semantics at the

statement level.

page number 155

This chapter deals with the practical issues related to the adoption of reverse

engineering techniques within an Object Oriented software development process.

Tool support and integration is one of the main concerns. This chapter

contains some considerations on a general architecture for tools that implement

the techniques presented in the previous chapters. A survey of the existing

support and of the current practice in reverse engineering is also provided.

Once an automated infrastructure for reverse engineering is in place, the

process of software evolution has to be adapted so as to smoothly integrate

the newly offered functionalities. This accounts for revising the main activities

in the micro-process of software maintenance. The kind of support offered to

program understanding has been already described in detail (see Chapter 1,

eLib example). The way other activities are affected by the integration of a

reverse engineering tool in the development process are described in this chapter,

by reconsidering the eLib program and the change requests sketched in

Chapter 1\. Location of the changes in the source code, change implementation

and assessment of the ripple effects are conducted on the eLib program, using,

whenever possible, the information reverse engineered from the code.

A vision of the software development process that could be realized by

exploiting the potential of reverse engineering concludes the chapter. The opportunities

offered by new programming languages and paradigms for reverse

engineering are outlined, as well as the possibility of integration with emerging

development processes.

This chapter is organized as follows: Section 8.1 describes the main modules

to be developed in a reverse engineering tool for Object Oriented code.

Reverse engineered diagrams can be exploited for change location and implementation,

as well as for change impact analysis. Their usage with the eLib

program is presented in Section 8.2\. The authors’ perspectives on potential

improvements of the current practices are given in Section 8.3, with reference

to new programming languages and development processes. Finally, related

works are commented in the last section of the chapter.

page number 156

Implementation of the algorithms described in the previous chapters is affected

by practical concerns, such as the target programming language, the available

libraries, the graphical format of the resulting diagrams, etc. However, it is

possible to devise a general architecture to be instantiated in each specific

case. In this architecture, functionalities are assigned to different modules, so

as to achieve a decomposition of the main task into manageable, well-defined

sub-tasks. In turn, each module requires a specialization that depends on the

specific setting in which the actual implementation is being built.

Fig. 8.1 shows the main processing steps performed by the modules composing

a reverse engineering tool. The first module, Parser, is responsible

for handling the syntax of the source programming language. It contains the

grammar that defines the language under analysis. It parses the source code

and builds the derivation tree associated with the grammar productions. A

higher-level view of the derivation tree is preferable, in order to decouple successive

modules from the specific choices made in the definition of the grammar

for the target language. Specifically, the intermediate non-terminals used

in each grammar production are quite variable, being strongly dependent on

the way the parser handles ambiguity (e.g., bottom-up and top-down parsers

require very different organizations of the non-terminals). For this reason, it

is convenient to transform the derivation tree into a more abstract tree representation

of the program, called the Abstract Syntax Tree (AST) . In this

program representation, chains of intermediate non-terminals are collapsed,

and only the main syntactic categories of the language are represented [2].

The AST is a program representation that reflects the syntactic structure

of the code. However, reverse engineering tools are based on a somewhat different

view of the source code. In the remainder of this chapter, this view is

referenced as the language model assumed by a reverse engineering tool. In a

language model, several syntactic details can be safely ignored. For example,

the tokens delimiting blocks of statements (curly braces, begi n , en d , etc.)

are irrelevant, while the information of interest is the actual presence of a

page number 157

sequence of statements. Thus, in the language model, tokens such as delimiters

of statement blocks and parameters, separators in parameter lists and

statement sequences, etc., are absent. On the other hand, information not

explicitly represented in the AST is made directly available in the language

model. For example, each variable involved in an expression is linked to its

declaration. Each method call is resolved in terms of all the type-compatible

definitions of the invoked method. Each class is associated with its superclass,

as well as the interfaces it implements. Such cross-references are not

obtained by means of plain identifiers, as in the AST, but are links toward

the referenced elements in the language model. For example, if class A extends

class B , the AST for class A contains just a child node for the extends clause,

leading to the identifier B , while in the language model an association exists

between the model element for class A and the model element for class B . An

example of (simplified) language model for the Java language is described in

detail below. The module responsible for building the language model out of

the AST of an input program is the Model Extractor (see Fig. 8.1).

Based upon the language model of the input program, reverse engineering

algorithms can be executed to recover alternative design views. The output is

a set of diagrams to be displayed to the user. In some cases, a further abstraction

of the language model that Reverse Engineering algorithms have in input

is necessary. For example, most (but not all) of the techniques described in the

previous chapters require that the data flows in the target Object Oriented

program be abstracted into a data structure called the Object Flow Graph

(OFG) . Such a data structure is built internally into the Reverse Engineering

module and is shared by all the algorithms that depend on it. Flow propagation

of proper information inside the OFG leads to the recovery of the design

views of interest. These are converted into a graphical format of choice, in

order for the final user to be able to visualize them.

Since reverse engineering techniques span over a wide spectrum, depending

on the kind of high-level information being recovered, it is quite important

to design a general language model that supports all of the alternative algorithms.

In turn, each algorithm may have an internal representation of the

source code, different from the language model itself. However, the main requirement

on the language model is that all the information necessary for the

reverse engineering algorithms to work and (possibly) build their own internal

data structures must be available in the language model. Thus, the language

model plays a critical, central role in the architecture described above and

should be designed very carefully . An example of such a model is given in

Fig. 8.2 for the Java language. Only the most important entities are shown

(for space reasons), with no indication of their properties.

A Java source file contains the definition of classes within a name space

called package. In turn, packages can be nested. Thus, the topmost entity

page number 158

in the language model for Java (see Fig. 8.2, left) is the package and a selfcontainment

relationship in the package entity represents nesting. Eventually,

packages contain classes (containment from package to class in Fig. 8.2). The

main property of the entity package (not shown in Fig. 8.2) is its name, that

uniquely identifies it.

The properties of the entity class include the name, visibility, as well as its

superclass, implemented interfaces, etc. The entities in turn contained inside

classes are the class members. Thus, the entity class is connected to the entity

attribute and to the entity method. Moreover, classes can be nested inside other

classes. This is the reason for the self-containment outgoing from the entity

class.

The entity attribute has properties such as name, type, visibility, initializer,

etc. Similarly, the entity method has properties such as name, formal parameters,

return type, visibility, etc. The body of each method is represented as a

sequence of statements in the language model (containment from method to

statement labeled body in Fig. 8.2).

Statements can be of different types. Some of them are enumerated in

Fig. 8.2, connected to their abstraction statement by an inheritance relationship.

Conditional statements are used for constructs such as if and switc h .

Among their properties, they hold a reference to the expression entity used

in the tested condition (not shown in Fig. 8.2). The if conditional statement

has a then-part and an else-part, which are in turn sequences of statements

(similarly to the body of a method). The switch statement is associated with

a sequence of case s , each containing the respective statements to execute.

Loop statements include whil e , for and do-while loops. Their main properties

are the tested condition (an expression entity, not shown in Fig. 8.2) and

the loop body (a sequence of statement s ) . For loops have also an initializer

and an increment part.

Assignment statements have two main components, the left hand side and

the right hand side. While the latter is a generic expression, the former must

eventually reference a location. This is achieved by constraining it to a unary

expression, instead of a generic expression.

Page number 159

Call statements involve a dereference chain (primary expression), eventually

leading to the object which is the target of the invocation. Other important

properties are the name of the called method, the actual parameter list

(a list of expression s ) , and links toward all type-compatible methods in the

language model. In the case of an invocation of a library method, the call is

marked as library call.

When the control flow inside a method is interrupted to return a value to

the caller, a return statement is encountered. The main property of this entity

is the expression that defines the returned value.

Among the entities and relationships not shown in Fig. 8.2 for space reasons,

the most important one is the entity expression, accounting for all mathematical

expressions supported by the language, possibly intermixed with

method invocations. The sub-hierarchy of the expression entities closely resembles

that available in most programming languages (either procedural or

Object Oriented).

The information represented according to the model in Fig. 8.2 is sufficient

to build the OFG for a given source code, as well as to conduct all other

analyses that do not depend on the OFG and have been described in the

previous chapters. Thus, it can be used as the basic representation exploited

by all reverse engineering techniques implemented in the Reverse Engineering

module.

Page number 170

The authors’ position is that all the information about a program should be

in the source code. From a purely observational point of view, the well-known

effects of software evolution, consisting of a progressive misalignment of source

code and other sources of information about a program, entail that only the

source code is reliable. So, de-facto, most information about a program is

in the source code. On the prescriptive side, one could take as the extreme

page number 171

consequence the fact that everything should be part of the code (including

design, documentation, etc.).

The first view gives a central role to reverse engineering in the future of

software development. Although this discipline was born with the problems of

legacy systems in mind, new software systems, developed according to modern

programming paradigms such as the Object Oriented one, are not free from

the problems related to program comprehension and modification. As described

in this book, the comprehension problems involved in understanding

Object Oriented systems are different from those arising with more traditional

software, but remain the main concerns during the evolution phase. Reverse

engineering has the potential to address them.

The view in which all relevant information about a program is centralized

in a single source, the code, comes from the Extreme Programming (XP)

development process [36]. In this methodology, limited effort is devoted to

design and design documents are not maintained over time. They are considered

a temporary support to communication and understanding, that is

abandoned when software engineers move to the implementation. The absence

of design information is mitigated by pair programming, by continuous

execution of refactoring, and by the description of functionalities in terms of

test cases. Reverse engineering can make an important contribution here [93].

In fact, understanding the organization of an application and of the interactions

among its objects is a quite difficult task in the XP setting. As discussed

in this book, there are several diagrams that can be extracted automatically

from the source code and approximate quite well this kind of information.

Looking at the emerging programming languages and paradigms, we can

hypothesize an increasing role of reverse engineering. Programming languages

tend to evolve so as to maintain very precise information about the program’s

behavior in the source code. Modern compilers rely on this information to

perform several checks, optimizations and transformations. Examples of this

kind of information are type parameters (genericity) and metadata (e.g., annotations),

that will be included in the next version (1.5) of the Java language.

Aspect Oriented Programming [40] and introspection capabilities (e.g., Java

reflection, OpenJava) are going in the same direction, in that they support a

programmable interface to the internal units of a program.

All this has a twofold effect. On one hand, it simplifies reverse engineering,

in that the source code becomes a richer information repository, that can

be queried automatically by tools. On the other hand, it makes the design

diagrams reverse engineered from the source code much more meaningful and

useful, in that they are based on information directly encoded in the program

(and checked by the compiler), instead of using information inferred by means

of approximate static or dynamic analysis methods. Availability of accurate

diagrams easily extracted from the code will make the reverse engineering

option even more appealing, getting closer to the XP vision that everything is

in the source code. In fact, maintaining and evolving multiple descriptions of

a software system is much too expensive and error prone. Only by focusing on

page number 172

the source code as the single source of information, is it possible to keep costs

low and to avoid communication errors resulting from inconsistent views.

Page number 156

![](Image00009.jpg)

![](Image00010.jpg) page number 23

![](Image00011.jpg)

page number 26

![](Image00012.jpg)

![](Image00013.jpg)

page number 158

![](Image00014.jpg) ![](Image00015.jpg)

![](Image00016.jpg) ![](Image00017.jpg)

![](Image00018.jpg) change line number 7 to be backward propagation .

Chapter 4 : CASE STUDY (library system)

4.1 CASE tools

CASE tools :

Modeler : Modelio, IDE : Eclipse, and Compiler : JDK .

library system execution :

![](Image00019.jpg)

4.2 source code

source code :

Main.java

import java.util.*;

import java.io.*;

class Main {

static Library lib = new Library();

public static void printHeader() {

System.out.println("COMMANDS:");

System.out.println("addUser name, address, phone");

System.out.println("addIntUser name, address, phone, id");

System.out.println("rmUser userId");

System.out.println("addBook title, authors, ISBN");

System.out.println("addReport title, ref, authors");

System.out.println("addJournal title");

System.out.println("rmDoc docId");

System.out.println("borrowDoc userId, docId");

System.out.println("returnDoc docId");

System.out.println("searchUser name");

System.out.println("searchDoc title");

System.out.println("isHolding userId, docId");

System.out.println("printLoans");

System.out.println("printUser userId");

System.out.println("printDoc docId");

System.out.println("exit");

}

public static String[] getArgs(String cmd) {

String args [] = new String [0] ;

String s = cmd.trim();

if (s.indexOf(" ") != -1) {

s = s.substring(s.indexOf(" "));

args = s.trim().split(",");

for (int i = 0 ; i < args.length ; i++)

args[i] = args[i] .trim() ;

}

return args;

}

public static void addUser(String cmd) {

String args[] = getArgs (cmd);

if (args.length < 3) return;

User user = new User (args [0] , args[1], args [2] );

lib.addUser(user);

System.out.println("Added user: " + user.getCode() +

" - " + user .getName());

}

public static void addIntUser(String cmd) {

String args[] = getArgs (cmd);

if (args.length < 4) return;

User user = new InternalUser(args[0] , args[1], args [2] , args[3]);

lib.addUser(user);

System.out.println("Added user: " + user.getCode() +

" - " + user.getName());

}

public static void rmUser(String cmd) {

String args[] = getArgs (cmd);

if (args.length < 1) return;

User user = lib.getUser(Integer.parseInt(args[0]));

if (lib.removeUser(Integer.parseInt(args[0])))

System.out.println("Removed user: " + user.getCode() +

" - " + user.getName()) ;

}

public static void addBook(String cmd) {

String args [] = getArgs (cmd) ;

if (args.length < 3) return;

Document doc = new Book(args [0] , args[1], args [2]);

lib.addDocument(doc);

System.out.println("Added doc: " + doc.getCode() +

" - " + doc.getTitle());

}

public static void addReport (String cmd) {

String args[] = getArgs(cmd);

if (args.length < 3) return;

Document doc = new TechnicalReport(args[0], args[1], args [2]);

lib.addDocument(doc);

System.out.println("Added doc: " + doc.getCode() +

" - " + doc.getTitle()) ;

}

public static void addJournal(String cmd) {

String args [] = getArgs(cmd);

if (args.length < 1) return;

Document doc = new Journal(args[0]);

lib.addDocument(doc);

System.out.println("Added doc: " + doc.getCode() +

" - " + doc.getTitle());

}

public static void rmDoc (String cmd) {

String args [] = getArgs(cmd);

if (args.length < 1) return;

Document doc = lib.getDocument(Integer.parseInt(args[0]));

if (lib.removeDocument(Integer.parseInt(args[0])))

System.out.println("Removed doc: " + doc.getCode() +

" - " + doc.getTitle());

}

public static void borrowDoc(String cmd) {

String args[] = getArgs(cmd) ;

if (args.length < 2) return;

User user = lib.getUser(Integer.parseInt(args[0]));

Document doc = lib.getDocument(Integer.parseInt(args[1]));

if (user == null || doc == null) return;

if (lib.borrowDocument(user, doc))

System.out.println("New loan: " + user .getName() +

" - " + doc.getTitle());

}

public static void returnDoc(String cmd) {

String args[] = getArgs(cmd);

if (args.length < 1) return;

Document doc = lib.getDocument(Integer.parseInt(args[0]));

if (doc == null) return;

User user = doc.getBorrower();

if (user == null) return;

if (lib.returnDocument(doc))

System.out.println("Loan closed: " + user.getName() +

" - " + doc.getTitle());

}

public static void searchUser(String cmd) {

String args [] = getArgs(cmd);

if (args.length < 1) return;

List users = lib.searchUser(args[0]);

Iterator i = users.iterator();

while (i.hasNext()) {

User user = (User)i.next();

System.out.println("User found: " + user.getCode() +

" - " + user.getName());

}

}

public static void searchDoc(String cmd) {

String args[] = getArgs(cmd);

if (args.length < 1) return;

List docs = lib.searchDocumentByTitle(args[0]);

Iterator i = docs.iterator();

while (i.hasNext()) {

Document doc = (Document)i.next();

System.out.println("Doc found: " + doc.getCode() +

" - " + doc.getTitle()) ;

}

}

public static void isHolding(String cmd) {

String args[] = getArgs(cmd);

if (args.length < 2) return;

User user = lib.getUser(Integer.parseInt(args [0]));

Document doc = lib.getDocument(Integer.parseInt(args[1]));

if (lib.isHolding(user, doc))

System.out.println(user.getName() +

" is holding " + doc.getTitle());

else

System.out.println(user.getName() +

" is not holding " + doc.getTitle());

}

public static void printUser(String cmd) {

String args[] = getArgs (cmd);

if (args.length < 1) return;

User user = lib.getUser(Integer.parseInt(args[0]));

if (user != null)

user.printInfo();

}

public static void printDoc(String cmd) {

String args [] = getArgs(cmd);

if (args.length < 1) return;

Document doc = lib.getDocument(Integer.parseInt(args[0]));

if (doc != null)

doc.printInfo();

}

public static void dispatchCommand(String cmd) {

if (cmd.startsWith("addUser")) addUser(cmd);

if (cmd.startsWith("addIntUser")) addIntUser(cmd) ;

if (cmd.startsWith("rmUser")) rmUser(cmd);

if (cmd.startsWith("addBook")) addBook(cmd) ;

if (cmd.startsWith("addReport")) addReport(cmd);

if (cmd.startsWith("addJournal")) addJournal(cmd);

if (cmd.startsWith("rmDoc")) rmDoc(cmd);

if (cmd.startsWith("borrowDoc")) borrowDoc(cmd);

if (cmd.startsWith("returnDoc")) returnDoc(cmd);

if (cmd.startsWith("searchUser")) searchUser(cmd);

if (cmd.startsWith("searchDoc")) searchDoc(cmd);

if (cmd.startsWith("isHolding")) isHolding(cmd);

if (cmd.startsWith("printLoans")) lib.printAllLoans();

if (cmd.startsWith("printUser")) printUser(cmd);

if (cmd.startsWith("printDoc")) printDoc(cmd);

}

public static void main(String arg[]) {

try{

printHeader();

String s = "";

BufferedReader in = new BufferedReader(

new InputStreamReader(System.in));

while (!s.equals("exit")) {

s = in.readLine() ;

dispatchCommand(s);

}

} catch (IOException e) {

System.err.println("IO error.");

System.exit(1);

}

}

}

Library.java

import java.util.*;

import java.io.*;

class Library {

Map documents = new HashMap();

Map users = new HashMap();

Collection loans = new LinkedList();

final int MAX_NUMBER_OF_LOANS = 20;

public boolean addUser(User user) {

if (!users.containsValue(user)) {

users.put(new Integer(user.getCode()), user);

return true;

}

return false;

}

public boolean removeUser(int userCode) {

User user = (User)users.get(new Integer(userCode));

if (user == null || user.numberOfLoans() > 0) return false;

users.remove(new Integer(userCode));

return true;

}

public User getUser(int userCode) {

return (User)users.get(new Integer(userCode));

}

public boolean addDocument(Document doc) {

if (!documents.containsValue(doc)) {

documents.put(new Integer(doc.getCode()), doc);

return true;

}

return false;

}

public boolean removeDocument(int docCode) {

Document doc = (Document)documents.get(new Integer(docCode));

if (doc == null || doc.isOut()) return false;

documents.remove(new Integer(docCode));

return true;

}

public Document getDocument(int docCode) {

return (Document)documents.get(new Integer(docCode));

}

private void addLoan(Loan loan) {

if (loan == null) return;

User user = loan.getUser();

Document doc = loan.getDocument();

loans.add(loan);

user.addLoan(loan);

doc.addLoan(loan);

}

private void removeLoan(Loan loan) {

if (loan == null) return;

User user = loan.getUser();

Document doc = loan.getDocument();

loans.remove(loan);

user.removeLoan(loan);

doc.removeLoan();

}

public boolean borrowDocument(User user, Document doc) {

if (user == null || doc == null) return false;

if (user.numberOfLoans() < MAX_NUMBER_OF_LOANS &&

doc.isAvailable() && doc.authorizedLoan(user)) {

Loan loan = new Loan(user, doc);

addLoan(loan);

return true;

}

return false;

}

public boolean returnDocument(Document doc) {

if (doc == null) return false;

if (doc.isOut()) {

User user = doc.getBorrower();

Loan loan = new Loan(user, doc);

removeLoan(loan);

return true;

}

return false;

}

public boolean isHolding(User user, Document doc) {

if (user == null || doc == null) return false;

return loans.contains(new Loan(user, doc));

}

public List searchUser(String name) {

List usersFound = new LinkedList();

Iterator i = users.values().iterator();

while (i.hasNext()) {

User user = (User)i.next();

if (user.getName().indexOf(name) != -1)

usersFound.add(user);

}

return usersFound;

}

public List searchDocumentByTitle(String title) {

List docsFound = new LinkedList();

Iterator i = documents.values().iterator();

while (i.hasNext()) {

Document doc = (Document)i.next();

if (doc.getTitle().indexOf(title) != -1)

docsFound.add(doc);

}

return docsFound;

}

public List searchDocumentByAuthors(String authors) {

List docsFound = new LinkedList();

Iterator i = documents.values().iterator();

while (i.hasNext()) {

Document doc = (Document)i.next();

if (doc.getAuthors().indexOf(authors) != -1)

docsFound.add(doc);

}

return docsFound;

}

public int searchDocumentByISBN(String isbn) {

Iterator i = documents. values() . iterator() ;

while (i.hasNext()) {

Document doc = (Document)i.next();

if (isbn. equals (doc. getISBN()))

return doc.getCode();

}

return -1;

}

public void printAllLoans() {

Iterator i = loans.iterator();

while (i.hasNext()) {

Loan loan = (Loan)i.next();

loan.print();

}

}

public void printUserInfo(User user) {

user.printInfo();

}

public void printDocumentInfo(Document doc) {

doc.printInfo();

}

}

Loan.java

class Loan {

User user;

Document document;

public Loan(User usr, Document doc) {

user = usr;

document = doc;

}

public User getUser() {

return user;

}

public Document getDocument() {

return document;

}

public boolean equals(Object obj) {

Loan loan = (Loan)obj;

return user.equals(loan.user) &&

document.equals(loan.document);

}

public void print() {

System.out.println("User: " + user.getCode() +

" - " + user .getName() +

" holds doc: " + document.getCode() +

" - " + document.getTitle());

}

}

Document.java

import java.util.*;

class Document {

int documentCode;

String title;

String authors;

String ISBNCode;

Loan loan = null;

static int nextDocumentCodeAvailable = 0;

public Document(String tit) {

title = tit;

ISBNCode = "";

authors = "";

documentCode = Document.nextDocumentCodeAvailable++;

}

public boolean equals(Object obj) {

Document doc = (Document)obj;

return documentCode == doc.documentCode;

}

public boolean isAvailable() {

return loan == null;

}

public boolean isOut() {

return ! isAvailable() ;

}

public boolean authorizedLoan(User user) {

return true;

}

public User getBorrower() {

if (loan != null)

return loan.getUser();

return null;

}

public int getCode() {

return documentCode;

}

public String getTitle() {

return title;

}

public String getAuthors() {

return authors;

}

public String getISBN() {

return ISBNCode;

}

public void addLoan(Loan ln) {

loan = ln;

}

public void removeLoan() {

loan = null;

}

protected void printAuthors() {

System.out.println("Author(s): " + getAuthors());

}

protected void printHeader() {

System.out.println("Document: " + getCode() +

" - " + getTitle());

}

protected void printAvailability() {

if (loan == null) {

System.out.println("Available.");

} else {

User user = loan.getUser();

System.out.println("Hold by " + user.getCode() +

" - " + user .getName()) ;

}

}

protected void printGeneralInfo() {

System.out.println("Title: " + getTitle());

if (!getISBN().equals(""))

System.out.println("ISBN: " + getISBN());

}

public void printInfo() {

printHeader();

printGeneralInfo();

printAvailability();

}

}

Book.java

class Book extends Document {

public Book(String tit, String auth, String isbn) {

super(tit);

ISBNCode = isbn;

authors = auth;

}

public void printInfo() {

printHeader() ;

printAuthors();

printGeneralInfo();

printAvailability();

}

}

TechnicalReport.java

class TechnicalReport extends Document {

String refNo;

public TechnicalReport(String tit, String ref, String auth) {

super(tit);

refNo = ref;

authors = auth;

}

public boolean authorizedLoan(User user) {

return false;

}

public String getRefNo() {

return refNo;

}

protected void printRefNo() {

System.out.println("Ref. No.: " + getRefNo());

}

public void printInfo() {

printHeader() ;

printAuthors();

printGeneralInfo() ;

printRefNo() ;

}

}

Journal.java

class Journal extends Document {

public Journal(String tit) {

super(tit);

}

public boolean authorizedLoan(User user) {

return user.authorizedUser();

}

}

User.java

import java.util.*;

class User {

int userCode;

String fullName;

String address;

String phoneNumber;

Collection loans = new LinkedList();

static int nextUserCodeAvailable = 0;

public User(String name, String addr, String phone) {

fullName = name;

address = addr;

phoneNumber = phone;

userCode = User.nextUserCodeAvailable++;

}

public boolean equals(Object obj) {

User user = (User)obj;

return userCode == user.userCode;

}

public boolean authorizedUser() {

return false;

}

public int getCode() {

return userCode;

}

public String getName() {

return fullName;

}

public String getAddress() {

return address;

}

public String getPhone() {

return phoneNumber;

}

public void addLoan(Loan loan) {

loans.add(loan);

}

public int numberOfLoans() {

return loans.size();

}

public void removeLoan(Loan loan) {

loans.remove(loan);

}

public void printInfo() {

System.out.println("User: " + getCode() + " - " + getName());

System.out.println("Address: " + getAddress());

System.out.println("Phone: " + getPhone());

System.out.println("Borrowed documents:");

Iterator i = loans.iterator();

while (i.hasNext()) {

Loan loan = (Loan)i.next();

Document doc = loan.getDocument();

System.out. println(doc.getCode() + " - " + doc.getTitle());

}

}

}

InternalUser.java

class InternalUser extends User {

String internalId;

public InternalUser(String name, String addr,

String phone, String id) {

super(name, addr, phone);

internalId = id;

}

public boolean authorizedUser() {

return true;

}

}

4.3 abstract syntax tree (AST)

abstract syntax tree (AST) :

BNF :

P ::= D* S*

D ::= a | m(fk) | cs(fk)

S ::= x = new c(ak) | x = y | [x=] y.m(ak)

so we can construct AST for a library system source code .

4.4 language model

language model :

class model :

![](Image00020.gif)

4.5 OFG, and flow propagation

OFG, and flow propagation :

abstract code for class Main (attribute allocation) :

Main.lib  = new Library( )

OFG edges {(Library.Library.this, Main.lib)}

abstract code for class Main (method addUser) :

Main.addUser.user = new User( )

OFG edges {(User.User.this, Main.addUser.user)}

Main.lib.addUser(Main.addUser.user)

OFG edges {(Main.addUser.user,Library.addUser.user)}

abstract code for class Main (method addIntUser) :

Main.addIntUser.user = new InternalUser( )

OFG edges {(InternalUser.InternalUser.this, Main.addIntUser.user)}

Main.addUser.this.Library.addUser(Main.addIntUser.user)

OFG edges {(Main.addIntUser.user,Library.addUser.user)}

abstract code for class Main (method addBook) :

Main.addBook.doc = new Book( )

OFG edges {(Book.Book.this, Main.addBook.doc)}

Main.addDocument.this.Library.addDocument(Main.addBook.doc)

OFG edges {(Main.addBook.doc, Library.addDocument.doc)}

abstract code for class Main (method addReport) :

Main.addReport.doc = new TechnicalReport( )

OFG edges {(TechnicalReport.TechnicalReport.this, Main.addReport.doc)}

Main.addDocument.this.Library.addDocument(Main.addReport.doc)

OFG edges {(Main.addReport.doc, Library.addDocument.doc)}

abstract code for class Main (method addJournal) :

Main.addJournal.doc = new Journal( )

OFG edges {(Journal.Journal.this, Main.addJournal.doc)}

Main.addDocument.this.Library.addDocument(Main.addJournal.doc)

OFG edges {(Main.addJournal.doc, Library.addDocument.Doc)}

abstract code for class Main (method borrowDoc) :

Main.borrowDoc.user = Library.getUser.return

OFG edges : {(Library.getUser.return, Main.borrowDoc.user)}

Main.borrowDoc.doc = Library.getDocument.return

OFG edges {(Library.getDocument.return, main.borrowDoc.doc)}

object insensitive OFG (driver class)

![](Image00021.jpg)

![](Image00022.jpg)

object insensitive OFG (core classes)

![](Image00023.jpg)

4.6 class diagram

class diagram :

![](Image00024.jpg)

4.7 object diagram

object diagram :

![](Image00025.jpg)

4.8 change location

change location :

new class diagram :

![](Image00026.jpg)

4.9 impact of the change

impact of the change :

new object diagram :

![](Image00027.jpg)