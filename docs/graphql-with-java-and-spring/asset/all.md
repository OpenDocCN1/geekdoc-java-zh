![](media/cover.png)

1.  [Title Page](text/title_page.xhtml)
2.  [Cover](text/cover.xhtml)
3.  [Table of Contents](#nav.xhtml_toc)

# GraphQL with Java and Spring

# Prologue

## Andi (Andreas)

In 2015, I (Andi) was working as a software developer for a small company in Berlin, Germany. During a conversation, one of my colleagues (thanks a lot Stephan!) mentioned to me this new technology called “GraphQL”, aimed at improving the way clients access data from a service, and they planned to release it soon.

After looking into GraphQL, it immediately convinced me of the value it could provide. Of course, I could not predict its success, but I experienced firsthand in multiple companies the struggles of creating and maintaining a REST API. Despite serious effort, they all looked more like GraphQL over time rather than how a good REST API was supposed to look. Perhaps it came from a lack of understanding REST, but after I had witnessed very similar challenges again and again in very different contexts, I thought otherwise.

Being convinced of the value, I started immediately working on a Java implementation after they released the GraphQL specification. After about two weeks of investing all the free time I had outside my job, I released the first version of GraphQL Java.

While it was just me in the beginning, shortly after I received the first PR that fixed a typo. Today more than [200 people](https://github.com/graphql-java/graphql-java/graphs/contributors) have contributed to GraphQL Java and without them there would be no GraphQL Java. Sincerely, thanks a lot to all of you.

Many thanks and a special mention belongs to [Brad Baker](https://github.com/bbakerman), who has been a co-maintainer for over six years. There is no way to overstate his contributions and influence on GraphQL Java. It is as much his project as it is mine.

Most importantly I want to thank my wife Elli for all her support: without her there would be no book today.

## Donna

I (Donna) am thrilled to write this book with Andi, who created GraphQL Java and played a major role in the creation of Spring for GraphQL. Andi, Brad, and I are the maintainers of GraphQL Java.

I discovered programming later in life, initially it was only a hobby. One of the first programming ideas I learned about was open source software. As a profit-maximising investment banker, it seemed delightfully nuts that high quality work could be happily given away for free. I adored the spirit of collaboration and community in the open source world. I adored it so much that I changed careers and became a software engineer.

Thanks to everyone in the GraphQL Java community for your contributions over the years.

## About this book

This book is for anyone who wants to build a production GraphQL service with Java. By the end of this book, you will be confident building your own production GraphQL service with Spring for GraphQL, the official Spring integration built on top of the GraphQL Java engine. Spring for GraphQL makes it easier than ever to build a GraphQL service by eliminating boilerplate code and seamlessly integrating with the Spring ecosystem.

GraphQL Java is the dominant Java implementation of GraphQL, powering services at Twitter, AirBnB, Netflix, Atlassian, and many other companies. By the end of this book, you’ll be leveraging the same engine with Spring for GraphQL.

In this book, you’ll learn key GraphQL concepts, paired with practical advice from our experiences running production GraphQL services at scale. At the end of this book, you’ll have in depth knowledge of Spring for GraphQL and the GraphQL Java engine, so you will have the confidence to run production ready GraphQL services.

This book is suitable for beginners building their first production GraphQL service. There are also advanced topics later in the book for intermediate readers.

We do not assume any prior knowledge of GraphQL. To make the most of this book, we assume basic Java knowledge, and we assume very basic [Spring](https://spring.io/) knowledge such as familiarity with the `@Component` annotation. Optionally, if you intend to build a reactive service, you should be familiar with the Reactor concepts of `Mono` and `Flux`.

All code examples were written with Java 17, which is the minimum version required for Spring Boot 3.x. Examples in this book were written with Spring Boot 3.0.4 and Spring for GraphQL 1.1.2, which uses GraphQL Java 19.2.

If you have feedback or comments on the book, please let us know via email at book-feedback@graphql-java.com.

We deeply hope you enjoy this book.

Special thanks to our reviewers for giving us fantastic feedback. Thanks to Rossen Stoyanchev and Brian Clozel from the Spring for GraphQL team, our technical reviewer Doug Warren, our reviewers Brad Baker, Antoine Boyer, Felipe Reis, Stephan Behnke, and Josh Long. Thanks to our cover designer Mike Riethmuller.

Version: 0aab44c

Date: Sun May 14 23:18:20 UTC 2023

# Introduction

## Your first Spring for GraphQL service

The best way to get a feeling for GraphQL is to experience it. We will walk through how to create your first Spring for GraphQL service, step by step. In the coming chapters, we will explain these steps in greater detail.

First, create a new project with [Spring Initializr](https://start.spring.io), at https://start.spring.io. In this book, we will use Spring Boot 3.x which requires at least Java 17\. If you prefer to use Java 11, select a Spring Boot version of at least 2.7.0 to use Spring for GraphQL. You can choose between a Maven or Gradle project.

In the dependencies section, add Spring for GraphQL. We’ll then need to add one more dependency for underlying transport. You can choose either Spring Reactive Web (WebFlux) or Spring Web (Spring MVC). In this book, we’ll be using Spring Reactive Web to make use of the WebFlux framework and the Netty server for reactive services. If you choose Spring Web (which includes Spring MVC), all content in this book is still applicable to your service, as Spring for GraphQL fully supports both Spring MVC and WebFlux. All examples in this book are almost identical for Spring MVC, the only difference is that controller methods will not be wrapped in a `Mono` or `Flux`.

You can add your own project metadata, or follow along with our example in the screenshot “Spring Start”.

![Spring Start](media/file0.png)

Spring Start

Click Generate at the bottom of the page to generate your project. Open the project in your favourite code editor. Start the application from the `main` method in `myservice.service.ServiceApplication`. It will start an HTTP endpoint at `http://localhost:8080`, but not much else yet!

Let’s make this service more useful and implement a very simple GraphQL service, which serves pet data. To keep this initial example simple, the data will be an in-memory list. Later, in the [Building a GraphQL service chapter](#ch008.xhtml_building-a-graphql-service), we’ll extend this example to call another service.

For this initial example, we’ll cover concepts at a high level, so we can quickly arrive at a working service you can interact with. In the coming chapters, we will explain these concepts in greater detail.

Let’s start by creating a GraphQL schema, which is a static description of the API. Create a new subdirectory “graphql” under “resources”. Paste the following into a new file `src/main/resources/graphql/schema.graphqls`.

```
[](#cb1-1)type Query {
[](#cb1-2)    pets: [Pet]
[](#cb1-3)}
[](#cb1-4)
[](#cb1-5)type Pet {
[](#cb1-6)    name: String
[](#cb1-7)    color: String
[](#cb1-8)}
```

This GraphQL schema for pets is written in Schema Definition Language (SDL) format. This defines a GraphQL query type with a pets field, which returns a list of pets. Each pet has a name and color, and both fields are string attributes. In the [Schema chapter](#ch005.xhtml_schema-chapter), we’ll discuss GraphQL schema elements in depth.

Add a Pet record class in the package `myservice.service`.

```
[](#cb2-1)package myservice.service;
[](#cb2-2)
[](#cb2-3)record Pet(String name, String color) {
[](#cb2-4)}
```

Next, we’ll add the logic to connect our schema with the pet data. Create a new Java class `PetsController` in the package `myservice.service`.

```
[](#cb3-1)package myservice.service;
[](#cb3-2)
[](#cb3-3)import org.springframework.graphql.data.method.annotation
[](#cb3-4)  .QueryMapping;
[](#cb3-5)import org.springframework.stereotype.Controller;
[](#cb3-6)
[](#cb3-7)import java.util.List;
[](#cb3-8)
[](#cb3-9)@Controller
[](#cb3-10)class PetsController {
[](#cb3-11)
[](#cb3-12)  @QueryMapping
[](#cb3-13)  List<Pet> pets() {
[](#cb3-14)    return List.of(
[](#cb3-15)      new Pet("Luna", "cappuccino"),
[](#cb3-16)      new Pet("Skipper", "black"));
[](#cb3-17)  }
[](#cb3-18)
[](#cb3-19)}
```

And that’s all the code we need: a schema file, a record class, and a GraphQL controller! The `@QueryMapping` controller annotation registers the pets method as a DataFetcher, connecting the pets field in the schema to data, in this case an in-memory list. We’ll explain how to connect your schema and your data in much more detail in the [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1).

To add a visual frontend to explore our API, enable the built-in [GraphiQL](https://github.com/graphql/graphiql) interactive playground by adding `spring.graphql.graphiql.enabled=true` to the `application.properties` file in `src/main/resources`. GraphiQL is a small web app for exploring GraphQL APIs interactively from the browser. Think of it as a REPL (“Read-Eval-Print Loop”) tool for GraphQL.

Restart your service. You should see a log entry `GraphQL endpoint HTTP POST /graphql` if you’re successful. Then open GraphiQL by navigating to `http://localhost:8080/graphiql`.

If your service is not starting correctly, double check that your schema file `schema.graphqls` is stored in the `graphql` subfolder inside `resources`.

Let’s try our first query. Enter the following on the left-hand side of the GraphiQL playground:

```
[](#cb4-1)query myPets {
[](#cb4-2)    pets {
[](#cb4-3)        name
[](#cb4-4)        color
[](#cb4-5)    }
[](#cb4-6)}
```

Then send the query by clicking the play button, a pink button with a triangle icon, as in the screenshot “GraphiQL request and response”.

![GraphiQL request and response](media/file1.png)

GraphiQL request and response

On the left-hand side of the GraphiQL playground, we see our query and on the right we see the JSON response. The structure of the response matches the query exactly.

Take a moment to experiment with GraphiQL. For example, you could remove `color` from the query. Try the automatic completion help when typing a query.

Open the Documentation Explorer by clicking on document icon in the top left corner, as shown in the screenshot “GraphiQL Documentation Explorer”.

![GraphiQL Documentation Explorer](media/file2.png)

GraphiQL Documentation Explorer

Then click on the root Query for pets, and then click on Pet to see its attributes (name and color), as shown in the screenshot “GraphiQL Pet documentation”.

![GraphiQL Pet documentation](media/file3.png)

GraphiQL Pet documentation

Congratulations on completing your first Spring for GraphQL service! In this chapter, we discussed concepts at a very high level. In the remainder of this book, we’ll discuss each concept in greater detail. Later, in the [Building a GraphQL service chapter](#ch008.xhtml_building-a-graphql-service), we’ll extend this service with more features.

To quickly recap what we did:

*   Created a new GraphQL service with WebFlux via `https://start.spring.io`
*   Added a GraphQL schema file in SDL format
*   Implemented a GraphQL controller that returns a list of Pet data
*   Executed a GraphQL query

## What is GraphQL?

GraphQL is a technology for client-server data exchange. The typical uses cases are web or mobile clients accessing or changing data on a backend server, as shown in the diagram “Client Server”. We sometimes describe the two parties involved as the API “consumer” and “producer”.

![Client Server](media/file4.png)

Client Server

In practical terms, GraphQL comprises two different parts: a domain-specific language that enables the client to specify their intent such as what data to query, which action to perform, data attributes to be returned, and a backend service able to execute this request. The domain-specific language is called the “GraphQL query language”; although “query” unfortunately is an overloaded term, since the “query language” lets you perform updates (or “mutations”), subscriptions, and queries.

For example, a request to query a list of pets and their names:

```
[](#cb5-1)# This is a comment
[](#cb5-2)
[](#cb5-3)# We are asking for two fields:
[](#cb5-4)# "pets" and the "name" for each pet
[](#cb5-5)
[](#cb5-6)query myPets {
[](#cb5-7)    pets { 
[](#cb5-8)        name 
[](#cb5-9)    }
[](#cb5-10)} 
```

This is a “query operation”, but there are also “mutation” and “subscription” operations that can be executed by a GraphQL service. We’ll explain [operations](#ch006.xhtml_operations) in more detail in the Query Language chapter. Assuming there are two pets named Luna and Skipper, this is the JSON response:

```
[](#cb6-1){
[](#cb6-2)  "data": 
[](#cb6-3)  {
[](#cb6-4)    "pets": [
[](#cb6-5)      {
[](#cb6-6)        "name": "Luna"
[](#cb6-7)      },
[](#cb6-8)      {
[](#cb6-9)        "name": "Skipper"
[](#cb6-10)      }
[](#cb6-11)    ]
[](#cb6-12)  }
[](#cb6-13)}
```

This also shows a key feature of GraphQL: we need to explicitly ask for every piece of information we want. The response contains exactly the fields we asked for: the “name” of every pet.

If we changed the query and also ask for the color:

```
[](#cb7-1)query myPets {
[](#cb7-2)    pets { 
[](#cb7-3)        name
[](#cb7-4)        color
[](#cb7-5)    }
[](#cb7-6)} 
```

the response would look like this:

```
[](#cb8-1){
[](#cb8-2)  "pets": [
[](#cb8-3)    {
[](#cb8-4)      "name": "Luna",
[](#cb8-5)      "color": "cappuccino"
[](#cb8-6)    },
[](#cb8-7)    {
[](#cb8-8)      "name": "Skipper",
[](#cb8-9)      "color": "black"
[](#cb8-10)    }
[](#cb8-11)  ]
[](#cb8-12)}
```

Technically speaking, we normally send a GraphQL request as an HTTP POST with the operation specified in the HTTP body with the response as JSON. Every POST request is sent to the same URL (typically ending with `/graphql`), but the body of the POST request varies based on what you want to request.

The GraphQL ecosystem today offers implementations in nearly every [language](https://graphql.org/code/). The [GraphQL specification](https://graphql.org/code/) (often shortened to “spec”) maintains consistency across all implementations, which defines the exact behaviour of each GraphQL request. Beside the spec, there is a [reference implementation](https://github.com/graphql/graphql-js) written in TypeScript.

One thing to note is that the spec describes how to execute a GraphQL request should be executed with no considerations of the transport layer. A GraphQL request (in the abstract spec sense) could be an in-memory API call or could be a request via [RSocket](https://rsocket.io/), the spec describes merely a “GraphQL engine”. This is important for later to understand for how GraphQL Java and Spring for GraphQL relate to each other.

While in theory GraphQL could be executed over many transport protocols, the vast majority of GraphQL APIs use HTTP. Although the spec does not yet specify GraphQL over HTTP, the GraphQL community in practice agrees on a GraphQL request over HTTP standard. In this book, we will also only focus on GraphQL via HTTP for queries and mutations, and GraphQL via WebSocket for subscriptions.

A GraphQL API is a statically typed API. “Typed” means that a GraphQL API contains a clear description of what the consumers can do with an API. The API doesn’t change often. When the API does change, it normally involves a redeployment of the service.

For example, the API used by the queries above would look like this:

```
[](#cb9-1)# This is a comment
[](#cb9-2)
[](#cb9-3)# this is the root Object, because it is named Query
[](#cb9-4)type Query { 
[](#cb9-5)    # a field named "pets" which returns a list of Pet
[](#cb9-6)    pets: [Pet] 
[](#cb9-7)}
[](#cb9-8)
[](#cb9-9)# an Object named Pet
[](#cb9-10)type Pet { 
[](#cb9-11)    # a field with the name "name" of type String
[](#cb9-12)    name: String 
[](#cb9-13)    color: String
[](#cb9-14)}
```

This syntax is called Schema Definition Language (SDL) and the structure of a GraphQL API is called a schema. Every GraphQL API has a schema that clearly describes the API in SDL syntax. The best way to think about a GraphQL API for now is that it is a list of types with a list of fields.

Every GraphQL API offers special fields that let you query the schema of the API itself. This feature is called introspection. For example, a valid query for every GraphQL API is this:

```
[](#cb10-1)query myIntrospection {
[](#cb10-2)    __schema {
[](#cb10-3)        types {
[](#cb10-4)            name
[](#cb10-5)        }
[](#cb10-6)    }
[](#cb10-7)}
```

For our API from above, it would return:

```
[](#cb11-1){
[](#cb11-2)  "__schema": {
[](#cb11-3)    "types": [
[](#cb11-4)      {
[](#cb11-5)        "name": "Query"
[](#cb11-6)      },
[](#cb11-7)      {
[](#cb11-8)        "name": "Pet"
[](#cb11-9)      }
[](#cb11-10)    ]
[](#cb11-11)  }
[](#cb11-12)}
```

As you can see the special field `__schema` starts with `__`, which indicates this is an introspection field, not a normal field.

#### GraphQL is an API technology

We want to highlight one very important aspect of GraphQL: it is an API technology that is agnostic to the source of your data. When implementing a GraphQL service, the actual data can come from anywhere. GraphQL is not a database or persistence-specific technology. And while there are technologies and services that let us expose our database schema as GraphQL API, that is not a robust architecture when our system will grow: these are two things that we should not couple together. We highly recommend you think about a database schema as something different from a GraphQL schema.

## A brief history of GraphQL

The official birthday of GraphQL was the 29th of February 2012, when it was an internal proposal at Facebook with the name [SuperGraph](https://twitter.com/leeb/status/1498759168689598464?s=20&t=817z2q0x1_x2En8xxH5X8w).

It was part of the effort to rewrite the Facebook iOS client as a native app and aimed to solve multiple problems the team encountered with traditional REST like APIs described by co-creator Lee Byron in this 10-minute video keynote of a [Brief History of GraphQL](https://www.youtube.com/watch?v=VjHWkBr3tjI):

*   Slow on the network: multiple coordinated round-trips were required to fetch the needed data.
*   Fragile client/server relationship: changes to the server API could easily break the app and docs were often out of date.
*   Tedious code and process: necessary service changes often blocked client development.

GraphQL addressed these issues with the features outlined in the previous section: a query language allows the client to specify exactly what they want, develop flexibly and independently of the server, and a static type system that makes the client/server relationship much more stable.

After GraphQL was successfully used inside Facebook for a few years, it was [open sourced in July 2015](https://youtu.be/WQLzZf34FJ8?t=1473). Two artifacts were published together: the GraphQL spec and the reference implementation. The reference implementation was initially a JavaScript implementation of the spec, but it’s now also available in TypeScript. This dual approach of having a clear spec together with a reference implementation led to implementations across every major programming language and ecosystem, including Ruby, PHP, .NET, Python, Go, and of course Java.

After the open source release in 2015, GraphQL was owned and run by Facebook until the end of 2018 with the creation of the [GraphQL Foundation](https://medium.com/@leeb/introducing-the-graphql-foundation-3235d8186d6d). The GraphQL Foundation is a vendor-neutral entity, comprising over [25 members](https://graphql.org/foundation/members/). The list includes AWS, Airbnb, Atlassian, Microsoft, IBM, and Shopify. The official description of the [foundation](https://graphql.org/foundation/) is:

> The GraphQL Foundation is a neutral foundation founded by global technology and application development companies. The GraphQL Foundation encourages contributions, stewardship, and a shared investment from a broad group in vendor-neutral events, documentation, tools, and support for GraphQL.

Legally, the GraphQL Foundation owns the GraphQL trademark and the copyright for certain GraphQL projects.

The official web page of GraphQL is https://graphql.org. Note that the domain ending in .com (https://graphql.com) is an unrelated page owned by a company.

Practically speaking, the Foundation is ultimately responsible for the official GraphQL projects under the [GraphQL GitHub organization](https://github.com/graphql). It includes the spec, the reference implementation, and GraphiQL. Most of the GraphQL implementations are not part of the GraphQL Foundation, even though they implement the spec.

The most important group for developing the GraphQL spec is the GraphQL Working Group (often shortened to WG). It is an open group that meets online three times a month and mainly discusses GraphQL spec changes and improvements. Everybody from the GraphQL community can join. More details are available in the working group [GitHub repository](https://github.com/graphql/graphql-wg).

## From GraphQL Java to Spring for GraphQL

Shortly after GraphQL was open sourced, a first version of [GraphQL Java](https://github.com/graphql-java/graphql-java/releases/tag/v1.0) was released. One of the fundamental design decisions that I (Andi) made was to focus purely on the execution part of GraphQL. GraphQL Java always aimed to be a spec-compliant GraphQL engine, not a fully-fledged framework for GraphQL services. This meant that GraphQL Java should never deal with HTTP I/O or any kind of threading, to the extent that is possible.

While I am still quite happy with this decision, because it allowed GraphQL Java to have a strong focus and widespread adoption, it came with one clear downside: every service would need to solve the HTTP integration itself.

So some time after I released GraphQL Java, the first GraphQL Java Spring integrations became available. I even developed a small [GraphQL Java Spring](https://github.com/graphql-java/graphql-java-spring) library, which aimed to be as lightweight as possible. But nothing beats an official Spring integration maintained by the Spring team that allows for the most GraphQL adoption and best experience overall.

In July 2020, the Spring and GraphQL Java teams came together to develop an official Spring for GraphQL integration. One year later, we published a [first milestone](https://spring.io/blog/2021/07/06/hello-spring-graphql) and after that, the first release of [Spring for GraphQL](https://spring.io/projects/spring-graphql) in May 2022.

Spring for GraphQL aims to be an unopinionated integration of GraphQL Java into Spring with a focus on comprehensive and wide-ranging support. It should serve as a fundamental building block for GraphQL solutions with Spring. Another key design decision was the direct usage of GraphQL Java itself, there is no abstraction or additional layer between Spring and GraphQL Java.

Spring for GraphQL comprises two parts: one is the actual [Spring Framework integration](https://docs.spring.io/spring-graphql/docs/current/reference/html/) with GraphQL Java, and on top of that there is the [Spring Boot Starter](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#web.graphql) for GraphQL. In this book, we will build services developed with Spring Boot that take advantage of the Spring Boot GraphQL Starter.

We will constantly move between the GraphQL Java and Spring world, but it is often important to understand which layer contributes what part in order to take full advantage of Spring for GraphQL. This is especially valuable for troubleshooting. Throughout this book, we’ll make it clear when we talk about a Spring for GraphQL concept and when we are directly discussing a GraphQL Java concept.

In the next few chapters, we will explain the concepts used in this initial service in greater detail, and also discuss core GraphQL concepts. After that, we will build a more substantial application to review what we have learned. Later in the book, we’ll cover more advanced topics.

# Overview

In this chapter, we cover the fundamentals aspects of Spring for GraphQL and GraphQL Java, and how they relate to each other. This is important to build an overall understanding and not get lost in the details in the next chapters.

This chapter will cover concepts at a high level to provide an overview. Later in the book, we’ll explain these concepts in greater detail.

## Three layers

We have three layers to consider, where the higher ones depend on the lower ones.

![Three layers](media/file5.png)

Three layers

From bottom to top in the diagram “Three layers”:

*   GraphQL Specification (Spec): defines in a technology-independent way what GraphQL is and what a GraphQL service needs to implement.
*   GraphQL Java: implements the GraphQL spec for Java.
*   Spring for GraphQL: integrates GraphQL Java with Spring.

We can also look at this as a hierarchy of abstractions, from less opinionated at the bottom to more specific at the top:

*   The spec is the most abstract as it is relevant for all implementations of GraphQL, not only for Java. It is only a text document, not running software. For example, it describes what a GraphQL mutation is, without describing the details of its implementation.
*   GraphQL Java implements the spec and actually provides running software. It is not tied to any specific framework like Spring and doesn’t deal with any transport level details.
*   Spring for GraphQL: leverages GraphQL Java to provide a comprehensive framework for building GraphQL services, including transport level details.

We can consider GraphQL Java and the spec as the same from a practical Java point of view. GraphQL Java doesn’t offer major features beyond the spec and the spec doesn’t define anything that is not represented in Java, it is a one-to-one relationship. Therefore, we will not discuss the spec separately from GraphQL Java, and we can assume features in GraphQL Java by default to be defined in the spec.

## Schema and SDL

A GraphQL API uses static types, so it can only do what it clearly describes. Changing the API usually involves a redeployment of our service.

The schema is the description of the API, which is an instance of `GraphQLSchema` in GraphQL Java.

The Schema Definition Language (SDL) syntax defines the schema in a human-readable format.

```
[](#cb12-1)type Query {
[](#cb12-2)    pets: [Pet]
[](#cb12-3)}
[](#cb12-4)
[](#cb12-5)type Pet {
[](#cb12-6)    name: String
[](#cb12-7)    color: String
[](#cb12-8)}
```

This is a schema in SDL format defining two types: `Query` and `Pet`. The `Query` type has a `pets` field. The `Pet` type has two fields, `name` and `color`.

The SDL format is great for defining a schema, and makes the schema easily readable. During execution, GraphQL Java uses an instance of `GraphQLSchema`, which represents the provided SDL schema.

We will discuss GraphQL schemas in depth in the [Schema chapter](#ch005.xhtml_schema-chapter).

## GraphQL query language

The GraphQL query language is a domain-specific language for describing what a client wants to request. It looks similar to JSON on purpose, but it is not JSON.

```
[](#cb13-1)query myPets { 
[](#cb13-2)    pets { 
[](#cb13-3)        name 
[](#cb13-4)    } 
[](#cb13-5)} 
```

The client is required to explicitly “select” any data it wants, such as the names of pets. The response is in JSON, and only contains the data requested, no more and no less.

```
[](#cb14-1){
[](#cb14-2)  "data":{ 
[](#cb14-3)    "pets": [
[](#cb14-4)      {
[](#cb14-5)        "name": "Luna"
[](#cb14-6)      },
[](#cb14-7)      {
[](#cb14-8)        "name": "Skipper"
[](#cb14-9)      }
[](#cb14-10)    ]
[](#cb14-11)  }
[](#cb14-12)}
```

A response can also contain another two top level keys, “errors” and “extensions”. We’ll discuss this in more detail in the [Request and Response chapter](#ch010.xhtml_request-and-response-chapter).

## Request and Response

Every interaction of a consumer of a GraphQL API starts with a GraphQL request, and results in a GraphQL response.

A GraphQL request in GraphQL Java is an instance of `ExecutionInput` and the response is an `ExecutionResult`. These are request and response definitions independent of a specific transport level. From a GraphQL Java perspective, a request and a response are just an argument and return value of a method call. We’ll discuss [GraphQL requests and responses](#ch010.xhtml_request-and-response-chapter) in more detail in a dedicated chapter later in the book.

Spring for GraphQL defines a `GraphQlRequest` with the most important implementation being `WebGraphQlRequest` for requests via HTTP or WebSocket. `WebGraphQlRequest` contains specific data for the HTTP request, such as URL and HTTP headers.

A response in Spring for GraphQL is a `GraphQlResponse` with `WebGraphQlResponse` again being specific to HTTP or WebSocket, containing the HTTP response headers.

Most notably, a GraphQL request contains a GraphQL document, which is text in GraphQL query language format that contains the intent of the client.

The response can contain data, errors, and extensions. Data can be anything. In `ExecutionResult`, data is `Map<String, Object>`. On the transport layer, we send the response over HTTP in JSON.

## Execution and DataFetcher

We can roughly divide the actual execution of a GraphQL request via HTTP like this:

1.  First, the request is deserialized and processed (Spring).
2.  We invoke GraphQL Java, which involves fetching data (GraphQL Java).
3.  Then we create and serialize the response (Spring).

The first step is purely Spring and can also involve aspects like authentication. Then Spring invokes GraphQL Java and once finished, the response is again handled by Spring and sent back to the client.

Step two involves multiple steps, such as invoking the relevant DataFetchers that retrieve the data necessary to fulfill the request. We’ll go into much more detail on DataFetchers in a [dedicated chapter](#ch007.xhtml_datafetchers-part-1) later in this book.

In Spring for GraphQL, annotated controller methods are registered as DataFetchers. For example, in the previous chapter we built a sample service with a list of pets:

```
[](#cb15-1)package myservice.service;
[](#cb15-2)
[](#cb15-3)import org.springframework.graphql.data.method.annotation
[](#cb15-4)  .QueryMapping;
[](#cb15-5)import org.springframework.stereotype.Controller;
[](#cb15-6)
[](#cb15-7)import java.util.List;
[](#cb15-8)
[](#cb15-9)@Controller
[](#cb15-10)class PetsController {
[](#cb15-11)
[](#cb15-12)  @QueryMapping
[](#cb15-13)  List<Pet> pets() {
[](#cb15-14)    return List.of(
[](#cb15-15)      new Pet("Luna", "cappuccino"),
[](#cb15-16)      new Pet("Skipper", "black"));
[](#cb15-17)  }
[](#cb15-18)
[](#cb15-19)}
```

The `@QueryMapping` annotation registers this method as a DataFetcher for a field `pets` in the type `Query`, connecting the method to the field of the same name. We’ll explain Spring for GraphQL’s schema mapping annotations in detail in the [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1).

The last step of creating and serializing the response is handled by Spring for GraphQL.

For more on [execution](#ch015.xhtml_execution-chapter), see the dedicated chapter later in this book.

## How concepts relate to each other

![Concept relations](media/file6.png)

Concept relations

As shown in the diagram “Concept relations”,

*   The SDL defines the schema
*   A request contains text in query language format
*   The execution of a request uses the schema and DataFetchers to produce a response

## GraphQL Java

The primary classes of GraphQL Java are, as shown in the diagram “GraphQL Java classes”:

**`graphql.GraphQL`:** Normally only one instance per service. Used to start GraphQL Java execution.

**`graphql.ExecutionInput`:** A GraphQL Java request.

**`graphql.ExecutionResult`:** A GraphQL Java response.

**`graphql.schema.GraphQLSchema`:** Description of the GraphQL API plus the logic needed to execute it.

**`graphql.schema.DataFetcher`:** Java interface to be implemented by every service. Your GraphQL service will implement DataFetchers via Spring for GraphQL’s schema mapping annotations.

![GraphQL Java classes](media/file7.png)

GraphQL Java classes

## Spring for GraphQL

The primary classes of Spring for GraphQL are (all class name start with `org.springframework.graphql`, abbreviated as `o.s.g`):

**`o.s.g.server.webflux.GraphQlHttpHandler`:** WebFlux handler. Creates `WebGraphQlRequest` and calls a `WebGraphQlHandler`

**`o.s.g.server.webmvc.GraphQlHttpHandler`:** Spring MVC handler. Creates `WebGraphQlRequest` and calls a `WebGraphQlHandler`

**`o.s.g.server.WebGraphQlRequest`:** A GraphQL request over HTTP or WebSocket.

**`o.s.g.server.WebGraphQlResponse`:** A GraphQL response over HTTP or WebSocket.

**`o.s.g.server.WebGraphQlHandler`:** Handles GraphQL requests over HTTP or WebSocket.

**`o.s.g.server.WebGraphQlInterceptor`:** Hook to intercept a `WebGraphQlRequest` and `WebGraphQlResponse`.

**`o.s.g.graphql.ExecutionGraphQlService`:** The actual service responsible for invoking GraphQL Java.

A request passes through three primary classes in Spring for GraphQL, each with a distinct responsibility, as shown in the diagram “Spring for GraphQL classes”:

1.  A general purpose HTTP request invokes `GraphQlHttpHandler` converts the request into a `WebGraphQlRequest`.
2.  `WebGraphQlHandler` takes the `WebGraphQlRequest`, and calls `ExecutionGraphQlService` to execute the request.
3.  `ExecutionGraphQlService` ultimately invokes GraphQL Java.

![Spring for GraphQL classes](media/file8.png)

Spring for GraphQL classes

The most relevant of these steps in daily usage is the second one as the `WebGraphQlHandler` offers the ability to intercept any request and response via `WebGraphQlInterceptor`.

A quick note on capitalization. You might have noticed the capitalization of the letters “Q” and “L” in class names vary. In all Spring for GraphQL classes, “Q” is always in upper case and “l” is always in lower case, to be consistent with Spring naming conventions. In GraphQL Java, names usually include “Q” and “L” in upper case. Where this convention has not been followed, we’ll call it out in the relevant code example.

This chapter summarized the most fundamental concepts at a high level. Throughout this book, we’ll expand on all these topics is greater detail.

# Schema

The schema of a GraphQL API is the static description of the API. A schema describes what a consumer of the API may request, which can be represented in Schema Definition Language (SDL) format (also called “SDL syntax” or “SDL notation”).

Under the hood, Spring for GraphQL represents an executable schema with GraphQL Java’s `GraphQLSchema`, which is then used to create a `GraphQL` object. It is an “executable” schema because it contains all the logic needed to execute a request, as well as the description of the API for the consumer. In this chapter, we will focus on the API description. In the [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1), we will discuss how this API description connects to the execution logic.

## Schema-first

“Schema-first” refers to the idea that the design of a GraphQL schema should be done on its own, and should not be generated or inferred from something else. The schema should not be generated from a database schema, Java domain classes, nor a REST API.

Schemas ought to be schema-first because they should be created in a deliberate way and not merely generated. Although a GraphQL API will have much in common with the database schema or REST API being used to fetch data, the schema should still be deliberately constructed.

We strongly believe that this is the only viable approach for any real-life GraphQL API and we will only focus on this approach. Both Spring for GraphQL and GraphQL Java only support “schema-first”.

In GraphQL Java, the schema is represented by an instance of `GraphQLSchema`. This can be created either via SDL or programmatically. Both approaches are “schema-first” because the schema is deliberately designed. In this book, all examples will use schemas created via SDL.

## Loading schema resources in Spring for GraphQL

Spring for GraphQL automatically loads schema files with extensions `.graphqls` or `.gqls` in the directory `src/main/resources/graphql`. All you need to do is save the schema file in the correct location. You can alternatively load schema files from a different location, see details in the [documentation](https://docs.spring.io/spring-graphql/docs/current/reference/html/#execution-graphqlsource-schema-resources).

Under the hood, Spring for GraphQL automatically reads the schema files, parses the files, and instantiates GraphQL Java’s `GraphQLSchema` object with the schema.

## GraphQL schema elements

A schema in GraphQL Java is represented as a `GraphQLSchema` instance, which is a graph of `GraphQLSchemaElement`s. We will describe the most important elements of a `GraphQLSchema` and the notation in SDL format.

## GraphQL types

The most important schema elements are the types. There are eight types in the GraphQL type system: Object, Interface, Union, Enum, Scalar, InputObject, List, and NonNull. The first six are “named types”, because each type has a unique name across the whole schema, while List and NonNull are called “wrapping types”, because they wrap named types, as we will see later.

Another classification of types differentiates between input and output types. An output type is a type that describes the result of a request, while input types are used to describe input data for a GraphQL request. We will cover requests in greater detail in the next chapter on GraphQL query language.

![Input and Output types](media/file9.png)

Input and Output types

## Fields everywhere

The most prominent elements of a schema are fields. Objects and interfaces contain fields which can have arguments. An input object has input fields, which cannot have arguments. If we squint, we can think of a schema as a list of types with a list of fields.

In GraphQL Java, a field is represented by an instance of `GraphQLFieldDefinition` for object and interface fields, or `GraphQLInputObjectField` for input objects.

## Scalar

A scalar is a primitive type describing a certain set of allowed values. For example, a `Boolean` scalar means the value can be `true` or `false`, an `Int` can be any number between -2^31 and 2^31, and a `String` can be any String literal. A scalar name must be unique across the schema.

GraphQL comes with five built-in scalars: `String`, `Int`, `Float`, `Boolean`, and `ID`. In addition, every GraphQL service can define its own custom scalars.

In SDL, custom scalars need to be declared explicitly, while built-in scalars can be used without any declaration.

```
[](#cb16-1)"""
[](#cb16-2)A custom scalar representing a date without any time zone.
[](#cb16-3)Note how this custom scalar must be declared explicitly.
[](#cb16-4)"""
[](#cb16-5)scalar Date @specifiedBy(url:
[](#cb16-6)  "https://scalars.graphql.org/andimarek/local-date")
[](#cb16-7)
[](#cb16-8)type Pet {
[](#cb16-9)    "String is a built-in scalar, therefore no declaration is required."
[](#cb16-10)    name: String
[](#cb16-11)    dateOfBirth: Date
[](#cb16-12)}
```

The built-in `@specifiedBy` directive links to a custom scalar specification URL. We’ll discuss this in more detail in the [Directives chapter](#ch014.xhtml_specifiedby). The `@specifiedBy` directive is optional, but is highly recommended.

## Enum

An enum type describes a list of possible values. It can be used as an input or output type. Enums and scalars are the primitive types of the GraphQL type system. An enum name must be unique across the schema.

Here is how to declare an enum in SDL:

```
[](#cb17-1)enum PetKind {
[](#cb17-2)    CAT, DOG, BIRD
[](#cb17-3)}
[](#cb17-4)
[](#cb17-5)type Pet {
[](#cb17-6)    name: String
[](#cb17-7)    kind: PetKind # used as output type
[](#cb17-8)}
[](#cb17-9)
[](#cb17-10)type Query {
[](#cb17-11)    pets(kind: PetKind!): [Pet] # used as input type
[](#cb17-12)}
```

Alternatively, enums can also be declared with each value on its own line. This is because a comma `,` is considered whitespace and is ignored.

```
[](#cb18-1)enum PetKind {
[](#cb18-2)    CAT
[](#cb18-3)    DOG
[](#cb18-4)    BIRD
[](#cb18-5)}
```

In GraphQL Java, an enum is represented by an instance of `GraphQLEnumType`.

## Object

A GraphQL object type describes a certain shape of data as a list of fields. It has a unique name across the schema. Each field has a specific type, which must be an output type. Every field has an optional list of arguments. Recursive references are allowed.

An object type is declared in SDL as `type`.

```
[](#cb19-1)type Pet {
[](#cb19-2)    name: String
[](#cb19-3)    color: String
[](#cb19-4)    friend: Pet # recursive reference
[](#cb19-5)    owners: [Person!] # A list of people
[](#cb19-6)}
[](#cb19-7)
[](#cb19-8)type Person {
[](#cb19-9)    name: String
[](#cb19-10)}
[](#cb19-11)
[](#cb19-12)type Query {
[](#cb19-13)    pet(name: String!): Pet # lookup a pet via name
[](#cb19-14)}
```

In GraphQL Java, an object type is represented by an instance of `GraphQLObjectType` with `GraphQLFieldDefinition` defining its fields.

## Input object

An input object type describes a group of input fields where each has an input type. An input object name must be unique across the schema.

In SDL, an input object is declared via `input`.

```
[](#cb20-1)input PetFilter {
[](#cb20-2)    minAge: Int
[](#cb20-3)    maxAge: Int
[](#cb20-4)}
[](#cb20-5)
[](#cb20-6)type Pet {
[](#cb20-7)    name: String
[](#cb20-8)    age: Int
[](#cb20-9)}
[](#cb20-10)
[](#cb20-11)type Query {
[](#cb20-12)    pets(filter: PetFilter): [Pets]
[](#cb20-13)}
```

## Interface

Similar to an object, an interface describes a certain shape of data as a list of fields and has a name. In contrast to an object, an interface can be implemented by another interface or object. An interface or object implementing an interface must contain at least the same fields defined in the interface. In that sense, an interface is used to describe an abstract shape, which can be realized by different objects.

Similar to objects, every field has an optional list of arguments. Every argument has a name and type, which must be an input type.

An interface in SDL is declared as `interface`. Implementations by other interfaces or objects specify `implements` followed by the interface name. In the example below, both Dog and Cat types implements the Pet interface. Both Dog and Cat types contain at least fields for name and owners, which are declared in the Pet interface.

```
[](#cb21-1)interface Pet {
[](#cb21-2)    name: String
[](#cb21-3)    owners(includePreviousOwners: Boolean): [Person!]
[](#cb21-4)}
[](#cb21-5)
[](#cb21-6)# One implementation of the interface
[](#cb21-7)type Dog implements Pet {
[](#cb21-8)    name: String
[](#cb21-9)    owners(includePreviousOwners: Boolean): [Person!]
[](#cb21-10)    doesBark: Boolean # additional field specific to Dog
[](#cb21-11)}
[](#cb21-12)
[](#cb21-13)# Another implementation
[](#cb21-14)type Cat implements Pet {
[](#cb21-15)    name: String
[](#cb21-16)    owners(includePreviousOwners: Boolean): [Person!]
[](#cb21-17)    doesMeow: Boolean # additional field specific to Cat
[](#cb21-18)}
```

It might surprise you that all interface fields must be repeated. As we can see in this example, `Cat` and `Dog` both repeat the same `name` field from `Pet`. This was a deliberate decision by the GraphQL working group to focus more on readability than shorter notation.

In GraphQL Java, an interface is represented as an instance of `GraphQLInterfaceType`, and fields by instances of `GraphQLFieldDefinition`.

## Union

A union type must be one of the member types at execution time. In other words, a union is fully described by the list of possible object types it can be at execution time.

In SDL, a union is declared as a list of object types separated by a vertical bar `|`.

```
[](#cb22-1)union Pet = Dog | Cat
[](#cb22-2)
[](#cb22-3)type Dog {
[](#cb22-4)    name: String
[](#cb22-5)    doesBark: Boolean
[](#cb22-6)}
[](#cb22-7)
[](#cb22-8)type Cat {
[](#cb22-9)    name: String
[](#cb22-10)    doesMeow: Boolean
[](#cb22-11)}
```

In GraphQL Java, a union is represented as an instance of `GraphQLUnionType`.

## List and NonNull

Wrapping types contain another type, which can be another wrapping type or named type. Ultimately, a wrapping type wraps a named type.

A list type is a list of the wrapped type. A non-null type marks this type as never being `null`.

A wrapping type can be used as a type for a field argument, as a field or input field type.

In SDL notation, a non-null type is declared by appending an exclamation mark `!` to the type. A list is declared by surrounding the type with brackets `[` `]`.

```
[](#cb23-1)type Query {
[](#cb23-2)    pet(id: ID!): Pet
[](#cb23-3)}
[](#cb23-4)
[](#cb23-5)type Pet {
[](#cb23-6)    id: ID!
[](#cb23-7)    ownerNames: [String!] # A combination: a list of non-null strings
[](#cb23-8)}
```

GraphQL Java ensures that any field or input field marked as non-null is never `null`. In GraphQL Java, list types are represented by instances of `GraphQLList` and non-null types by instances of `GraphQLNonNull`.

## Directives

A directive is a schema element that allows us to define metadata for a schema or a GraphQL operation. A directive needs to declare all possible locations where it can be used. A directive contains an optional list of arguments, similarly to fields.

An instance of a directive is called an applied directive. We’ll discuss applied directives in more detail in the [Directives chapter](#ch014.xhtml_directives-chapter).

To declare a directive in SDL:

```
[](#cb24-1)# This is a directive without any argument
[](#cb24-2)# and it can only used in two locations inside the schema
[](#cb24-3)directive @example on FIELD_DEFINITION | ARGUMENT_DEFINITION
[](#cb24-4)
[](#cb24-5)# Example usage
[](#cb24-6)type SomeType {
[](#cb24-7)    field(arg: Int @example): String @example
[](#cb24-8)}
```

In GraphQL Java, a directive declared in the schema is represented as `GraphQLDirective`.

There’s much more to directives. We will dive into greater detail in the [Directives chapter](#ch014.xhtml_directives-chapter).

## Arguments

Directives, object type fields, and interface fields can have an optional list of arguments.

Every argument has a name and type, which must be an input type. In the following example, the `pet` field has one defined argument called `name` which is of type `String!`.

```
[](#cb25-1)type Query {
[](#cb25-2)    pet(name: String!): Pet # lookup a pet via name
[](#cb25-3)}
[](#cb25-4)
[](#cb25-5)type Pet {
[](#cb25-6)    name: String
[](#cb25-7)    color: String
[](#cb25-8)}
```

A default value can be optionally defined with the equals sign `=`. In the following example, you can fetch a specific number of pets. Alternatively, if the number of pets is not specified, it will default to 20.

```
[](#cb26-1)type Query {
[](#cb26-2)  pets(howMany: Int = 20): [Pet]
[](#cb26-3)}
```

Arguments can be optional or required. An argument is required if the argument type is non-null and does not have a default value. Otherwise, the argument is optional. For example, the argument `name: String!` is required.

## Documentation with descriptions

Documentation is a powerful feature of GraphQL. Descriptions of GraphQL definitions such as fields and types are embedded in the schema, alongside their definitions. These descriptions are made available via introspection, and can be used to generate interactive documentation.

Nearly every SDL element can have a description in [Markdown](https://commonmark.org/) format as documentation. The description is either a string literal enclosed in quotation marks `"`, or a block string wrapped in triple-quotes `"""` for multi-line documentation with line breaks or additional Markdown.

```
[](#cb27-1)type Query {
[](#cb27-2)    "all currently known pets"
[](#cb27-3)    pets: [Pet]
[](#cb27-4)}
[](#cb27-5)
[](#cb27-6)"""
[](#cb27-7)A Pet can be a Dog or or Cat.
[](#cb27-8)A Pet has a human owner.
[](#cb27-9)"""
[](#cb27-10)type Pet {
[](#cb27-11)    name: String
[](#cb27-12)    owner: Person
[](#cb27-13)}
```

These descriptions are collated into documentation, for example in the [GraphiQL playground](https://github.com/graphql/graphiql) in the screenshot “Documentation in GraphiQL”.

![Documentation in GraphiQL](media/file10.png)

Documentation in GraphiQL

To access documentation in GraphiQL, click on the book icon in the top left corner. See the Introduction chapter for how to add GraphiQL to your Spring for GraphQL application.

The [GraphQL specification](https://spec.graphql.org/draft/#sec-Descriptions) recommends that the schema and all other definitions (including types, fields, and arguments) should provide a description unless they are considered self-descriptive.

## Comments

Comments start with a hash sign `#` and everything on the same line is considered a part of a comment. For example:

```
[](#cb28-1)type Query {
[](#cb28-2)    # This is a comment
[](#cb28-3)    hello: String
[](#cb28-4)}
[](#cb28-5)
[](#cb28-6)# Multi line comment
[](#cb28-7)# requires
[](#cb28-8)# multiple hash signs
```

Note that comments are very different to descriptions. Descriptions are used to construct documentation for the schema, which is made available via introspection. Comments are ignored like whitespace, and are not used in documentation.

In this chapter, we discussed the schema elements that describe the structure of an API. In the [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1), we’ll discuss how this API description connects to the logic to execute requests. Before we get to DataFetchers, let’s discuss the GraphQL query language.

# GraphQL query language

The GraphQL query language is the domain-specific language (DSL) that enables consumers define what they would like to do.

Note that the phrase “query language” encapsulates queries, mutations, and subscriptions, as we’ll discuss in this chapter.

The query language syntax is deeply related to the GraphQL schema. A GraphQL schema defines which queries, mutations, or subscriptions are valid in query language. In the query language examples below, assume there is a corresponding GraphQL schema that makes the query language valid.

## Literals

The query language contains several literals that mirror the schema input types.

*   `String` literals written as `"String literal"`, enclosed with double quotation marks
*   `Boolean` literals which are `true` or `false`
*   `Int` literals written as `123`
*   `Float` literals written as `123.45`
*   A literal with no value (Null) written as `null`
*   List literals written as `["one list element", "another list element"]`, wrapped with square brackets
*   Enum values written as `ENUM_VALUE`
*   Input object literals written as `{ someField: "value", anotherOne: { fieldInField: 123 } }`. They represent an unordered list of key input, wrapped in curly braces

## Operations

There are three operations in GraphQL:

*   query, a read-only fetch
*   mutation, a write followed by a fetch
*   subscription, a long-lived request that fetches data in response to events

In a GraphQL schema, these operations are modelled as root operation types.

In GraphQL query language, these operations also form the root of the query.

## Query operations

A query operation requests data and returns a response containing the result.

A simple query called `myQuery`, fetching a single field `someField`, is written like this:

```
[](#cb29-1)query myQuery {
[](#cb29-2)    someField
[](#cb29-3)}
```

A query operation is a tree of *selected fields*. The fields on the first level of the query are called *root fields*. The fields below another field are a *sub-selection*. Every selected field in query operation must match their respective schema definitions.

In this example operation, `pet` is a root field, and `name` is a sub-selection.

```
[](#cb30-1)query petName {
[](#cb30-2)    pet {
[](#cb30-3)        name
[](#cb30-4)    }
[](#cb30-5)}
```

Selected fields in this `petName` query correspond to their respective schema definitions:

```
[](#cb31-1)type Query {
[](#cb31-2)    pet: Pet
[](#cb31-3)}
[](#cb31-4)
[](#cb31-5)type Pet {
[](#cb31-6)    name: String
[](#cb31-7)}
```

A key feature of GraphQL is that only selected fields are returned, no more and no less. To enable this feature, fields of object, interface, and union types require a sub-selection. Every field must be explicitly selected, there are no wildcard selections. Requiring sub-selections was a deliberate decision in the GraphQL spec to ensure queries are predictable and therefore clients always receive exactly what they ask for.

As a more complex example, a query can request the country of the address of the owner of a pet.

```
[](#cb32-1)query petOwnerDetails {
[](#cb32-2)    pet {
[](#cb32-3)        name
[](#cb32-4)        owner {
[](#cb32-5)            name
[](#cb32-6)            address {
[](#cb32-7)                country
[](#cb32-8)            }
[](#cb32-9)        }
[](#cb32-10)    }
[](#cb32-11)}
```

Queries are always validated against the schema of the API. We cannot query fields that are not defined in the schema.

For this schema:

```
[](#cb33-1)type Query {
[](#cb33-2)    pet: Pet
[](#cb33-3)}
[](#cb33-4)
[](#cb33-5)type Pet {
[](#cb33-6)    name: String
[](#cb33-7)}
```

We will not be able to execute the following invalid query. An error will be raised because there is no `nickName` field on the `Pet` type.

```
[](#cb34-1)query invalid {
[](#cb34-2)    pet {
[](#cb34-3)        name
[](#cb34-4)        nickName
[](#cb34-5)    }
[](#cb34-6)}
```

Although there is a difference between a “field definition” in schema and a “field” used in query language, we often use the word field for both if the context is clear.

## Mutation operations

A mutation operation is a write followed by a fetch. Mutations should have a side effect, which usually means changing (or “mutating”) some data.

Declare a mutation operation with the keyword `mutation` followed by the name of the mutation:

```
[](#cb35-1)mutation myMutation {
[](#cb35-2)    changeSomething
[](#cb35-3)}
```

Every root field of a mutation operation must be a field of the `Mutation` object type in the schema. Only the root fields of a mutation can have side effects, as required by the GraphQL spec.

Sub-selections of the root field of a mutation operation are semantically equal to queries. In practice, it’s useful for a mutation to return some of the changed data. For example, after updating the name of a `User`, it’s useful to receive the newly changed `User` in the response.

For example, in the schema, the `changeUser` field is defined in the `Mutation` type:

```
[](#cb36-1)type Mutation {
[](#cb36-2)    changeUser(newName: String!): User
[](#cb36-3)}
[](#cb36-4)
[](#cb36-5)type User {
[](#cb36-6)    name: String
[](#cb36-7)    address: Address
[](#cb36-8)}
[](#cb36-9)
[](#cb36-10)type Address {
[](#cb36-11)    street: String
[](#cb36-12)    country: String
[](#cb36-13)}
```

After changing the user’s name to “Brad”, we can query the details of the changed user as a normal query. Notice how the sub-selection looks exactly like a query sub-selection.

```
[](#cb37-1)mutation changeUserName {
[](#cb37-2)    changeUser(newName: "Brad") {
[](#cb37-3)        name
[](#cb37-4)        address {
[](#cb37-5)            street
[](#cb37-6)            country
[](#cb37-7)        }
[](#cb37-8)    }
[](#cb37-9)}
```

If there are two or more root fields in the mutation operation, they will be executed in sequence, as required by the GraphQL spec.

```
[](#cb38-1)mutation mutationWithTwoRootFields {
[](#cb38-2)    first: changeName(name: "Bradley")
[](#cb38-3)    second: changeName(name: "Brad")
[](#cb38-4)}
```

In this example, the final name of the user will always be “Brad”, because the fields are always executed in sequence. The second name change to “Brad” will always be executed last.

## Subscription operations

A subscription is a long-lived request that sends updates to the client when new events happen.

For example, if the client wants to be informed about every new email matching certain criteria:

```
[](#cb39-1)subscription newMessage {
[](#cb39-2)    newEmail(criteria: {
[](#cb39-3)        sender: "luna@example.com",
[](#cb39-4)        contains: "playing" }
[](#cb39-5)    ) {
[](#cb39-6)        text
[](#cb39-7)    }
[](#cb39-8)}
```

A subscription can only contain exactly one root field, like `newEmail`. This is in contrast to query and mutation operations, which can contain many root fields.

The execution of a subscription and the handling of the request on the transport layer differs significantly from queries and mutations. This is simply because a long-lived subscription request reacting to certain events is more complicated than a simple process of query (or mutation) request, execution, and response. We’ll discuss this further in the [Subscriptions chapter](#ch009.xhtml_subscriptions-chapter).

## Arguments

Fields can have arguments, which have their type defined in the schema. Arguments can be either optional or required. As discussed in the [Schema chapter](#ch005.xhtml_arguments), an argument is required if it is non-null (indicated with `!`) and there is no default value (declared with `=`).

For example, a schema defining a `pet` field with a required `id` argument:

```
[](#cb40-1)type Query {
[](#cb40-2)    pet(id: ID!): Pet
[](#cb40-3)}
[](#cb40-4)
[](#cb40-5)type Pet {
[](#cb40-6)    name: String
[](#cb40-7)}
```

In a query, this is how to request a `pet` with the string literal “123” as its `id` value.

```
[](#cb41-1)query petSearch {
[](#cb41-2)    pet(id: "123") {
[](#cb41-3)        name
[](#cb41-4)    }
[](#cb41-5)}
```

Arguments can be any literal, including `null`, as long as it conforms to the schema. For example, here’s a query with an input object literal.

```
[](#cb42-1)query petAgeSearch {
[](#cb42-2)    pets(filter: { minAge: 10, maxAge: 20 }) {
[](#cb42-3)        name
[](#cb42-4)    }
[](#cb42-5)}
```

Argument types in operations must correspond to their respective schema definitions. If the schema requires an `Int` argument value, and we provide a `Boolean` in a query, the incorrect argument will cause a validation error.

## Fragments

Fragments allow us to reuse parts of the query. Fragments are a list of selected fields (including sub-selections) for a certain type. Fragments have a name and type condition, which must be an object, interface, or union.

Fragments are declared outside of operations. The fragment definition syntax is:

```
[](#cb43-1)fragment <FragmentName> on <TypeCondition> {
[](#cb43-2)    <fields>
[](#cb43-3)}
```

Use fragments inside operations with the fragment spread syntax:

```
[](#cb44-1)... <FragmentName>
```

For example, let’s define a `personDetails` fragment, to reuse common repeated fields of `Person`. Let’s use the fragment in the `petOwners` query.

```
[](#cb45-1)fragment personDetails on Person {
[](#cb45-2)    firstName
[](#cb45-3)    lastName
[](#cb45-4)    title
[](#cb45-5)}
[](#cb45-6)
[](#cb45-7)query petOwners {
[](#cb45-8)    pets {
[](#cb45-9)        owner {
[](#cb45-10)            ...personDetails
[](#cb45-11)        }
[](#cb45-12)        previousOwner {
[](#cb45-13)            ...personDetails
[](#cb45-14)        }
[](#cb45-15)    }
[](#cb45-16)}
```

In this example, we use `personDetails` twice, for both the `owner` and `previousOwner` fields.

## Inline fragments

Inline fragments are a selection of fields with a type condition. Inline fragments are used to query different fields depending on the type. You can think of them as switch statements, that depend on the type of the previous field.

Inline fragments are different to fragments, as they are declared *inline* rather than outside an operation. Unlike fragments, inline fragments have no name, and cannot be reused.

The inline fragment syntax is:

```
[](#cb46-1)... on <TypeCondition> {
[](#cb46-2)    <fields>
[](#cb46-3)}
```

Consider this schema:

```
[](#cb47-1)type Query {
[](#cb47-2)    pets: [Pet]
[](#cb47-3)}
[](#cb47-4)
[](#cb47-5)interface Pet {
[](#cb47-6)    name: String
[](#cb47-7)}
[](#cb47-8)
[](#cb47-9)type Dog implements Pet {
[](#cb47-10)    name: String
[](#cb47-11)    doesBark: Boolean
[](#cb47-12)}
[](#cb47-13)
[](#cb47-14)type Cat implements Pet {
[](#cb47-15)    name: String
[](#cb47-16)    doesMeow: Boolean
[](#cb47-17)}
```

We can write inline fragments to query the `doesBark` field for Dog results and `doesMeow` for Cat results.

```
[](#cb48-1)query allThePets {
[](#cb48-2)    pets {
[](#cb48-3)        ... on Dog {
[](#cb48-4)            doesBark
[](#cb48-5)        }
[](#cb48-6)        ... on Cat {
[](#cb48-7)            doesMeow
[](#cb48-8)        }
[](#cb48-9)    }
[](#cb48-10)}
```

Depending on the Pet type, we select different fields. We are only interested in `doesBark` for Dogs, while for Cats we are only interested in `doesMeow`.

Types implementing interfaces will likely add additional fields which are not shared across all implementations. For example, the `doesBark` field only appears in the `Dog` type. Fragments or inline fragments must be used to query fields which are not guaranteed across all implementations.

As a counterexample, the query below is invalid because there is no `doesBark` field in the Pet interface.

```
[](#cb49-1)query invalid {
[](#cb49-2)    pets {
[](#cb49-3)        doesBark
[](#cb49-4)    }
[](#cb49-5)}
```

Fragments or inline fragments must be used for union types. A GraphQL union represents an object that could be one of a list of types, but a union does not define any fields itself.

For example, consider this example schema with two important food groups:

```
[](#cb50-1)union Food = Pizza | IceCream
[](#cb50-2)
[](#cb50-3)type Query {
[](#cb50-4)    dinner: [Food]
[](#cb50-5)}
[](#cb50-6)
[](#cb50-7)type Pizza {
[](#cb50-8)    name: String
[](#cb50-9)    toppings: [String]
[](#cb50-10)}
[](#cb50-11)
[](#cb50-12)type IceCream {
[](#cb50-13)    name: String
[](#cb50-14)    flavors: [String]
[](#cb50-15)}
```

A query for `dinner` must include fragments or inline fragments, because the union does not define any fields itself.

```
[](#cb51-1)query healthyDinner {
[](#cb51-2)    dinner {
[](#cb51-3)        ... on Pizza {
[](#cb51-4)            name
[](#cb51-5)            toppings
[](#cb51-6)        }
[](#cb51-7)        ... on IceCream {
[](#cb51-8)            name
[](#cb51-9)            flavors
[](#cb51-10)        }
[](#cb51-11)    }
[](#cb51-12)}
```

The following query is invalid, because the union type `Food` does not define any fields.

```
[](#cb52-1)query invalid {
[](#cb52-2)    dinner {
[](#cb52-3)        toppings
[](#cb52-4)        flavors
[](#cb52-5)    }
[](#cb52-6)}
```

## Variables

We can include parameter variables in a GraphQL operation, which enables clients to reuse operations without needing to dynamically rebuild them.

An operation can declare variables that serve as input for the entire operation.

To declare variables, define them after the operation name. The variable name begins with `$`, and is followed by the type. Variables can be marked as non-null with an exclamation mark `!`, similarly to field or directive arguments.

For example, the variable `petId` is of type ID, and it is non-nullable.

```
[](#cb53-1)query findPet($petId: ID!) {
[](#cb53-2)    pet(id: $petId) {
[](#cb53-3)        name
[](#cb53-4)    }
[](#cb53-5)}
```

A default value can be provided, defined after an equals sign `=`.

```
[](#cb54-1)query findPet2($petId: ID! = "12345DefaultId") {
[](#cb54-2)    pet(id: $petId) {
[](#cb54-3)        name
[](#cb54-4)    }
[](#cb54-5)}
```

It’s possible to have multiple variables. In this example mutation, the first variable is required and the second is not required.

```
[](#cb55-1)mutation changePetName($petId: ID!, $petName: String) {
[](#cb55-2)    changePetName(id: $petId, name: $petName) {
[](#cb55-3)        success
[](#cb55-4)    }
[](#cb55-5)}
```

Variable values are sent alongside the operation. For example, we want to find a pet with ID `9000`.

```
[](#cb56-1)query findPet($petId: ID!) {
[](#cb56-2)    pet(id: $petId) {
[](#cb56-3)        name
[](#cb56-4)    }
[](#cb56-5)}
```

If providing variable values as JSON, to find a pet with ID `9000`, we would send:

```
[](#cb57-1){
[](#cb57-2)  "petId": "9000"
[](#cb57-3)}
```

## Aliases

By default, a key in the response object will be set as the corresponding field name in the operation. Aliases enable renaming of keys in the response.

Define an alias with the name, followed by a colon:

```
[](#cb58-1)query aliases {
[](#cb58-2)    alias1: someField
[](#cb58-3)    alias2: someField
[](#cb58-4)}
```

Although simple renames are handy, aliases are more often used to query the same field multiple times with different arguments. As the response key is set to the field name by default, aliases are essential if we want to use the same field twice. For example:

```
[](#cb59-1)type Query {
[](#cb59-2)    search(filter: String!): String
[](#cb59-3)}
```

```
[](#cb60-1)query searches {
[](#cb60-2)    search1: search(filter: "Foo")
[](#cb60-3)    search2: search(filter: "Bar")
[](#cb60-4)}
```

This query will produce a response including the data:

```
[](#cb61-1){
[](#cb61-2)  "search1": "Foo result",
[](#cb61-3)  "search2": "Bar result"
[](#cb61-4)}
```

## GraphQL document

A GraphQL executable document (often shortened to document) is a text written in GraphQL query language notation that contains at least one query, mutation, or subscription operation and an optional list of fragments.

### Named and unnamed operations

The operation name is the word following the `query`, `mutation`, or `subscription` keyword. In the following example, the operation name is `findPet`.

```
[](#cb62-1)query findPet($petId: ID!) {
[](#cb62-2)    pet(id: $petId) {
[](#cb62-3)        name
[](#cb62-4)    }
[](#cb62-5)}
```

In the GraphQL document, if there are multiple operations, they must all have a name. If there is only one operation, it can be unnamed.

Although the specification permits unnamed operations, we strongly suggest using operation names. They give a meaningful name that explains the intention of an operation. Operation names are invaluable for observability in a production GraphQL service. For example, operation naming helps track query usage over time. You could also ask consumers to use operation names that identify the caller, so it’s easier to track who is using the query.

Nevertheless, we will briefly cover unnamed operations, as they do appear in documentation examples and elsewhere.

If there is only one operation, it can be unnamed. For example this unnamed mutation:

```
[](#cb63-1)mutation {
[](#cb63-2)    changeName(name: "Foo")
[](#cb63-3)}
```

Where the single unnamed operation is a query, the keyword `query` can be dropped. The two following examples are equivalent:

```
[](#cb64-1)query {
[](#cb64-2)    hello
[](#cb64-3)}
```

```
[](#cb65-1){
[](#cb65-2)    hello
[](#cb65-3)}
```

Where there are multiple operations in a document, they must all be named. Here’s an example document with a fragment:

```
[](#cb66-1)query hello {
[](#cb66-2)    ...helloFragment
[](#cb66-3)}
[](#cb66-4)
[](#cb66-5)mutation changeName {
[](#cb66-6)    changeName(name: "Foo")
[](#cb66-7)}
[](#cb66-8)
[](#cb66-9)subscription nameChanged {
[](#cb66-10)    nameChanged
[](#cb66-11)}
[](#cb66-12)
[](#cb66-13)fragment helloFragment on Query {
[](#cb66-14)    hello
[](#cb66-15)}
```

## Query language in GraphQL Java

In GraphQL Java, a query language text is parsed and transformed into an abstract syntax tree (AST) of `graphql.language.Node` instances. For example, a field is a `graphql.language.Field` and an inline fragment is a `graphql.language.InlineFragment`.

GraphQL Java takes care of parsing and validating the request, including the query language text, so normally we do not require direct access to `Node` instances. We won’t go into further depth on this topic as it’s an engine detail and not relevant for implementing a GraphQL service.

In this chapter, we covered GraphQL query language and the three operations, query, mutation, and subscriptions. In the next chapter we’ll discuss [DataFetchers](#ch007.xhtml_datafetchers-part-1), the methods which populate data for fields in a schema.

# DataFetchers

A DataFetcher loads data for exactly one field. It’s the most important concept for executing a GraphQL request, because it’s the logic that connects your schema and your data.

In the first half of this chapter, we will show how to add your data fetching logic to Spring for GraphQL via controller annotations. These controller annotations automate much of the work with DataFetchers, to the point that even the word DataFetcher does not appear in controller code. In the second half of this chapter, we will remove the Spring “magic” and take a look under the hood at how DataFetchers are used by the GraphQL Java engine. By the end of this chapter, you will have a thorough understanding of DataFetchers. We will cover more advanced topics in the [DataFetchers in depth chapter](#ch013.xhtml_datafetchers-in-depth) and take a deep dive into execution in the [Execution chapter](#ch015.xhtml_execution-chapter).

A quick note: DataFetchers are called `Resolver`s in the GraphQL specification and in other implementations. I (Andi) named it DataFetcher because I thought it reflected the purpose better. I am not convinced I would make the same decision today, but now it is too late to change.

A GraphQL operation is basically a tree of fields. The execution is field-oriented: for each field, GraphQL Java loads the data. However, given that GraphQL is agnostic about where the data comes from, we must tell GraphQL Java *how* to load the data.

GraphQL Java needs to know how to load the data **for every field**, therefore **every field has an associated DataFetcher**.

This field-oriented data loading approach differs from REST, where we implement the logic per endpoint for resources. In GraphQL, there is only one endpoint and data loading happens per field depending on the request. This carries over to Spring controllers, where we map every field DataFetcher to a method in a `Controller`. This means that Spring for GraphQL controller methods represent a GraphQL *field*, instead of a REST *resource*.

Although every field has an associated DataFetcher, in practice you don’t have to manually write a DataFetcher for every field. In the [PropertyDataFetcher section](#ch007.xhtml_propertydatafetcher) later in this chapter, we’ll show how most fields can be automatically mapped to DataFetchers.

## Spring for GraphQL annotated methods

Spring for GraphQL provides an annotation-based programming model, where annotated methods are registered as DataFetchers. In the second half of this chapter, we’ll take a closer look at the DataFetcher interface inside the GraphQL Java engine. For now, we’ll see how Spring for GraphQL controller annotations achieve exactly the same result with far less boilerplate code.

Before we go on, there are a few key classes which work closely with DataFetchers. In GraphQL Java, a `GraphQLSchema` is both the structure (or shape) of the API, and all the logic needed to execute requests against it. Another key GraphQL Java concept is `RuntimeWiring`, which contains `GraphQLCodeRegistry`, a map of schema fields to DataFetchers. Each DataFetcher needs to be registered in the `GraphQLCodeRegistry` inside `RuntimeWiring`.

Annotated controller methods enable us to implement a DataFetcher and also automatically register into the `GraphQLCodeRegistry` inside `RuntimeWiring`. While the Spring Boot starter automatically initializes and manages `RuntimeWiring` for GraphQL Java, you also have the full flexibility to manually access and modify it. Later in this chapter, we’ll see how to modify `RuntimeWiring` when we demonstrate how to [add a custom scalar](#ch007.xhtml_add-custom-scalar).

There are four different schema mapping annotations available in Spring for GraphQL: the general `@SchemaMapping`, and three shortcut annotations, `@QueryMapping`, `@MutationMapping`, and `@SubscriptionMapping`.

`@QueryMapping` is a shortcut annotation for the DataFetcher for the query type, `@MutationMapping` and `@SubscriptionMapping` are for mutation and subscription types respectively. All three are shortcuts for the general `@SchemaMapping` annotation, which takes arguments `typeName` and `field`, to indicate which type and field the DataFetcher should be mapped to.

Let’s see these annotations in an example. Here is a Pet schema:

```
[](#cb67-1)type Query {
[](#cb67-2)    favoritePet: Pet
[](#cb67-3)}
[](#cb67-4)
[](#cb67-5)type Pet {
[](#cb67-6)    name: String
[](#cb67-7)    owner: Person
[](#cb67-8)}
[](#cb67-9)
[](#cb67-10)type Person {
[](#cb67-11)    firstName: String
[](#cb67-12)    lastName: String
[](#cb67-13)}
```

With Pet and Owner record classes:

```
[](#cb68-1)package myservice.service;
[](#cb68-2)
[](#cb68-3)record Pet(String name, String ownerId) {
[](#cb68-4)}
```

```
[](#cb69-1)package myservice.service;
[](#cb69-2)
[](#cb69-3)record Person(String id, String firstName, String lastName) {
[](#cb69-4)}
```

This is how to register the two DataFetchers with Spring for GraphQL’s controller annotations.

```
[](#cb70-1)package myservice.service;
[](#cb70-2)
[](#cb70-3)import org.springframework.graphql.data.method.annotation
[](#cb70-4)  .QueryMapping;
[](#cb70-5)import org.springframework.graphql.data.method.annotation
[](#cb70-6)  .SchemaMapping;
[](#cb70-7)import org.springframework.stereotype.Controller;
[](#cb70-8)
[](#cb70-9)@Controller
[](#cb70-10)record PetsController(PetService petService) {
[](#cb70-11)
[](#cb70-12)  @QueryMapping
[](#cb70-13)  Pet favoritePet() {
[](#cb70-14)    return petService.getFavoritePet();
[](#cb70-15)  }
[](#cb70-16)
[](#cb70-17)  @SchemaMapping(typeName = "Pet", field = "owner")
[](#cb70-18)  Person owner(Pet pet) {
[](#cb70-19)    return petService.getPerson(pet.ownerId());
[](#cb70-20)  }
[](#cb70-21)
[](#cb70-22)}
```

The `favoritePet` method is annotated with `@QueryMapping`, indicating it will be registered to a field in the `Query` type. By default, Spring for GraphQL will determine the field name from the method name. This means the `favoritePet` method will be registered as a DataFetcher for the field `favoritePet` in the type `Query`.

The `@QueryMapping` annotation is a shortcut. You can alternatively specify a `field` with the `@QueryMapping` annotation, or use the general `@SchemaMapping` annotation.

The `owner` method is annotated with the general `@SchemaMapping` annotation. The annotation’s attributes indicate this method will be registered as a DataFetcher for the `owner` field in the `Pet` type.

In addition to registering DataFetchers automatically, these annotated methods allow for convenient access to different inputs. In the example above, the `owner` DataFetcher takes a parameter `Pet pet`, which contains the *source* or *parent* object `Pet`, which is necessary to determine the owner’s name.

In the `@SchemaMapping` annotation in our example, we can take an extra shortcut and remove the `typeName` and `field` attributes. When these attributes are not provided, Spring for GraphQL will register the `typeName` as the simple class name of the source or parent object injected into the method (`Pet`), and the `field` name will default to the name of the method (`owner`).

You might be wondering why only two DataFetchers are registered in this controller, considering there were 5 fields in the schema. We’ll see how the remaining fields were automatically wired with DataFetchers in the [PropertyDataFetcher section](#ch007.xhtml_propertydatafetcher) up next in this chapter.

## PropertyDataFetchers in Spring for GraphQL

We stated that **every field has an associated DataFetcher**. However, in the Pet example earlier, we had five fields in the schema and only implemented two DataFetchers with controller annotations. This was not a mistake, and we have not forgotten anything! This is actually a realistic scenario.

While every field has a DataFetcher, **we only need to implement a few DataFetchers ourselves**. The rest are default DataFetchers that GraphQL Java automatically generates, which are called `PropertyDataFetcher`s. This is illustrated in the diagram “DataFetcher per field”.

![DataFetcher per field](media/file11.png)

DataFetcher per field

**A `PropertyDataFetcher` is the perfect choice when the schema matches the Java object returned by the parent DataFetcher.**

Returning to our Pet example is the best way to understand this: we have a `PropertyDataFetcher` for 3 different fields: `Pet.name`, `Person.firstName`, and `Person.lastName`.

The `Pet` record class returned by the `PetService` is:

```
[](#cb71-1)package myservice.service;
[](#cb71-2)
[](#cb71-3)record Pet(String name, String ownerId) {
[](#cb71-4)}
```

And this is the `Person` record class:

```
[](#cb72-1)package myservice.service;
[](#cb72-2)
[](#cb72-3)record Person(String id, String firstName, String lastName) {
[](#cb72-4)}
```

The parent field of `Pet.name` is `Query.favoritePet` and our DataFetcher `favoritePet` returns the Java object `Pet` containing the property `name` exposed via the standard Java getter convention, so the schema GraphQL field `name` matches exactly the Java property. The same is true for `Person`: the second DataFetcher `owner` returns a `Person` Java object with a structure identical to the schema: both contain two strings named `firstName` and `lastName`.

**A `PropertyDataFetcher` fetches the data from a Java object as long as the GraphQL field matches the Java object property.** In our example, it means the Java property follows the Java getter naming convention.

The `PropertyDataFetcher` can also fetch data from Java fields, is compatible with record classes, and can also access values from a `java.util.Map`.

The `Map` support is particularly useful to quickly mock DataFetchers. For example, our `owner` DataFetcher can return the same `Person` using a `Map`.

```
[](#cb73-1)@SchemaMapping
[](#cb73-2)Map<String, String> owner(Pet pet) {
[](#cb73-3)  return Map.of("firstName","Andi",
[](#cb73-4)    "lastName","Marek");
[](#cb73-5)}
```

No other changes are required. The keys of the `Map` match the schema fields `firstName` and `lastName`, so the `PropertyDataFetcher` will load the correct values.

## DataFetchers and schema mapping handler methods

A quick note on naming. `@SchemaMapping` and shortcut annotations `@QueryMapping`, `@MutationMapping`, and `@SubscriptionMapping`, declare schema mapping handler methods, which are then registered as DataFetchers by Spring for GraphQL. There is a one-to-one relationship between a schema mapping handler method and a DataFetcher. Therefore, in the remainder of this book, we’ll use the word DataFetcher for these schema mapping handler methods.

Technically speaking, the schema mapping handler methods do not implement the DataFetcher interface directly. It is the Spring for GraphQL `AnnotatedControllerConfigurer` that registers these handler methods as DataFetchers. However, as these concepts map one-to-one, we want you to think of these schema mapping handler methods as DataFetchers.

## TypeResolver in Spring for GraphQL

If the type of the field is an [interface](#ch005.xhtml_interface) or [union](#ch005.xhtml_union), GraphQL Java needs to determine the actual object type of the value via a `TypeResolver`. For an introduction to interfaces and unions, see the earlier Schema chapter.

For example, let’s consider a Pet interface, which is implemented by Cat and Dog types.

```
[](#cb74-1)type Query {
[](#cb74-2)    favoritePet: Pet
[](#cb74-3)}
[](#cb74-4)
[](#cb74-5)interface Pet {
[](#cb74-6)    name: String
[](#cb74-7)    owner: Person
[](#cb74-8)}
[](#cb74-9)
[](#cb74-10)type Dog implements Pet {
[](#cb74-11)    name: String
[](#cb74-12)    owner: Person
[](#cb74-13)    doesBark: Boolean
[](#cb74-14)}
[](#cb74-15)
[](#cb74-16)type Cat implements Pet {
[](#cb74-17)    name: String
[](#cb74-18)    owner: Person
[](#cb74-19)    doesMeow: Boolean
[](#cb74-20)}
[](#cb74-21)
[](#cb74-22)type Person {
[](#cb74-23)    firstName: String
[](#cb74-24)    lastName: String
[](#cb74-25)}
```

Most likely, you will not need to write your own `TypeResolver`s, because Spring for GraphQL registers a default `ClassNameTypeResolver` which implements the `TypeResolver` interface. It tries to match the simple class name of the value to a `GraphQLObjectType`. If it cannot find a match, it will continue searching through super types, including base classes and interfaces. This default `TypeResolver` is registered when `graphql.GraphQL` is initialized.

The default `ClassNameTypeResolver` is sufficient if your Java model maps 1:1 with your API, without any further configuration. Optionally, you can modify the behaviour of the default `ClassNameTypeResolver` (see [documentation](https://docs.spring.io/spring-graphql/docs/current/reference/html/#execution.graphqlsource.default-type-resolver)) or manually provide your own `TypeResolver` via the `RuntimeWiringConfigurer`.

For this example schema, to make use of the default type resolver, create a `Pet` Java interface, and `Dog` and `Cat` classes which implement `Pet`.

```
[](#cb75-1)package myservice.service;
[](#cb75-2)
[](#cb75-3)interface Pet {
[](#cb75-4)  String name();
[](#cb75-5)  String ownerId();
[](#cb75-6)}
```

```
[](#cb76-1)package myservice.service;
[](#cb76-2)
[](#cb76-3)record Dog(String name, String ownerId, Boolean doesBark) 
[](#cb76-4)  implements Pet {
[](#cb76-5)}
```

```
[](#cb77-1)package myservice.service;
[](#cb77-2)
[](#cb77-3)record Cat(String name, String ownerId, Boolean doesMeow) 
[](#cb77-4)  implements Pet {
[](#cb77-5)}
```

Then add two owner DataFetchers for Dog and Cat types.

```
[](#cb78-1)package myservice.service;
[](#cb78-2)
[](#cb78-3)import org.springframework.graphql.data.method.annotation
[](#cb78-4)  .QueryMapping;
[](#cb78-5)import org.springframework.graphql.data.method.annotation
[](#cb78-6)  .SchemaMapping;
[](#cb78-7)import org.springframework.stereotype.Controller;
[](#cb78-8)
[](#cb78-9)@Controller
[](#cb78-10)record PetsController(PetService petService) {
[](#cb78-11)
[](#cb78-12)  @QueryMapping
[](#cb78-13)  Pet favoritePet() {
[](#cb78-14)    return petService.getFavoritePet();
[](#cb78-15)  }
[](#cb78-16)
[](#cb78-17)  @SchemaMapping
[](#cb78-18)  Person owner(Dog dog) {
[](#cb78-19)    return petService.getPerson(dog.ownerId());
[](#cb78-20)  }
[](#cb78-21)
[](#cb78-22)  @SchemaMapping
[](#cb78-23)  Person owner(Cat cat) {
[](#cb78-24)    return petService.getPerson(cat.ownerId());
[](#cb78-25)  }
[](#cb78-26)
[](#cb78-27)}
```

Here’s a sample query for favorite pet:

```
[](#cb79-1)query bestPet {
[](#cb79-2)    favoritePet {
[](#cb79-3)        name
[](#cb79-4)        owner {
[](#cb79-5)            firstName
[](#cb79-6)        }
[](#cb79-7)        ...on Dog {
[](#cb79-8)            doesBark
[](#cb79-9)        }
[](#cb79-10)        ...on Cat {
[](#cb79-11)            doesMeow
[](#cb79-12)        }
[](#cb79-13)    }
[](#cb79-14)}
```

If you have encountered a case where the default `ClassNameTypeResolver` is not suitable, you can manually register a `TypeResolver` by creating a `RuntimeWiringConfigurer` bean. The `RuntimeWiringConfigurer` has `RuntimeWiring.Builder` as a parameter.

```
[](#cb80-1)package myservice.service;
[](#cb80-2)
[](#cb80-3)import graphql.schema.TypeResolver;
[](#cb80-4)import graphql.schema.idl.TypeRuntimeWiring;
[](#cb80-5)import org.springframework.context.annotation.Bean;
[](#cb80-6)import org.springframework.context.annotation.Configuration;
[](#cb80-7)import org.springframework.graphql.execution
[](#cb80-8)  .RuntimeWiringConfigurer;
[](#cb80-9)
[](#cb80-10)import static graphql.schema.idl.TypeRuntimeWiring.newTypeWiring;
[](#cb80-11)
[](#cb80-12)@Configuration
[](#cb80-13)class Config {
[](#cb80-14)  TypeResolver petTypeResolver = (env) -> {
[](#cb80-15)    // Your custom type resolver logic
[](#cb80-16)  };
[](#cb80-17)
[](#cb80-18)  @Bean
[](#cb80-19)  RuntimeWiringConfigurer runtimeWiringConfigurer() {
[](#cb80-20)    return wiringBuilder -> {
[](#cb80-21)      TypeRuntimeWiring petWiring = newTypeWiring("Pet")
[](#cb80-22)        .typeResolver(petTypeResolver)
[](#cb80-23)        .build();
[](#cb80-24)
[](#cb80-25)      wiringBuilder.type(petWiring);
[](#cb80-26)    };
[](#cb80-27)  }
[](#cb80-28) 
[](#cb80-29)}
```

When we have a closer look at [TypeResolvers in GraphQL Java](#ch007.xhtml_typeresolver-in-graphql-java) later in this chapter, we’ll see how to manually write our own `TypeResolver` with pure GraphQL Java.

### Arguments in Spring for GraphQL

To access a GraphQL argument, declare them via the `@Argument` annotation.

For example, a search field in the schema takes arguments.

```
[](#cb81-1)type Query {
[](#cb81-2)    search(pattern: String, limit: Int): String
[](#cb81-3)}
```

With Spring for GraphQL, the arguments are declared with the `@Argument` annotation.

```
[](#cb82-1)package myservice.service;
[](#cb82-2)
[](#cb82-3)import org.springframework.graphql.data.method.annotation
[](#cb82-4)  .Argument;
[](#cb82-5)import org.springframework.graphql.data.method.annotation
[](#cb82-6)  .QueryMapping;
[](#cb82-7)import org.springframework.stereotype.Controller;
[](#cb82-8)
[](#cb82-9)@Controller
[](#cb82-10)class SearchController {
[](#cb82-11)
[](#cb82-12)  @QueryMapping
[](#cb82-13)  String search(@Argument String pattern, @Argument int limit) {
[](#cb82-14)    // Your search logic here
[](#cb82-15)  }
[](#cb82-16)
[](#cb82-17)}
```

The `@Argument` annotation automatically takes the method parameter name, if available, as the name for the GraphQL argument. Note this requires the `-parameters` compiler flag with Java 8+ or debugging information from the compiler. You most likely have this flag already enabled.

It’s also possible to customise the name through the annotation, as in this example:

```
[](#cb83-1)package myservice.service;
[](#cb83-2)
[](#cb83-3)import org.springframework.graphql.data.method.annotation
[](#cb83-4)  .Argument;
[](#cb83-5)import org.springframework.graphql.data.method.annotation
[](#cb83-6)  .QueryMapping;
[](#cb83-7)import org.springframework.stereotype.Controller;
[](#cb83-8)
[](#cb83-9)@Controller
[](#cb83-10)class SearchController {
[](#cb83-11)
[](#cb83-12)  @QueryMapping
[](#cb83-13)  String search(@Argument("pattern") String searchPattern,
[](#cb83-14)                       @Argument("limit") int maxElements) {
[](#cb83-15)    // Your search logic here
[](#cb83-16)  }
[](#cb83-17)
[](#cb83-18)}
```

Spring for GraphQL makes it much easier to use input object arguments. We’ll see later in this chapter that in GraphQL Java, we always get `java.util.Map` for input objects. Spring for GraphQL makes this step easier by binding GraphQL arguments to Java classes automatically, if they are compatible.

For example, a search schema with an input object argument:

```
[](#cb84-1)type Query {
[](#cb84-2)    search(input: SearchInput): String
[](#cb84-3)}
[](#cb84-4)
[](#cb84-5)input SearchInput {
[](#cb84-6)    pattern: String
[](#cb84-7)    limit: Int
[](#cb84-8)}
```

The `SearchInput` record class:

```
[](#cb85-1)package myservice.service;
[](#cb85-2)
[](#cb85-3)record SearchInput(String pattern, int limit) {
[](#cb85-4)}
```

And the search controller method:

```
[](#cb86-1)package myservice.service;
[](#cb86-2)
[](#cb86-3)import org.springframework.graphql.data.method.annotation
[](#cb86-4)  .Argument;
[](#cb86-5)import org.springframework.graphql.data.method.annotation
[](#cb86-6)  .QueryMapping;
[](#cb86-7)import org.springframework.stereotype.Controller;
[](#cb86-8)
[](#cb86-9)@Controller
[](#cb86-10)class SearchController {
[](#cb86-11)
[](#cb86-12)  @QueryMapping
[](#cb86-13)  String search(@Argument SearchInput input) {
[](#cb86-14)    // Your search logic here
[](#cb86-15)  }
[](#cb86-16)
[](#cb86-17)}
```

The input object is bound to an instance of `SearchInput`. This is easier to work with than the `java.util.Map` that represents input objects when using GraphQL Java without Spring for GraphQL.

Without Spring for GraphQL’s argument injection, the input object would be a map, which is not as convenient to work with.

```
[](#cb87-1)package myservice.service;
[](#cb87-2)
[](#cb87-3)import graphql.schema.DataFetchingEnvironment;
[](#cb87-4)import org.springframework.graphql.data.method.annotation
[](#cb87-5)  .QueryMapping;
[](#cb87-6)import org.springframework.stereotype.Controller;
[](#cb87-7)
[](#cb87-8)import java.util.Map;
[](#cb87-9)
[](#cb87-10)@Controller
[](#cb87-11)class SearchController {
[](#cb87-12)
[](#cb87-13)  @QueryMapping
[](#cb87-14)  String search(DataFetchingEnvironment env) {
[](#cb87-15)    Map<String, Object> input = env.getArgument("input");
[](#cb87-16)    String pattern = (String) input.get("pattern");
[](#cb87-17)    int limit = (int) input.get("limit");
[](#cb87-18)    // Your search logic here
[](#cb87-19)  }
[](#cb87-20)
[](#cb87-21)}
```

## More Spring for GraphQL inputs

Spring for GraphQL also supports the following method parameters for schema mapping handler methods.

| Argument | Description |
| --- | --- |
| @Arguments | Binding all arguments to a single object |
| “Source” | Access to the source (parent) instance of the field |
| DataLoader | A `DataLoader` from the `DataLoaderRegistry`. See the chapter about [DataLoader](#ch007.xhtml_data-loader) |
| @ContextValue | A value from the main `GraphQLContext` in `DataFetchingEnvironment`. See more on context in the [DataFetchers in depth chapter](#ch013.xhtml_global-context) |
| @LocalContextValue | A value from the local `GraphQLContext` in `DataFetchingEnvironment` |
| GraphQLContext | The entire `GraphQLContext` |
| java.security.Principal | The currently authenticated principal that made this request. See the chapter about [Security](#ch007.xhtml_Security) for more. This is `SecurityContext.getAuthentication()` |
| DataFetchingFieldSelectionSet | The `DataFetchingFieldSelectionSet` from `DataFetchingEnvironment` |
| Locale or `Optional<Locale>` | The current locale for the request, from `DataFetchingEnvironment` |
| DataFetchingEnvironment | The entire `DataFetchingEnvironment` |

## Adding custom scalars in Spring for GraphQL

In the [Schema chapter](#ch005.xhtml_scalar), we discussed that in addition to the built-in scalar types, it is possible to add custom scalars.

A common custom scalar to add is `Date`. In the Schema chapter we saw that custom scalars must be declared in the schema:

```
[](#cb88-1)"""
[](#cb88-2)A custom scalar representing a date without any time zone.
[](#cb88-3)Note how this custom scalar must be declared explicitly.
[](#cb88-4)"""
[](#cb88-5)scalar Date @specifiedBy(url:
[](#cb88-6)"https://scalars.graphql.org/andimarek/local-date")
[](#cb88-7)
[](#cb88-8)type Pet {
[](#cb88-9)    "String is a built-in scalar, therefore no declaration is required."
[](#cb88-10)    name: String
[](#cb88-11)    dateOfBirth: Date
[](#cb88-12)}
```

You can use custom scalar implementations from libraries or implement your own. In this example we’ll demonstrate the [GraphQL Java Extended Scalars](https://github.com/graphql-java/graphql-java-extended-scalars) library, which is maintained by the GraphQL Java team.

To use the `Date` scalar in the GraphQL Java Extended Scalars library, add the package.

For Gradle, add this to your `build.gradle` file:

```
[](#cb89-1)implementation 'com.graphql-java:graphql-java-extended-scalars:19.1'
```

For Maven:

```
[](#cb90-1)<dependency>
[](#cb90-2)  <groupId>com.graphql-java</groupId>
[](#cb90-3)  <artifactId>graphql-java-extended-scalars</artifactId>
[](#cb90-4)  <version>19.1</version>
[](#cb90-5)</dependency>
```

Note: the major version number of the Extended Scalars library corresponds to the linked major version of the main GraphQL Java release. As examples in this book were written with Spring for GraphQL 1.1.2 which uses GraphQL Java 19.2, we’ll use Extended Scalars 19.1.

To wire custom scalars in Spring for GraphQL, create a `RuntimeWiringConfigurer` bean. This will link the `Date` implementation in `graphql-java-extended-scalars` to the `scalar Date` declared in your schema.

```
[](#cb91-1)package myservice.service;
[](#cb91-2)
[](#cb91-3)import graphql.scalars.ExtendedScalars;
[](#cb91-4)import org.springframework.context.annotation.Bean;
[](#cb91-5)import org.springframework.context.annotation.Configuration;
[](#cb91-6)import org.springframework.graphql.execution
[](#cb91-7)  .RuntimeWiringConfigurer;
[](#cb91-8)
[](#cb91-9)@Configuration
[](#cb91-10)class GraphQlConfig {
[](#cb91-11) 
[](#cb91-12)  @Bean
[](#cb91-13)  RuntimeWiringConfigurer runtimeWiringConfigurer() {
[](#cb91-14)    return wiringBuilder ->
[](#cb91-15)      wiringBuilder.scalar(ExtendedScalars.Date);
[](#cb91-16)  }
[](#cb91-17) 
[](#cb91-18)}
```

The Spring Boot Starter automatically detects all `RuntimeWiringConfigurer` beans.

## Under the hood: DataFetchers inside GraphQL Java

Spring for GraphQL automates much of the work to register DataFetchers with schema fields. By using Spring for GraphQL controller annotations, you might never even see the words DataFetcher nor `RuntimeWiring`.

To build a deeper understanding of how Spring for GraphQL connects data fetching logic to the schema, we are going to discuss how GraphQL Java works under the hood. In your Spring for GraphQL application, you won’t need to write any of the code in the remainder of this chapter, but we hope that by showing you the fundamentals, we concretely explain the “magic” of Spring.

In this second half of the chapter, we will build up to an executable schema with pure GraphQL Java. A complete end-to-end example is presented later in this chapter.

## DataFetchers in GraphQL Java

Recall that a GraphQL operation is basically a tree of fields. We need to instruct GraphQL Java how to load the data for every field. Therefore, every field must have an associated DataFetcher.

Earlier in this chapter we covered how to create and register DataFetchers with Spring for GraphQL’s controller annotations such as `@QueryMapping` and `@SchemaMapping`. Now let’s see how to write the equivalent code for the Pet schema without any Spring automated “magic”.

A DataFetcher loads data for exactly one field. Inside GraphQL Java, it is represented as a very generic Java interface.

```
[](#cb92-1)public interface DataFetcher<T> {
[](#cb92-2)  T get(DataFetchingEnvironment environment) throws Exception;
[](#cb92-3)}
```

The interface has only one method `get` with one argument `DataFetchingEnvironment`. The returned result can be anything. This interface directly reflects a core principle of GraphQL, it is agnostic about where the data comes from.

Let’s implement DataFetchers for the simple Pet schema in the earlier Spring for GraphQL example. Note that we are implementing the initial example, where Pet is an object type and not an interface.

```
[](#cb93-1)type Query {
[](#cb93-2)    favoritePet: Pet
[](#cb93-3)}
[](#cb93-4)
[](#cb93-5)type Pet {
[](#cb93-6)    name: String
[](#cb93-7)    owner: Person
[](#cb93-8)}
[](#cb93-9)
[](#cb93-10)type Person {
[](#cb93-11)    firstName: String
[](#cb93-12)    lastName: String
[](#cb93-13)}
```

As a general rule, at least every root field needs to have a DataFetcher implemented. Let’s implement the DataFetcher for `Query.favoritePet`. Note that the logic is identical to the `favoritePet` controller method in the Spring for GraphQL example earlier in this chapter.

```
[](#cb94-1)// Lower level layer service does the work of retrieving data
[](#cb94-2)PetService petService = new PetService();
[](#cb94-3)
[](#cb94-4)DataFetcher<Pet> favoritePetDataFetcher = (env) -> {
[](#cb94-5)  return petService.getFavoritePet();
[](#cb94-6)};
```

This DataFetcher also reflects best practice: a DataFetcher should be slim. A DataFetcher should only take care of GraphQL-specific aspects, and delegate the actual data retrieval to a layer below.

This particular `favoritePetDataFetcher` is quite simple, and does not make use of the `DataFetchingEnvironment` (`env`) at all.

The `Pet` record class returned by the `PetService` is the same as the class used in the Spring for GraphQL example earlier in this chapter.

```
[](#cb95-1)package myservice.service;
[](#cb95-2)
[](#cb95-3)record Pet(String name, String ownerId) {
[](#cb95-4)}
```

And this is the `Person` record class:

```
[](#cb96-1)package myservice.service;
[](#cb96-2)
[](#cb96-3)record Person(String id, String firstName, String lastName) {
[](#cb96-4)}
```

As `Pet` contains only a `ownerId` and not a full `Person` object, we need to load more data. Let’s implement another DataFetcher.

```
[](#cb97-1)// Lower level layer service does the work of retrieving data
[](#cb97-2)PetService petService = new PetService();
[](#cb97-3)
[](#cb97-4)DataFetcher<Pet> favoritePetDataFetcher = (env) -> {
[](#cb97-5)  return petService.getFavoritePet();
[](#cb97-6)};
[](#cb97-7)
[](#cb97-8)DataFetcher<Person> ownerDataFetcher = (env) -> {
[](#cb97-9)  // Load the correct Person for the Pet
[](#cb97-10)  Pet pet = env.getSource();
[](#cb97-11)  return petService.getPerson(pet.ownerId());
[](#cb97-12)};
```

In the `ownerDataFetcher`, we need to access the `source` object of the `DataFetchingEnvironment`, which is an object of type `Pet`. The pet instance information is necessary in order to retrieve the details of the owner.

To highlight the convenience of Spring for GraphQL, let’s compare to the `owner` DataFetcher we wrote previously:

```
[](#cb98-1)@SchemaMapping
[](#cb98-2)Person owner(Pet pet) {
[](#cb98-3)  return petService.getPerson(pet.ownerId());
[](#cb98-4)}
```

Spring for GraphQL injects the `Pet` source object as a method parameter, rather than having to manually access it from the `DataFetchingEnvironment` with `env.getSource()`.

## Source objects in GraphQL Java

Let’s expand on the previous example to understand better how DataFetchers work in practice and discuss the important `source` object.

**The `source` comes from the result of the parent field DataFetcher**, which was executed before the child DataFetcher. The `source` can be anything, so the actual method signature in `DataFetchingEnvironment` is very generic.

```
[](#cb99-1)<T> T getSource(); // in DataFetchingEnvironment
```

In the previous section, we implemented an `ownerDataFetcher`. The purpose of the `ownerDataFetcher` is to load a `Person`.

```
[](#cb100-1)DataFetcher<Person> ownerDataFetcher = (env) -> {
[](#cb100-2)  // Load the correct Person for the Pet
[](#cb100-3)  Pet pet = env.getSource();
[](#cb100-4)  return petService.getPerson(pet.ownerId());
[](#cb100-5)};
```

We know that the parent DataFetcher `favoritePet` returned a `Pet`. We can access the parent DataFetcher result via the `source` object of the `DataFetchingEnvironment`.

```
[](#cb101-1)Pet pet = env.getSource();
```

Then use the pet’s owner ID to look up the owner:

```
[](#cb102-1)return petService.getPerson(pet.ownerId());
```

We can always safely assume that `source` is not `null`, except for the root fields because a root field doesn’t have a parent field. If a DataFetcher returns `null`, which can be a valid response, the execution stops and the child DataFetchers are never invoked.

The `source` object is specific for every non-root DataFetcher. It gives each child DataFetcher a source of data and additional information.

The `source` object also couples the DataFetchers together. The `ownerDataFetcher` is not generic logic that can load any `Person`, rather it requires that the parent field DataFetcher has loaded a `Pet` object.

## RuntimeWiring in GraphQL Java

`RuntimeWiring` is the GraphQL Java class which contains `GraphQLCodeRegistry`, which maps schema fields to DataFetchers.

We have implemented our two DataFetchers, but we haven’t yet instructed GraphQL Java which schema fields these correspond to. This is how to manually register the DataFetchers in the `RuntimeWiring` with pure GraphQL Java code.

```
[](#cb103-1)TypeRuntimeWiring queryWiring = newTypeWiring("Query")
[](#cb103-2)  .dataFetcher("favoritePet", favoritePetDataFetcher)
[](#cb103-3)  .build();
[](#cb103-4)TypeRuntimeWiring petWiring = newTypeWiring("Pet")
[](#cb103-5)  .dataFetcher("owner", ownerDataFetcher)
[](#cb103-6)  .build();
[](#cb103-7)
[](#cb103-8)RuntimeWiring runtimeWiring = newRuntimeWiring()
[](#cb103-9)  .type(queryWiring)
[](#cb103-10)  .type(petWiring)
[](#cb103-11)  .build();
```

Spring for GraphQL’s schema mapping annotations implement DataFetchers and automatically register them to their correct field and type coordinates in the schema in the `GraphQLCodeRegistry` inside `RuntimeWiring`.

## Creating an executable schema in GraphQL Java

At the start of the [annotated methods section](#ch007.xhtml_annotated-methods) of this chapter, we mentioned there are a few key GraphQL Java classes which work closely with DataFetchers. Let’s see how these classes come together to create an executable schema in GraphQL Java.

A `GraphQLSchema` is both the structure of the API, and all the logic needed to execute requests against it.

We saw [earlier](#ch007.xhtml_runtimewiring) in this chapter that another key concept `RuntimeWiring`, contains `GraphQLCodeRegistry`, which maps schema fields to DataFetchers. Each DataFetcher needs to be registered in the `GraphQLCodeRegistry` inside `RuntimeWiring`.

In pure GraphQL Java code, here is a creation of `GraphQLSchema` from start to finish, and an example of a query being executed.

```
[](#cb104-1)import graphql.GraphQL;
[](#cb104-2)import graphql.schema.DataFetcher;
[](#cb104-3)import graphql.schema.GraphQLSchema;
[](#cb104-4)import graphql.schema.idl.RuntimeWiring;
[](#cb104-5)import graphql.schema.idl.SchemaGenerator;
[](#cb104-6)import graphql.schema.idl.SchemaParser;
[](#cb104-7)import graphql.schema.idl.TypeDefinitionRegistry;
[](#cb104-8)import graphql.schema.idl.TypeRuntimeWiring;
[](#cb104-9)import myservice.service.Person;
[](#cb104-10)import myservice.service.Pet;
[](#cb104-11)import myservice.service.PetService;
[](#cb104-12)
[](#cb104-13)import static graphql.schema.idl.RuntimeWiring.newRuntimeWiring;
[](#cb104-14)import static graphql.schema.idl.TypeRuntimeWiring.newTypeWiring;
[](#cb104-15)
[](#cb104-16)public class PureGraphQLJava {
[](#cb104-17)
[](#cb104-18)  public static void main(String[] args) {
[](#cb104-19)    String sdl = """
[](#cb104-20) type Query {
[](#cb104-21) favoritePet: Pet
[](#cb104-22) }
[](#cb104-23) 
[](#cb104-24) type Pet {
[](#cb104-25) name: String
[](#cb104-26) owner: Person
[](#cb104-27) }
[](#cb104-28) 
[](#cb104-29) type Person {
[](#cb104-30) firstName: String
[](#cb104-31) lastName: String
[](#cb104-32) }
[](#cb104-33) """;
[](#cb104-34)    TypeDefinitionRegistry parsedSdl = new SchemaParser().parse(sdl);
[](#cb104-35)
[](#cb104-36)    // Lower level layer service does the work of retrieving data
[](#cb104-37)    PetService petService = new PetService();
[](#cb104-38)
[](#cb104-39)    DataFetcher<Pet> favoritePetDataFetcher = (env) -> {
[](#cb104-40)      return petService.getFavoritePet();
[](#cb104-41)    };
[](#cb104-42)
[](#cb104-43)    DataFetcher<Person> ownerDataFetcher = (env) -> {
[](#cb104-44)      // Load the correct Person for the Pet
[](#cb104-45)      Pet pet = env.getSource();
[](#cb104-46)      return petService.getPerson(pet.ownerId());
[](#cb104-47)    };
[](#cb104-48)
[](#cb104-49)    TypeRuntimeWiring queryWiring = newTypeWiring("Query")
[](#cb104-50)      .dataFetcher("favoritePet", favoritePetDataFetcher)
[](#cb104-51)      .build();
[](#cb104-52)    TypeRuntimeWiring petWiring = newTypeWiring("Pet")
[](#cb104-53)      .dataFetcher("owner", ownerDataFetcher)
[](#cb104-54)      .build();
[](#cb104-55)
[](#cb104-56)    RuntimeWiring runtimeWiring = newRuntimeWiring()
[](#cb104-57)      .type(queryWiring)
[](#cb104-58)      .type(petWiring)
[](#cb104-59)      .build();
[](#cb104-60)
[](#cb104-61)    GraphQLSchema schema = new SchemaGenerator()
[](#cb104-62)      .makeExecutableSchema(parsedSdl, runtimeWiring);
[](#cb104-63)    GraphQL graphQL = GraphQL.newGraphQL(schema).build();
[](#cb104-64)    System.out.println("data:" + graphQL
[](#cb104-65)      .execute("query pureGJ {favoritePet{name owner{firstName}}}")
[](#cb104-66)      .getData());
[](#cb104-67)  }
[](#cb104-68) 
[](#cb104-69)}
```

The schema is first parsed from a string. This schema could alternatively be parsed from a file. Then, the `TypeRuntimeWiring` objects containing our two DataFetchers are instantiated. Then the `TypeRuntimeWiring` objects are registered in the `RuntimeWiring`. Finally, the executable schema is created by combining both the parsed schema and the `RuntimeWiring`. Luckily, you won’t have to write any of this boilerplate code to instantiate an executable schema, as this is automatically managed by Spring for GraphQL.

## TypeResolver in GraphQL Java

If the type of the field is an interface or union, GraphQL Java needs to determine the actual object of the value via a `TypeResolver`. In GraphQL Java, a `TypeResolver` is a very generic Java interface:

```
[](#cb105-1)public interface TypeResolver {
[](#cb105-2)  GraphQLObjectType getType(TypeResolutionEnvironment env);
[](#cb105-3)}
```

Every interface and union type has an associated `TypeResolver`, similar to how every field has an associated DataFetcher. The `TypeResolver` interface needs to be implemented.

If using GraphQL Java without Spring for GraphQL’s default `ClassNameTypeResolver`, we would have to implement our own `TypeResolver`. It’s worth reviewing this example to understand how a `TypeResolver` works without the Spring magic. For example, let’s write a Pet `TypeResolver` for this expanded Pet schema.

```
[](#cb106-1)type Query {
[](#cb106-2)    favoritePet: Pet
[](#cb106-3)}
[](#cb106-4)
[](#cb106-5)interface Pet {
[](#cb106-6)    name: String
[](#cb106-7)    owner: Person
[](#cb106-8)}
[](#cb106-9)
[](#cb106-10)type Dog implements Pet {
[](#cb106-11)    name: String
[](#cb106-12)    owner: Person
[](#cb106-13)    doesBark: Boolean
[](#cb106-14)}
[](#cb106-15)
[](#cb106-16)type Cat implements Pet {
[](#cb106-17)    name: String
[](#cb106-18)    owner: Person
[](#cb106-19)    doesMeow: Boolean
[](#cb106-20)}
[](#cb106-21)
[](#cb106-22)type Person {
[](#cb106-23)    firstName: String
[](#cb106-24)    lastName: String
[](#cb106-25)}
```

If using GraphQL Java directly, this is how to implement a `TypeResolver` for the Pet interface above. In this example, we map Java classes to schema types. However, you could implement any logic here to resolve types.

```
[](#cb107-1)TypeResolver petTypeResolver = (env) -> {
[](#cb107-2)  Object javaObject = env.getObject();
[](#cb107-3)  if (javaObject instanceof Dog) {
[](#cb107-4)    return env.getSchema().getObjectType("Dog");
[](#cb107-5)  } else if (javaObject instanceof Cat) {
[](#cb107-6)    return env.getSchema().getObjectType("Cat");
[](#cb107-7)  } else {
[](#cb107-8)    return null;
[](#cb107-9)  }
[](#cb107-10)};
```

This `TypeResolver` is then registered with the `RuntimeWiring` via a `TypeRuntimeWiring`, similar to how DataFetchers are registered. This how to register the `TypeResolver`, as well as the new DataFetcher wiring required for the Cat and Dog types.

```
[](#cb108-1)// Lower level layer service does the work of retrieving data
[](#cb108-2)PetService petService = new PetService();
[](#cb108-3)
[](#cb108-4)DataFetcher<Pet> favoritePetDataFetcher = (env) -> {
[](#cb108-5)  return petService.getFavoritePet();
[](#cb108-6)};
[](#cb108-7)
[](#cb108-8)DataFetcher<Person> ownerDataFetcher = (env) -> {
[](#cb108-9)  // Load the correct Person for the Pet
[](#cb108-10)  Pet pet = env.getSource();
[](#cb108-11)  return petService.getPerson(pet.ownerId());
[](#cb108-12)  };
[](#cb108-13)
[](#cb108-14)TypeResolver petTypeResolver = (env) -> {
[](#cb108-15)  Object javaObject = env.getObject();
[](#cb108-16)  if (javaObject instanceof Dog) {
[](#cb108-17)    return env.getSchema().getObjectType("Dog");
[](#cb108-18)  } else if (javaObject instanceof Cat) {
[](#cb108-19)    return env.getSchema().getObjectType("Cat");
[](#cb108-20)  } else {
[](#cb108-21)    return null;
[](#cb108-22)  }
[](#cb108-23)};
[](#cb108-24)
[](#cb108-25)TypeRuntimeWiring queryWiring = newTypeWiring("Query")
[](#cb108-26)  .dataFetcher("favoritePet", favoritePetDataFetcher)
[](#cb108-27)  .build();
[](#cb108-28)
[](#cb108-29)TypeRuntimeWiring petWiring = newTypeWiring("Pet")
[](#cb108-30)  .typeResolver(petTypeResolver)
[](#cb108-31)  .build();
[](#cb108-32)
[](#cb108-33)TypeRuntimeWiring catWiring = newTypeWiring("Cat")
[](#cb108-34)  .dataFetcher("owner", ownerDataFetcher)
[](#cb108-35)  .build();
[](#cb108-36)
[](#cb108-37)TypeRuntimeWiring dogWiring = newTypeWiring("Dog")
[](#cb108-38)  .dataFetcher("owner", ownerDataFetcher)
[](#cb108-39)  .build();
[](#cb108-40)
[](#cb108-41)RuntimeWiring runtimeWiring = newRuntimeWiring()
[](#cb108-42)  .type(queryWiring)
[](#cb108-43)  .type(petWiring)
[](#cb108-44)  .type(catWiring)
[](#cb108-45)  .type(dogWiring)
[](#cb108-46)  .build();
```

Most likely, you will not need to write nor register any `TypeResolver`s and instead make use of Spring for GraphQL’s default `ClassNameTypeResolver`. However, we hope this section gives you a better understanding of how interfaces and unions are resolved in GraphQL Java.

In this chapter, we covered the essentials of DataFetchers, the logic that connects your schema to your data. We saw how to create DataFetchers in Spring for GraphQL. We then took a look under the hood in GraphQL Java. We saw how DataFetchers work in GraphQL Java, and re-created the same DataFetchers and executable schema without the Spring “magic”.

We hope you have a much better understanding of DataFetchers and how Spring for GraphQL eliminates much of the boilerplate code. We will cover more advanced topics in the [DataFetchers in depth chapter](#ch013.xhtml_datafetchers-in-depth) and take a deep dive into execution in the [Execution chapter](#ch015.xhtml_execution-chapter).

# Building a GraphQL service

This chapter focuses on the more hands-on aspects of building a service with Spring for GraphQL, and makes use of the concepts we covered in the previous chapters. We will build upon the service we started in the Introduction chapter. By the end of this chapter, you will implement a more substantial GraphQL service.

## Spring for GraphQL

The Spring for GraphQL homepage is https://spring.io/projects/spring-graphql and the source code can be accessed on GitHub at https://github.com/spring-projects/spring-graphql.

The best way to get a project up and running with Spring for GraphQL is via the Spring Initializr tool at https://start.spring.io. We previously created the application in the [“Your first Spring for GraphQL service”](#ch003.xhtml_first-spring-service) section of the Introduction chapter.

The Spring for GraphQL project contains multiple artifacts:

**`org.springframework.graphql:spring-graphql`:** Integrates GraphQL Java with the Spring framework.

**`org.springframework.boot:spring-boot-starter-graphql`:** This is the Spring Boot Starter for GraphQL.

**`org.springframework.graphql:spring-graphql-test:`** Testing support for Spring for GraphQL. We’ll discuss this in the [Testing](#ch018.xhtml_testing) chapter.

In addition to the Spring for GraphQL repo, some Boot-specific code is in the [Spring Boot repository](https://github.com/spring-projects/spring-boot).

When we write “Spring for GraphQL”, we always mean Spring for GraphQL with Spring Boot.

## GraphQL Java

GraphQL Java is automatically included with Spring for GraphQL. If you are using GraphQL Java directly, it can be added to your project as a dependency via Maven or Gradle.

The GraphQL Java homepage is https://www.graphql-java.com and the source code can be accessed on GitHub at https://github.com/graphql-java/graphql-java.

GraphQL Java has minimal dependencies to maximize its usage. [SLF4J](https://www.slf4j.org/) is the only key dependency.

Every version of GraphQL Java has two parts: the major and bug fix part. At the time of writing, the latest Spring for GraphQL 1.1.2 uses GraphQL Java 19.2\. GraphQL Java doesn’t use semantic versioning.

## Spring WebFlux or Spring MVC

Spring for GraphQL supports both reactive Spring WebFlux and Spring MVC. When starting a new project, choose either

```
org.springframework.boot:spring-boot-starter-webflux
```

or

```
org.springframework.boot:spring-boot-starter-web
```

as a dependency. Spring for GraphQL automatically detects either dependency. In this chapter, we will use WebFlux in the examples, but all examples can be easily changed to their Spring MVC equivalent by removing the `Mono` and `Flux` types.

## Reading schemas

Spring for GraphQL then scans for schema files in `src/main/resources/graphql/` ending with `*.graphqls` or `*.gqls`. After the schema files are found and successfully loaded, Spring for GraphQL exposes the GraphQL API at the endpoint `/graphql` by default.

## Configuration properties

Spring for GraphQL offers configuration properties to adjust the default behavior without writing any code.

**Path:** By default, the GraphQL API is exposed via `/graphql`. This can be modified by setting `spring.graphql.path` to another value.

**GraphiQL:** GraphiQL is an interactive, in-browser GraphQL IDE. Spring for GraphQL comes with built-in GraphiQL support, but it’s not enabled by default. Activate it with `spring.graphql.graphiql.enabled=true`. The default GraphiQL path is `/graphiql`, which can be modified with `spring.graphql.graphiql.path`.

**Schema files:** Spring for GraphQL scans Schema Definition Language (SDL) files with default file extensions `*.graphqls` and `*.gqls` from the default location `classpath:graphql/**/`.

You can modify file extensions with `spring.graphql.schema.locations.file-extensions` and modify the location with `spring.graphql.schema.locations`.

## Expanding our Spring for GraphQL service

In the “Your first Spring for GraphQL service” section of the [introduction chapter](#ch003.xhtml_first-spring-service), we built a minimal Spring for GraphQL service and executed our first query. Let’s revisit key Spring for GraphQL concepts from the past few chapters and build a more fully featured GraphQL service.

## Pet schema

Let’s continue with the GraphQL service we started in the “Your first Spring for GraphQL service” section of the [introduction chapter](#ch003.xhtml_first-spring-service), an API for pets. Review the Introduction chapter for instructions on how to create and download a Spring for GraphQL service.

We have a simple query field `pets` which returns basic information about Pets. You should already have this schema file saved in the file `src/main/resources/graphql/schema.graphqls`.

```
[](#cb111-1)type Query {
[](#cb111-2)    pets: [Pet]
[](#cb111-3)}
[](#cb111-4)
[](#cb111-5)type Pet {
[](#cb111-6)    name: String
[](#cb111-7)    color: String
[](#cb111-8)}
```

## Controllers

Recall from the [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1) that DataFetchers load data for exactly one field. They are the most important concept in executing a GraphQL request because they represent the logic that connects your schema and your data.

We will use Spring for GraphQL’s [annotation-based programming model](#ch007.xhtml_annotated-methods) to register DataFetchers, which was previously discussed in the DataFetchers chapter. `@Controller` components use annotations to declare handler methods as DataFetchers for specific GraphQL fields. As we have a query field `pets`, let’s use the shortcut `@QueryMapping` annotation. We’ll represent Pets in Java as a record class.

```
[](#cb112-1)package myservice.service;
[](#cb112-2)
[](#cb112-3)record Pet(String name, String color) {
[](#cb112-4)}
```

```
[](#cb113-1)package myservice.service;
[](#cb113-2)
[](#cb113-3)import org.springframework.graphql.data.method.annotation
[](#cb113-4)  .QueryMapping;
[](#cb113-5)import org.springframework.stereotype.Controller;
[](#cb113-6)
[](#cb113-7)import java.util.List;
[](#cb113-8)
[](#cb113-9)@Controller
[](#cb113-10)class PetsController {
[](#cb113-11)
[](#cb113-12)  @QueryMapping
[](#cb113-13)  List<Pet> pets() {
[](#cb113-14)    return List.of(
[](#cb113-15)      new Pet("Luna", "cappuccino"),
[](#cb113-16)      new Pet("Skipper", "black"));
[](#cb113-17)  }
[](#cb113-18)
[](#cb113-19)}
```

The `@QueryMapping` shortcut annotation registers the `pets()` method as a DataFetcher for the query field `pets`. We did not have to specify the schema field name, because it was automatically detected from the method name. For more on `@SchemaMapping` and shortcut versions such as `@QueryMapping`, see the [annotated methods section](#ch007.xhtml_annotated-methods) in the DataFetchers chapter.

In this example, we don’t need to manually write DataFetchers for the Pet fields `name` and `color`. Recall that [PropertyDataFetchers](#ch007.xhtml_propertydatafetcher) for `name` and `color` are automatically registered, because the GraphQL fields match the Java object’s properties. For more on PropertyDataFetchers, see the earlier DataFetchers chapter.

The `pets()` method is currently returning an in-memory list. We’ll change this to call another service in the next section.

## Fetching data from an external service

GraphQL is agnostic about the source of your data. Let’s upgrade our data source from an in-memory list to a more realistic scenario. In a production service, it’s likely you want to fetch data from another service, such as a REST service with the help of Spring `WebClient`.

```
[](#cb114-1)package myservice.service;
[](#cb114-2)
[](#cb114-3)import org.springframework.graphql.data.method.annotation
[](#cb114-4)  .QueryMapping;
[](#cb114-5)import org.springframework.stereotype.Controller;
[](#cb114-6)import org.springframework.web.reactive.function.client
[](#cb114-7)  .WebClient;
[](#cb114-8)import reactor.core.publisher.Flux;
[](#cb114-9)
[](#cb114-10)@Controller
[](#cb114-11)class PetsController {
[](#cb114-12)
[](#cb114-13)  WebClient petWebClient;
[](#cb114-14)
[](#cb114-15)  PetsController(WebClient.Builder builder) {
[](#cb114-16)    this.petWebClient = builder.baseUrl("http://pet-service").build();
[](#cb114-17)  }
[](#cb114-18)
[](#cb114-19)  @QueryMapping
[](#cb114-20)  Flux<Pet> pets() {
[](#cb114-21)    return petWebClient.get()
[](#cb114-22)      .uri("/pets")
[](#cb114-23)      .retrieve()
[](#cb114-24)      .bodyToFlux(Pet.class);
[](#cb114-25)  }
[](#cb114-26)
[](#cb114-27)}
```

In our upgraded `pets` DataFetcher, the `bodyToFlux` call returns a `Flux<Pet>` based on the JSON response of `http://pets-service/pets`. This is a placeholder URL in place of a REST endpoint. If you do not yet have an external service in mind, you can revert to using in-memory objects for the following examples.

## Source object

A core concept of GraphQL is that you can write flexible queries to retrieve exactly the information you need.

Let’s expand our Pet schema to model one owner per pet.

```
[](#cb115-1)type Query {
[](#cb115-2)    pets: [Pet]
[](#cb115-3)}
[](#cb115-4)
[](#cb115-5)type Pet {
[](#cb115-6)    name: String
[](#cb115-7)    color: String
[](#cb115-8)    owner: Person
[](#cb115-9)}
[](#cb115-10)
[](#cb115-11)type Person {
[](#cb115-12)    name: String
[](#cb115-13)}
```

Now we can query the owner’s name for each pet.

```
[](#cb116-1)query petsAndOwners {
[](#cb116-2)    pets {
[](#cb116-3)        name
[](#cb116-4)        owner {
[](#cb116-5)            name
[](#cb116-6)        }
[](#cb116-7)    }
[](#cb116-8)}
```

Our external Pet service only contains a reference to an owner with `ownerId`. To retrieve information such as the owner’s `name`, we have to contact a separate owner service. To model this, add the field `ownerId` to the Pet class.

```
[](#cb117-1)package myservice.service;
[](#cb117-2)
[](#cb117-3)record Pet(String name, String color, String ownerId) {
[](#cb117-4)}
```

Add a class for Person, the type of the owner field:

```
[](#cb118-1)package myservice.service;
[](#cb118-2)
[](#cb118-3)record Person(String name) {
[](#cb118-4)}
```

To fetch the owner information for a given list of pets, we need to implement a new DataFetcher called `owner` that takes a `Pet` as an argument. The argument `Pet` is called the “source object” since it determines the pet we retrieve owner data for.

```
[](#cb119-1)package myservice.service;
[](#cb119-2)
[](#cb119-3)import org.springframework.graphql.data.method.annotation
[](#cb119-4)  .QueryMapping;
[](#cb119-5)import org.springframework.graphql.data.method.annotation
[](#cb119-6)  .SchemaMapping;
[](#cb119-7)import org.springframework.stereotype.Controller;
[](#cb119-8)import org.springframework.web.reactive.function.client
[](#cb119-9)  .WebClient;
[](#cb119-10)import reactor.core.publisher.Flux;
[](#cb119-11)import reactor.core.publisher.Mono;
[](#cb119-12)
[](#cb119-13)@Controller
[](#cb119-14)class PetsController {
[](#cb119-15)
[](#cb119-16)  WebClient petWebClient;
[](#cb119-17)  WebClient ownerWebClient;
[](#cb119-18)
[](#cb119-19)  PetsController(WebClient.Builder builder) {
[](#cb119-20)    this.petWebClient = builder.baseUrl("http://pet-service").build();
[](#cb119-21)    this.ownerWebClient = builder.baseUrl("http://owner-service")
[](#cb119-22)                            .build();
[](#cb119-23)  }
[](#cb119-24)
[](#cb119-25)  @QueryMapping
[](#cb119-26)  Flux<Pet> pets() {
[](#cb119-27)    return petWebClient.get()
[](#cb119-28)      .uri("/pets")
[](#cb119-29)      .retrieve()
[](#cb119-30)      .bodyToFlux(Pet.class);
[](#cb119-31)  }
[](#cb119-32)
[](#cb119-33)  // New
[](#cb119-34)  @SchemaMapping
[](#cb119-35)  Mono<Person> owner(Pet pet) {
[](#cb119-36)    return ownerWebClient.get()
[](#cb119-37)      .uri("/owner/{id}", pet.ownerId())
[](#cb119-38)      .retrieve()
[](#cb119-39)      .bodyToMono(Person.class);
[](#cb119-40)  }
[](#cb119-41)
[](#cb119-42)}
```

The `owner` DataFetcher returns the owner for exactly one pet. We use `bodyToMono` to convert the JSON response to a Java object.

To account for the new Pet schema field `owner`, we added a new property `ownerId` to the `Pet` class. This `ownerId` is used to construct the URL to fetch owner information. Note that the `Pet` class contains an `ownerId` which is not exposed, so a client cannot query it.

Every time we fetch data for a non-root field (such as owner), we use a source object as an argument to identify the parent for returned data from DataFetcher. See the DataFetcher chapter for more on the [source object in Spring for GraphQL](#ch007.xhtml_annotated-methods) and how it is [represented in GraphQL Java](#ch007.xhtml_source-objects-graphql-java).

## GraphQL arguments

Fields can have arguments, which have their type defined in the schema. Arguments can be either optional or required. As discussed in the [Schema chapter](#ch005.xhtml_arguments), an argument is required if it is non-null (indicated with `!`) and there is no default value (declared with `=`).

Let’s introduce a new query field `pet` which takes an argument `id`. The argument is of type `ID`. `ID` is a [built-in scalar type](#ch008.xhtml_scalars) representing a unique identifier. It is marked as non-nullable by adding `!`.

```
[](#cb120-1)type Query {
[](#cb120-2)    pets: [Pet]
[](#cb120-3)    pet(id: ID!): Pet # New field
[](#cb120-4)}
[](#cb120-5)
[](#cb120-6)type Pet {
[](#cb120-7)    id: ID! # New field
[](#cb120-8)    name: String
[](#cb120-9)    color: String
[](#cb120-10)    owner: Person
[](#cb120-11)}
[](#cb120-12)
[](#cb120-13)type Person {
[](#cb120-14)    name: String
[](#cb120-15)}
```

This is how to query the name of a specific pet with the id argument “123”.

```
[](#cb121-1)query myFavoritePet { 
[](#cb121-2)    pet(id: "123") {
[](#cb121-3)        name
[](#cb121-4)    }
[](#cb121-5)}
```

We can conveniently access this GraphQL argument by using Spring for GraphQL’s `@Argument` annotation. See more on [arguments in Spring for GraphQL](#ch007.xhtml_arguments-spring) in the DataFetchers chapter.

Let’s add the id field to the Pet class.

```
[](#cb122-1)package myservice.service;
[](#cb122-2)
[](#cb122-3)record Pet(String id, String name, String color, String ownerId) {
[](#cb122-4)}
```

```
[](#cb123-1)package myservice.service;
[](#cb123-2)
[](#cb123-3)import org.springframework.graphql.data.method.annotation
[](#cb123-4)  .Argument;
[](#cb123-5)import org.springframework.graphql.data.method.annotation
[](#cb123-6)  .QueryMapping;
[](#cb123-7)import org.springframework.graphql.data.method.annotation
[](#cb123-8)  .SchemaMapping;
[](#cb123-9)import org.springframework.stereotype.Controller;
[](#cb123-10)import org.springframework.web.reactive.function.client
[](#cb123-11)  .WebClient;
[](#cb123-12)import reactor.core.publisher.Flux;
[](#cb123-13)import reactor.core.publisher.Mono;
[](#cb123-14)
[](#cb123-15)@Controller
[](#cb123-16)class PetsController {
[](#cb123-17)
[](#cb123-18)  WebClient petWebClient;
[](#cb123-19)  WebClient ownerWebClient;
[](#cb123-20)
[](#cb123-21)  PetsController(WebClient.Builder builder) {
[](#cb123-22)    this.petWebClient = builder.baseUrl("http://pet-service").build();
[](#cb123-23)    this.ownerWebClient = builder.baseUrl("http://owner-service")
[](#cb123-24)                            .build();
[](#cb123-25)  }
[](#cb123-26)
[](#cb123-27)  @QueryMapping
[](#cb123-28)  Flux<Pet> pets() {
[](#cb123-29)    return petWebClient.get()
[](#cb123-30)      .uri("/pets")
[](#cb123-31)      .retrieve()
[](#cb123-32)      .bodyToFlux(Pet.class);
[](#cb123-33)  }
[](#cb123-34)
[](#cb123-35)  @SchemaMapping
[](#cb123-36)  Mono<Person> owner(Pet pet) {
[](#cb123-37)    return ownerWebClient.get()
[](#cb123-38)      .uri("/owner/{id}", pet.ownerId())
[](#cb123-39)      .retrieve()
[](#cb123-40)      .bodyToMono(Person.class);
[](#cb123-41)  }
[](#cb123-42)
[](#cb123-43)  // New
[](#cb123-44)  @QueryMapping
[](#cb123-45)  Mono<Pet> pet(@Argument String id) {
[](#cb123-46)    return petWebClient.get()
[](#cb123-47)      .uri("/pets/{id}", id)
[](#cb123-48)      .retrieve()
[](#cb123-49)      .bodyToMono(Pet.class);
[](#cb123-50)  }
[](#cb123-51)
[](#cb123-52)}
```

As we saw in the [Query Language chapter](#ch006.xhtml_query-language-arguments), an argument can also be an [input object](#ch005.xhtml_input-object).

An input object type describes a group of input fields where each has an input type. In SDL, an input object is declared with the `input` keyword.

Let’s introduce a new query field `petSearch` which takes an input object `PetSearchInput`.

```
[](#cb124-1)type Query {
[](#cb124-2)    pets: [Pet]
[](#cb124-3)    pet(id: ID!): Pet
[](#cb124-4)    petSearch(input: PetSearchInput!): [Pet] # New field
[](#cb124-5)}
[](#cb124-6)
[](#cb124-7)# New input type
[](#cb124-8)input PetSearchInput {
[](#cb124-9)    namePattern: String
[](#cb124-10)    ownerPattern: String
[](#cb124-11)}
[](#cb124-12)
[](#cb124-13)type Pet {
[](#cb124-14)    id: ID!
[](#cb124-15)    name: String
[](#cb124-16)    color: String
[](#cb124-17)    owner: Person
[](#cb124-18)}
[](#cb124-19)
[](#cb124-20)type Person {
[](#cb124-21)    name: String
[](#cb124-22)}
```

Let’s add a Java class `PetSearchInput` to represent the input type in the schema. To access this input object as an argument, we add it as a parameter to the `petSearch` method.

```
[](#cb125-1)package myservice.service;
[](#cb125-2)
[](#cb125-3)record PetSearchInput(String namePattern, String ownerPattern) {
[](#cb125-4)}
```

```
[](#cb126-1)package myservice.service;
[](#cb126-2)
[](#cb126-3)import org.springframework.graphql.data.method.annotation
[](#cb126-4)  .Argument;
[](#cb126-5)import org.springframework.graphql.data.method.annotation
[](#cb126-6)  .QueryMapping;
[](#cb126-7)import org.springframework.graphql.data.method.annotation
[](#cb126-8)  .SchemaMapping;
[](#cb126-9)import org.springframework.stereotype.Controller;
[](#cb126-10)import org.springframework.web.reactive.function.client
[](#cb126-11)  .WebClient;
[](#cb126-12)import reactor.core.publisher.Flux;
[](#cb126-13)import reactor.core.publisher.Mono;
[](#cb126-14)
[](#cb126-15)@Controller
[](#cb126-16)class PetsController {
[](#cb126-17)  WebClient petWebClient;
[](#cb126-18)  WebClient ownerWebClient;
[](#cb126-19)
[](#cb126-20)  PetsController(WebClient.Builder builder) {
[](#cb126-21)    this.petWebClient = builder.baseUrl("http://pet-service").build();
[](#cb126-22)    this.ownerWebClient = builder.baseUrl("http://owner-service")
[](#cb126-23)                            .build();
[](#cb126-24)  }
[](#cb126-25)
[](#cb126-26)  @QueryMapping
[](#cb126-27)  Flux<Pet> pets() {
[](#cb126-28)    return petWebClient.get()
[](#cb126-29)      .uri("/pets")
[](#cb126-30)      .retrieve()
[](#cb126-31)      .bodyToFlux(Pet.class);
[](#cb126-32)  }
[](#cb126-33)
[](#cb126-34)  @SchemaMapping
[](#cb126-35)  Mono<Person> owner(Pet pet) {
[](#cb126-36)    return ownerWebClient.get()
[](#cb126-37)      .uri("/owner/{id}", pet.ownerId())
[](#cb126-38)      .retrieve()
[](#cb126-39)      .bodyToMono(Person.class);
[](#cb126-40)  }
[](#cb126-41)
[](#cb126-42)  @QueryMapping
[](#cb126-43)  Mono<Pet> pet(@Argument String id) {
[](#cb126-44)    return petWebClient.get()
[](#cb126-45)      .uri("/pets/{id}", id)
[](#cb126-46)      .retrieve()
[](#cb126-47)      .bodyToMono(Pet.class);
[](#cb126-48)  }
[](#cb126-49)
[](#cb126-50)  // New
[](#cb126-51)  @QueryMapping
[](#cb126-52)  Flux<Pet> petSearch(@Argument PetSearchInput input) {
[](#cb126-53)    // perform the search
[](#cb126-54)  }
[](#cb126-55)
[](#cb126-56)}
```

## Mutations

As we saw in the Query Language chapter, data is changed in GraphQL with [mutation operations](#ch006.xhtml_mutations). Let’s add a mutation to change a pet’s name.

```
[](#cb127-1)type Query {
[](#cb127-2)    pets: [Pet]
[](#cb127-3)    pet(id: ID!): Pet
[](#cb127-4)    petSearch(input: PetSearchInput!): [Pet]
[](#cb127-5)}
[](#cb127-6)
[](#cb127-7)# New mutation field
[](#cb127-8)type Mutation {
[](#cb127-9)    changePetName(id: ID!, newName: String!): ChangePetNamePayload
[](#cb127-10)}
[](#cb127-11)
[](#cb127-12)# New type
[](#cb127-13)type ChangePetNamePayload {
[](#cb127-14)    pet: Pet
[](#cb127-15)}
[](#cb127-16)
[](#cb127-17)input PetSearchInput {
[](#cb127-18)    namePattern: String
[](#cb127-19)    ownerPattern: String
[](#cb127-20)}
[](#cb127-21)
[](#cb127-22)type Pet {
[](#cb127-23)    id: ID!
[](#cb127-24)    name: String
[](#cb127-25)    color: String
[](#cb127-26)    owner: Person
[](#cb127-27)}
[](#cb127-28)
[](#cb127-29)type Person {
[](#cb127-30)    name: String
[](#cb127-31)}
```

The return type for the mutation field ends with `Payload` to follow a quasi-standard naming [convention](#ch012.xhtml_mutation-format) for mutation response types.

This is a mutation request to change the name of the pet with the id “123” to “Mixie”.

```
[](#cb128-1)mutation changeName { 
[](#cb128-2)    changePetName(id: "123", newName: "Mixie") {
[](#cb128-3)        pet {
[](#cb128-4)            name
[](#cb128-5)        }
[](#cb128-6)    }
[](#cb128-7)}
```

Let’s add the mutation payload class.

```
[](#cb129-1)package myservice.service;
[](#cb129-2)
[](#cb129-3)record ChangePetNamePayload(Pet pet) {
[](#cb129-4)}
```

Implement the mutation DataFetcher with the shortcut `@MutationMapping` annotation.

```
[](#cb130-1)package myservice.service;
[](#cb130-2)
[](#cb130-3)import org.springframework.graphql.data.method.annotation
[](#cb130-4)  .Argument;
[](#cb130-5)import org.springframework.graphql.data.method.annotation
[](#cb130-6)  .MutationMapping;
[](#cb130-7)import org.springframework.graphql.data.method.annotation
[](#cb130-8)  .QueryMapping;
[](#cb130-9)import org.springframework.graphql.data.method.annotation
[](#cb130-10)  .SchemaMapping;
[](#cb130-11)import org.springframework.http.MediaType;
[](#cb130-12)import org.springframework.stereotype.Controller;
[](#cb130-13)import org.springframework.web.reactive.function
[](#cb130-14)  .BodyInserters;
[](#cb130-15)import org.springframework.web.reactive.function.client
[](#cb130-16)  .WebClient;
[](#cb130-17)import reactor.core.publisher.Flux;
[](#cb130-18)import reactor.core.publisher.Mono;
[](#cb130-19)
[](#cb130-20)import java.util.Map;
[](#cb130-21)
[](#cb130-22)@Controller
[](#cb130-23)class PetsController {
[](#cb130-24)
[](#cb130-25)  WebClient petWebClient;
[](#cb130-26)  WebClient ownerWebClient;
[](#cb130-27)
[](#cb130-28)  PetsController(WebClient.Builder builder) {
[](#cb130-29)    this.petWebClient = builder.baseUrl("http://pet-service").build();
[](#cb130-30)    this.ownerWebClient = builder.baseUrl("http://owner-service")
[](#cb130-31)                              .build();
[](#cb130-32)  }
[](#cb130-33)
[](#cb130-34)  @QueryMapping
[](#cb130-35)  Flux<Pet> pets() {
[](#cb130-36)    return petWebClient.get()
[](#cb130-37)      .uri("/pets")
[](#cb130-38)      .retrieve()
[](#cb130-39)      .bodyToFlux(Pet.class);
[](#cb130-40)  }
[](#cb130-41)
[](#cb130-42)  @SchemaMapping
[](#cb130-43)  Mono<Person> owner(Pet pet) {
[](#cb130-44)    return ownerWebClient.get()
[](#cb130-45)      .uri("/owner/{id}", pet.ownerId())
[](#cb130-46)      .retrieve()
[](#cb130-47)      .bodyToMono(Person.class);
[](#cb130-48)  }
[](#cb130-49)
[](#cb130-50)  @QueryMapping
[](#cb130-51)  Mono<Pet> pet(@Argument String id) {
[](#cb130-52)    return petWebClient.get()
[](#cb130-53)      .uri("/pets/{id}", id)
[](#cb130-54)      .retrieve()
[](#cb130-55)      .bodyToMono(Pet.class);
[](#cb130-56)  }
[](#cb130-57)
[](#cb130-58)  @QueryMapping
[](#cb130-59)  Flux<Pet> petSearch(@Argument PetSearchInput input) {
[](#cb130-60)    // perform the search
[](#cb130-61)  }
[](#cb130-62)
[](#cb130-63)  // New
[](#cb130-64)  @MutationMapping
[](#cb130-65)  Mono<ChangePetNamePayload> changePetName(
[](#cb130-66)    @Argument String id,
[](#cb130-67)    @Argument String newName
[](#cb130-68)  ) {
[](#cb130-69)    Map<String, String> changeNameBody = Map.of(
[](#cb130-70)      "name", newName
[](#cb130-71)    );
[](#cb130-72)    return petWebClient.put()
[](#cb130-73)      .uri("/pets/{id}", id)
[](#cb130-74)      .contentType(MediaType.APPLICATION_JSON)
[](#cb130-75)      .body(BodyInserters.fromValue(changeNameBody))
[](#cb130-76)      .retrieve()
[](#cb130-77)      .bodyToMono(ChangePetNamePayload.class);
[](#cb130-78)  }
[](#cb130-79)
[](#cb130-80)}
```

In our `changePetName` method, we update the name of a pet with an HTTP PUT request. The response from the HTTP PUT contains the newly modified pet’s details.

A mutation controller method can have [any of the method arguments](#ch007.xhtml_spring-datafetcher-inputs) available to schema mapping handler methods. See the DataFetchers chapter for a list of method arguments. In this case, the `changePetName` method takes the two parameters `id` and `newName`, representing arguments of the mutation field.

## Unions, interfaces, and TypeResolver

To demonstrate unions and interfaces, we will use a simpler example to demonstrate how Spring for GraphQL’s default `TypeResolver` works. If you would like to use this Pet interface in combination with the earlier examples of this chapter, we’ll leave the task of deserializing data up to you, as deserialization depends on the data source you choose.

There are many kinds of pets in the world, each with slightly different attributes. It would be better to represent Pet as an [interface](#ch005.xhtml_interface) in our schema. Let’s add two Pet implementations, Dog and Cat. You can add your favourite Pet implementation too.

To demonstrate [unions](#ch005.xhtml_union), we’ll also add a `Creature` union, and a new query field for `creatures`.

```
[](#cb131-1)type Query {
[](#cb131-2)    creatures: [Creature] # New
[](#cb131-3)}
[](#cb131-4)
[](#cb131-5)# Changed from type to interface
[](#cb131-6)interface Pet {
[](#cb131-7)    id: ID!
[](#cb131-8)    name: String
[](#cb131-9)    color: String
[](#cb131-10)}
[](#cb131-11)
[](#cb131-12)# New implementation of Pet
[](#cb131-13)type Dog implements Pet {
[](#cb131-14)    id: ID!
[](#cb131-15)    name: String
[](#cb131-16)    color: String
[](#cb131-17)    barks: Boolean
[](#cb131-18)}
[](#cb131-19)
[](#cb131-20)# New implementation of Pet
[](#cb131-21)type Cat implements Pet {
[](#cb131-22)    id: ID!
[](#cb131-23)    name: String
[](#cb131-24)    color: String
[](#cb131-25)    meows: Boolean
[](#cb131-26)}
[](#cb131-27)
[](#cb131-28)# New
[](#cb131-29)type Human {
[](#cb131-30)    name: String
[](#cb131-31)}
[](#cb131-32)
[](#cb131-33)# New
[](#cb131-34)union Creature = Dog | Cat | Human
```

Note that the GraphQL spec requires that unions only contain object types. We must specify the object types `Dog` and `Cat`, we cannot specify the interface `Pet`.

Let’s mirror these changes in our Java model. Let’s represent Pet as an interface.

```
[](#cb132-1)package myservice.service;
[](#cb132-2)
[](#cb132-3)interface Pet {
[](#cb132-4)  String id();
[](#cb132-5)  String name();
[](#cb132-6)  String color();
[](#cb132-7)}
```

And create two new classes, Dog and Cat, which implement the Pet interface.

```
[](#cb133-1)package myservice.service;
[](#cb133-2)
[](#cb133-3)record Dog(String id,
[](#cb133-4)           String name,
[](#cb133-5)           String color,
[](#cb133-6)           boolean barks) implements Pet {
[](#cb133-7)}
```

```
[](#cb134-1)package myservice.service;
[](#cb134-2)
[](#cb134-3)record Cat(String id,
[](#cb134-4)           String name,
[](#cb134-5)           String color,
[](#cb134-6)           boolean meows) implements Pet {
[](#cb134-7)}
```

Let’s create a new Human class.

```
[](#cb135-1)package myservice.service;
[](#cb135-2)
[](#cb135-3)record Human(String name) {
[](#cb135-4)}
```

Let’s register a DataFetcher for the new `creatures` query field. Note that the incoming data must be converted into the correct Java class representation. This will depend on the implementation of the remote service. For example, the service may return a field for each Creature to indicate its type.

In the example below we have included an in-memory list, so you can verify this union works before setting up how to request from the remote service and how to deserialize data.

```
[](#cb136-1)package myservice.service;
[](#cb136-2)
[](#cb136-3)import org.springframework.graphql.data.method.annotation
[](#cb136-4)  .QueryMapping;
[](#cb136-5)import org.springframework.stereotype.Controller;
[](#cb136-6)import reactor.core.publisher.Flux;
[](#cb136-7)
[](#cb136-8)@Controller
[](#cb136-9)class PetsController {
[](#cb136-10)
[](#cb136-11)  @QueryMapping
[](#cb136-12)  Flux<Object> creatures() {
[](#cb136-13)    // Add your fetching logic
[](#cb136-14)
[](#cb136-15)    // In-memory example
[](#cb136-16)    return Flux.just(
[](#cb136-17)      new Dog("Dog01", "Spot", "Yellow", true),
[](#cb136-18)      new Cat("Cat01", "Chicken", "Orange", true),
[](#cb136-19)      new Human("Donna"));
[](#cb136-20)
[](#cb136-21)  }
[](#cb136-22)
[](#cb136-23)}
```

Try out the query below with the GraphiQL interactive playground at `http://localhost:8080/graphiql`. To enable GraphiQL, please add the following to your `application.properties` file.

```
spring.graphql.graphiql.enabled=true
```

```
[](#cb138-1)query allTheThings {
[](#cb138-2)    creatures {
[](#cb138-3)        ...on Dog {
[](#cb138-4)            name
[](#cb138-5)            barks
[](#cb138-6)        }
[](#cb138-7)        ... on Cat {
[](#cb138-8)            name
[](#cb138-9)            meows
[](#cb138-10)        }
[](#cb138-11)        ... on Human {
[](#cb138-12)            name
[](#cb138-13)        }
[](#cb138-14)    }
[](#cb138-15)}
```

If a field type is an [interface](#ch005.xhtml_interface) or [union](#ch005.xhtml_union), GraphQL Java needs to determine the actual object type of the value via a [TypeResolver](#ch007.xhtml_typeresolver-spring).

In this service, we will make use of Spring for GraphQL’s default `ClassNameTypeResolver`, which tries to match the simple class name of the value to a `GraphQLObjectType`. If it cannot find a match, it will continue searching through super types, including base classes and interfaces. The default `ClassNameTypeResolver` is sufficient because in our service, the Java model maps 1:1 with the API. If your model doesn’t exactly match your API, see the [TypeResolver section](#ch007.xhtml_typeresolver-spring) in the DataFetchers chapter for how to register a custom `TypeResolver`.

The default `ClassNameTypeResolver` is registered when the Spring Boot starter initializes `graphql.GraphQL`, and therefore no further configuration is required for our service. We do not need to manually write a TypeResolver for either the `Pet` interface nor the `Creature` union.

In this chapter, you built a more substantial Spring for GraphQL application making use of concepts we have discussed in previous chapters.

If you haven’t already, enable the GraphiQL interactive playground by adding this to your `application.properties` file.

```
spring.graphql.graphiql.enabled=true
```

Start your service and navigate to the GraphiQL interactive playground at `http://localhost:8080/graphiql`. Try out various queries and mutations and verify your code is working end to end.

In the chapters that follow, we will discuss more specialized topics such as schema design and GraphQL errors. Later in the book, we will cover more advanced topics including a deep dive into [execution](#ch015.xhtml_execution-chapter) inside the GraphQL Java engine.

# Subscriptions

There are three types of operations supported by GraphQL: queries, mutations, and subscriptions. In this chapter we’ll expand on the subscription operation. While queries and mutations are similar in many respects, subscriptions are quite different.

A subscription is a long-lived request, where clients want to be informed about certain events on the server side. A subscription can be active for minutes or hours, whereas a query or mutation is active for a few milliseconds to a few seconds at most. With a subscription, the clients will get updates from the server for every relevant change, meaning that there is a “stream” of data, rather than a single response.

Let’s walk through an example of an online store. The client wants to be notified each time someone creates a new order, when it happened, and by whom. The subscription operation would look like this:

```
[](#cb140-1)subscription myOrders {
[](#cb140-2)    newOrderCreated {
[](#cb140-3)        id
[](#cb140-4)        createdTime
[](#cb140-5)        customer {
[](#cb140-6)            name
[](#cb140-7)        }
[](#cb140-8)    }
[](#cb140-9)}
```

First, the client requests a `newOrderCreated` subscription and then receives the first response 10 seconds later.

```
[](#cb141-1){
[](#cb141-2)  "newOrderCreated": {
[](#cb141-3)    "id": "123",
[](#cb141-4)    "createdTime": "2015-07-06T04:11:11.000Z",
[](#cb141-5)    "customer": {
[](#cb141-6)      "name": "Andi"
[](#cb141-7)    }
[](#cb141-8)  }
[](#cb141-9)}
```

Then another response after 2 more seconds. And so on.

```
[](#cb142-1){
[](#cb142-2)  "newOrderCreated": {
[](#cb142-3)    "id": "124",
[](#cb142-4)    "createdTime": "2015-07-06T04:11:13.000Z",
[](#cb142-5)    "customer": {
[](#cb142-6)      "name": "Elli"
[](#cb142-7)    }
[](#cb142-8)  }
[](#cb142-9)}
```

Note how there are multiple responses for the single subscription request. This differs from queries and mutations, where one request corresponds to exactly one response.

Protocol-wise, subscriptions also need a different solution, because HTTP was not designed for data to be sent from the server to the client via a long-lived connection. Most commonly, WebSockets are used as the protocol for subscriptions. Spring for GraphQL supports the WebSocket protocol out of the box.

## Getting started

Let’s implement subscriptions with Spring for GraphQL.

Start with a new Spring for GraphQL project with Spring Initializr at https://start.spring.io/, as we did in the “Your first Spring for GraphQL service” section of the [Introduction chapter](#ch003.xhtml_first-spring-service). Choose Spring for GraphQL as a dependency, and choose either Spring Web or Spring Reactive Web as a dependency. In the following examples we will use Spring Reactive Web, which includes Spring WebFlux. If you prefer to use subscriptions with WebMVC instead of WebFlux, add `org.springframework.boot:spring-boot-starter-websocket` as a dependency, and adjust the examples by removing `Mono` and `Flux`.

Let’s add a subscription field to a new schema.

```
[](#cb143-1)# Every schema needs a Query type
[](#cb143-2)type Query {
[](#cb143-3)    notUsed: String
[](#cb143-4)}
[](#cb143-5)
[](#cb143-6)type Subscription {
[](#cb143-7)    hello: String
[](#cb143-8)}
```

In the controller, add an annotated method `hello`. This method is annotated with `@SubscriptionMapping`, which registers this DataFetcher to the subscription field `hello` in the schema.

```
[](#cb144-1)package myservice.service;
[](#cb144-2)
[](#cb144-3)import org.springframework.graphql.data.method.annotation
[](#cb144-4)  .SubscriptionMapping;
[](#cb144-5)import org.springframework.stereotype.Controller;
[](#cb144-6)import reactor.core.publisher.Flux;
[](#cb144-7)
[](#cb144-8)import java.time.Duration;
[](#cb144-9)import java.util.List;
[](#cb144-10)
[](#cb144-11)@Controller
[](#cb144-12)class HelloController {
[](#cb144-13)
[](#cb144-14)  @SubscriptionMapping
[](#cb144-15)  Flux<String> hello() {
[](#cb144-16)    Flux<Integer> interval = Flux.fromIterable(List.of(0, 1, 2))
[](#cb144-17)      .delayElements(Duration.ofSeconds(1));
[](#cb144-18)    return interval.map(integer -> "Hello " + integer);
[](#cb144-19)  }
[](#cb144-20)
[](#cb144-21)}
```

As the results of subscriptions are streams of data, `Flux` from Reactor is a perfect abstraction. In our example, we emit data three times: “Hello 1”, “Hello 2” and “Hello 3”, each with a one-second delay.

In order to enable subscriptions, we have to add a new Spring configuration property, setting the path where we want to expose our subscription.

```
spring.graphql.websocket.path=/graphql
```

Let’s also enable the GraphiQL playground for manual testing.

```
spring.graphql.graphiql.enabled=true
```

Let’s test our subscription. Start the service and open the GraphiQL playground at `http://localhost:8080/graphiql`.

In the playground, execute a new subscription. Click the play button to execute, and you should see a response as in the screenshot “Subscription request”.

```
[](#cb147-1)subscription myFirstSubscription {
[](#cb147-2)    hello
[](#cb147-3)}
```

![Subscription request](media/file12.png)

Subscription request

Then we will see the response changing every second, from “Hello 0” to “Hello 1” to “Hello 2”, as shown in the screenshot “Hello 2 answer”.

![Hello 2 answer](media/file13.png)

Hello 2 answer

We have a working subscription. Congratulations!

If you instead saw this “isTrusted” error message, this is a generic message.

```
[](#cb148-1){
[](#cb148-2)  "errors": [
[](#cb148-3)    {
[](#cb148-4)      "isTrusted": true
[](#cb148-5)    }
[](#cb148-6)  ]
[](#cb148-7)}
```

Please double-check that you have enabled the WebSocket path in your configuration file.

```
spring.graphql.websocket.path=/graphql
```

## Execution

Similarly to queries and mutations, we implement subscriptions as DataFetchers. In order to deliver a stream of responses, GraphQL Java requires that it return a `org.reactivestreams.Publisher` instance. The [Reactive Streams](https://www.reactive-streams.org/) initiative defines this interface to provide a standard for asynchronous stream processing.

When using GraphQL Java with Spring, we use `Flux` from Project Reactor, which implements `Publisher`. We used `Flux` in the example earlier in this chapter.

Spring for GraphQL takes care of bridging the transport layer WebSocket protocol to this `Publisher`. Every time it emits a new result, we send it to the client.

The GraphQL specification requires a subscription request always has **exactly one root field**, unlike queries and mutations. For example, the subscription below is invalid because it has multiple roots.

```
[](#cb150-1)# Not valid
[](#cb150-2)subscription tooManyRoots {
[](#cb150-3)    newCats {
[](#cb150-4)        name
[](#cb150-5)    }
[](#cb150-6)    newDogs {
[](#cb150-7)        name
[](#cb150-8)    }
[](#cb150-9)}
```

Additionally, we can only subscribe to one subscription per request.

We execute all sub-selections below the root field, as we would for a query or mutation. Let’s return to our orders example from earlier in the chapter.

```
[](#cb151-1)subscription myOrders {
[](#cb151-2)    newOrderCreated {
[](#cb151-3)        id
[](#cb151-4)        createdTime
[](#cb151-5)        customer {
[](#cb151-6)            name
[](#cb151-7)        }
[](#cb151-8)    }
[](#cb151-9)}
```

The DataFetcher for `newOrderCreated` returns a `Publisher`. Every new event emitted from it starts a normal query execution for the sub-selection with the event payload as source object.

Let’s walk through subscription execution step by step:

We receive a new subscription request from a client, which is executed by calling the DataFetcher for `newOrderCreated`, that returns a `Publisher`.

When that `Publisher` emits a new event, we execute the sub-selection `{ id createdTime customer }` with the event payload as a source object. All of this happens exactly the same way as described in the [fetching data](#ch015.xhtml_fetching-data) section of the Execution chapter: we invoke all three DataFetchers for `id`, `createdTime`, and `customer` and complete the returned values. If `customer` returns a non-null value, we invoke the DataFetcher for `name`.

We send the result back to the client. When the `Publisher` emits a new event, the execution starts again, and we send a new result to the client.

Once the `Publisher` signals that it has finished, the whole request finishes.

It’s important to note that the data emitted by the `Publisher` is not the actual data sent to the client, but only used as input for the sub-selection, which follows the same GraphQL execution rules as queries and mutations.

## Protocol

Subscriptions require a way for the server to inform the client about new events. The protocol that comes closest to a standard for subscriptions is a WebSocket-based protocol: [graphql-ws](https://github.com/enisdenjo/graphql-ws). Spring for GraphQL supports this protocol out of the box.

This protocol enables any kind of GraphQL requests to be executed with it, but in practice it is used primarily for subscription requests because the WebSocket protocol is more complicated than HTTP.

To activate the WebSocket path, set the path via the `spring.graphql.websocket.path` configuration property.

```
spring.graphql.websocket.path=/graphql-subscriptions
```

The GraphiQL playground separates HTTP and WebSocket URLs, so we can set two different endpoints when we open GraphiQL.

```
http://localhost:8080/graphiql?path=/graphql&wsPath=/graphql-subscriptions
```

Spring for GraphQL handles the URLs for us automatically. When we open `http://localhost:8080/graphiql`, we get redirected automatically to a URL with the correct parameters depending on our configuration.

It is also possible to offer both the WebSocket protocol and normal HTTP protocol via the same URL, as we did in our example earlier in the chapter.

## Client support

We can use the graphql-ws protocol with a variety of different clients. However, as some clients might not support graphql-ws by default, additional setup might be required. The [graphql-ws GitHub repo](https://github.com/enisdenjo/graphql-ws#recipes) contains a list of recipes for different clients.

In this chapter we discussed GraphQL subscriptions. Later in the [Testing chapter](#ch018.xhtml_subscription-testing), we’ll discuss how to test subscriptions.

# Request and response

In this chapter, we will take a closer look at requests and responses for GraphQL, including the HTTP protocol.

## Transport protocols and serialization

It might surprise you that the GraphQL spec does not specify any transport protocol for how a client communicates with a server. Although it was a deliberate decision to exclude transport concerns from the spec, in practice HTTP has become the most commonly used protocol. The community agrees on the HTTP spec outlined in [Serving over HTTP best practices](https://graphql.org/learn/serving-over-http) on http://graphql.org, which serves as a quasi-standard. There is a proposal for a [GraphQL over HTTP specification](https://github.com/graphql/graphql-over-http), but it is not yet official at the time of writing.

Transport protocols are handled at the Spring for GraphQL level. GraphQL Java does not dictate any transport protocol.

JSON is the most common serialization choice. Although the GraphQL spec does not dictate any particular serialization format, given the sheer popularity of JSON, the spec includes a section on JSON serialization.

## Request

The most important elements of a GraphQL request are the query, operation name, and variables. Every GraphQL request over HTTP is a POST encoded as `application/json`, with the body being a JSON object:

```
[](#cb154-1){
[](#cb154-2)  "query": "<document>",
[](#cb154-3)  "variables": {
[](#cb154-4)    <variables>
[](#cb154-5)  },
[](#cb154-6)  "operationName": "<operationName>"
[](#cb154-7)}
```

The goal is to execute exactly one GraphQL operation. The HTTP endpoint is always the same, often ending with `/graphql` by convention.

In the request body, the first key “query” is actually a GraphQL *document*, rather than a GraphQL *query*. A GraphQL document can contain one or many operations, and is represented in the request as a JSON string. This key is not optional.

The next key “variables” is a JSON map with all the variables for the operation. This key is optional, as operation variables are optional.

The third key “operationName” specifies which operation to execute in the document. This is optional and only required when there are multiple operations in the document.

Under the hood, the transport protocol is handled by Spring for GraphQL. An HTTP request in Spring for GraphQL is represented by a `WebGraphQlRequest` containing HTTP-specific information such as headers.

And at the GraphQL Java level, a GraphQL request is represented by a `graphql.ExecutionInput` instance. Here are the most important fields:

```
[](#cb155-1)public class ExecutionInput {
[](#cb155-2)  private final String query;
[](#cb155-3)  private final String operationName;
[](#cb155-4)  private final RawVariables rawVariables;
[](#cb155-5)  // and more fields
[](#cb155-6)}
```

`query` represents the “query” key in the JSON object, and `operationName` represents the “operationName” key. `rawVariables` represents the variables map in the JSON object. The word raw reflects that the variables have not yet been coerced. We’ll discuss [variable coercion](#ch015.xhtml_coercing-variables) in the Execution chapter.

Note that transport concerns are managed at the Spring for GraphQL level. GraphQL Java’s `ExecutionInput` does not specify any transport protocol. The most important fields in this class correspond to the JSON object in the request body we saw previously.

## Response

Over HTTP, the response to a GraphQL request is a JSON object:

```
[](#cb156-1){
[](#cb156-2)  "data": <data>,
[](#cb156-3)  "errors": <list of GraphQL errors>,
[](#cb156-4)  "extensions": <map of extensions>
[](#cb156-5)}
```

If the data key is not present, the errors key must be present to explain why no data was returned. If the data key is present, the errors key can be present too, in the case where partial results are returned. Note that `null` is a valid value for data.

The extensions key is optional. The value is a map and there are no restrictions on its contents.

Under the hood in GraphQL Java, the response is represented as `graphql.ExecutionResult`, which mirrors the JSON response.

```
[](#cb157-1)public interface ExecutionResult {
[](#cb157-2)  <T> T getData();
[](#cb157-3)  List<GraphQLError> getErrors();
[](#cb157-4)  Map<Object, Object> getExtensions();
[](#cb157-5)  // and more methods
[](#cb157-6)}
```

We will discuss [GraphQL errors](#ch011.xhtml_graphql-errors) in greater detail in the next chapter.

## HTTP status codes

The response’s HTTP status code depends on whether the GraphQL Java engine was invoked.

If the request is rejected before the GraphQL Java engine is invoked, we use HTTP status codes to indicate the problem. For example, a `401 Unauthorized` code is returned for authentication failures, or `400 Bad Request` if the request itself is not a GraphQL request (e.g. the body is missing a “query” key).

If the request is rejected after the GraphQL Java engine is invoked, the `200 OK` status code is always returned. Any errors are represented as GraphQL errors in the JSON response body.

Why would we return a `200 OK` code even when there are errors in the response? The reason for this model is to enable more flexible requests and partial responses compared to a REST API. For example, a partial response is still valuable, so it is returned with a `200 OK` status code, and errors in the response to explain why part of the data could not be retrieved.

The challenge with this model is that analyzing the response now requires two steps:

1.  Check the HTTP status code
2.  If the status code is `200 OK`, check for any GraphQL errors in the response

This is a gotcha for developers with REST API experience. To determine whether a request succeeded, remember to check both the HTTP status code *and* the errors key of a response.

## HTTP headers

We strongly recommend that information needed to understand the request should be part of the GraphQL operation, and not passed in via request headers.

This general rule comes from the intention to express the API completely in the GraphQL schema. Let’s demonstrate this via a counterexample, where an HTTP header “Customer-Id” is sent alongside a query for the field `ordersByCustomerId`. In the schema, the field is defined as:

```
[](#cb158-1)type Query {
[](#cb158-2)    ordersByCustomerId: [Order]
[](#cb158-3)}
```

Imagine you are reading the schema for the first time, wanting to understand the API. There is no information to indicate that a “Customer-Id” header is essential for the `ordersByCustomerId` field. The schema becomes an incomplete description of the API.

We must have the customer ID to make sense of the request. It is much better to explicitly require the customer ID as an argument in the query request.

```
[](#cb159-1)type Query {
[](#cb159-2)    ordersByCustomerId(id: ID!): [Order]
[](#cb159-3)}
```

A person reading this improved schema would easily understand that there must be an `id` argument provided to fulfil the request. As the `id` argument is non-nullable, GraphQL validation and tooling will also require the argument be provided to proceed with the request.

We recommend sending information needed to understand the request in the GraphQL operation. However, that doesn’t mean request headers can’t be used at all. You should continue to use request headers to send meta or auxiliary data, which is not necessary to understand the GraphQL request.

One prominent example is sending authentication information. Although authentication is required to execute the request, we can understand the intent of the request without seeing credentials.

Another example is sending beta flags via request headers. If the client wants to use certain fields that are not yet stable, we could require some special header such as “beta-features”. With or without this beta flag information, the request on its own make sense.

A third example is tracing information such as request IDs. Metadata like request IDs are useful for logging but are not essential to understand the GraphQL request.

## Intercepting requests

Spring for GraphQL provides `WebGraphQlInterceptor` to intercept requests.

Spring for GraphQL automatically handles the HTTP protocol, including the invocation of GraphQL Java which actually executes the request. The default URL is `/graphql`, which we can customize via the config property `spring.graphql.path`.

`WebGraphQlRequest` and `WebGraphQlResponse` represent the GraphQL request and response over either HTTP or WebSocket. It contains GraphQL-specific information as well as HTTP or WebSocket details.

We can access and change the request with `WebGraphQlInterceptor`. For example, we can intercept a request and add a “special-header” to the response headers.

```
[](#cb160-1)package myservice.service;
[](#cb160-2)
[](#cb160-3)import org.springframework.graphql.server.WebGraphQlInterceptor;
[](#cb160-4)import org.springframework.graphql.server.WebGraphQlRequest;
[](#cb160-5)import org.springframework.graphql.server.WebGraphQlResponse;
[](#cb160-6)import org.springframework.stereotype.Component;
[](#cb160-7)import reactor.core.publisher.Mono;
[](#cb160-8)
[](#cb160-9)@Component
[](#cb160-10)class MyInterceptor implements WebGraphQlInterceptor {
[](#cb160-11)
[](#cb160-12)  @Override
[](#cb160-13)  public Mono<WebGraphQlResponse> intercept(
[](#cb160-14)    WebGraphQlRequest request, Chain chain
[](#cb160-15)  ) {
[](#cb160-16)    return chain.next(request)
[](#cb160-17)      .map(response -> {
[](#cb160-18)        response.getResponseHeaders().add("special-header", "true");
[](#cb160-19)        return response;
[](#cb160-20)      });
[](#cb160-21)  }
[](#cb160-22)}
```

Another use case is to change execution based on a request header. In this example, clients are required to send a special beta flag “beta-features” to request beta fields which are not yet stable. In the interceptor, if this “beta-features” header is present, we add “beta-features” to the `GraphQLContext` so this information can be accessed later in the execution. We’ll cover [GraphQLContext](#ch013.xhtml_global-context) in more detail in the DataFetchers in depth chapter.

```
[](#cb161-1)package myservice.service;
[](#cb161-2)
[](#cb161-3)import org.springframework.graphql.server.WebGraphQlInterceptor;
[](#cb161-4)import org.springframework.graphql.server.WebGraphQlRequest;
[](#cb161-5)import org.springframework.graphql.server.WebGraphQlResponse;
[](#cb161-6)import org.springframework.stereotype.Component;
[](#cb161-7)import reactor.core.publisher.Mono;
[](#cb161-8)
[](#cb161-9)@Component
[](#cb161-10)class BetaFeaturesInterceptor implements WebGraphQlInterceptor {
[](#cb161-11)
[](#cb161-12)  @Override
[](#cb161-13)  public Mono<WebGraphQlResponse> intercept(
[](#cb161-14)    WebGraphQlRequest request, Chain chain
[](#cb161-15)  ) {
[](#cb161-16)    boolean betaFeatures = request
[](#cb161-17)      .getHeaders()
[](#cb161-18)      .containsKey("beta-features");
[](#cb161-19)
[](#cb161-20)    request.configureExecutionInput((executionInput, builder) -> {
[](#cb161-21)      executionInput
[](#cb161-22)        .getGraphQLContext()
[](#cb161-23)        .put("beta-features", betaFeatures);
[](#cb161-24)      return executionInput;
[](#cb161-25)    });
[](#cb161-26)
[](#cb161-27)    return chain.next(request);
[](#cb161-28)  }
[](#cb161-29) 
[](#cb161-30)}
```

The example above changed the GraphQL Java request object `ExecutionInput`. We can also access and change the entire GraphQL Java response `ExecutionResult`. In the `intercept` method, return your customized `WebGraphQLResponse`.

For example, if you already attach a request ID to incoming requests, it is useful to add the request ID to the extensions section of the GraphQL response. This is very helpful for debugging issues, as the person using your API can give you a request ID to quickly find relevant logs.

This is how to append an extra key to the extensions of the response:

```
[](#cb162-1)package myservice.service;
[](#cb162-2)
[](#cb162-3)import graphql.ExecutionResult;
[](#cb162-4)import org.springframework.graphql.server.WebGraphQlInterceptor;
[](#cb162-5)import org.springframework.graphql.server.WebGraphQlRequest;
[](#cb162-6)import org.springframework.graphql.server.WebGraphQlResponse;
[](#cb162-7)import org.springframework.stereotype.Component;
[](#cb162-8)import reactor.core.publisher.Mono;
[](#cb162-9)
[](#cb162-10)import java.util.HashMap;
[](#cb162-11)import java.util.Map;
[](#cb162-12)
[](#cb162-13)@Component
[](#cb162-14)class ChangeResponse implements WebGraphQlInterceptor {
[](#cb162-15)
[](#cb162-16)  @Override
[](#cb162-17)  public Mono<WebGraphQlResponse> intercept(
[](#cb162-18)    WebGraphQlRequest request,
[](#cb162-19)    Chain chain
[](#cb162-20)  ) {
[](#cb162-21)    return chain.next(request)
[](#cb162-22)      .map(response -> {
[](#cb162-23)        // response is a WebGraphQLResponse containing 
[](#cb162-24)        // the ExecutionResult
[](#cb162-25)        ExecutionResult executionResult = response.getExecutionResult();
[](#cb162-26)        Map<Object, Object> newExtensions = new HashMap<>();
[](#cb162-27)        if (executionResult.getExtensions() != null) {
[](#cb162-28)          newExtensions.putAll(executionResult.getExtensions());
[](#cb162-29)        }
[](#cb162-30)        // Replace value with your request ID mechanism
[](#cb162-31)        newExtensions.put("request_id", "YOUR_REQUEST_ID_HERE");
[](#cb162-32)
[](#cb162-33)        return response.transform(builder ->
[](#cb162-34)          builder.extensions(newExtensions).build()
[](#cb162-35)        );
[](#cb162-36)      });
[](#cb162-37)  }
[](#cb162-38)
[](#cb162-39)}
```

In this chapter we discussed requests and responses for GraphQL in greater detail, and demonstrated how to access these objects in Spring for GraphQL.

In the next chapter, we’re going to build on these concepts and discuss GraphQL errors.

# GraphQL errors

What happens when things go wrong? How do we communicate errors from our GraphQL service?

In the previous chapter we started discussing GraphQL responses, which are JSON objects with three key entries: data, errors, and extensions.

```
[](#cb163-1){
[](#cb163-2)  "data": <data>,
[](#cb163-3)  "errors": <list of GraphQL errors>,
[](#cb163-4)  "extensions": <map of extensions>
[](#cb163-5)}
```

In this chapter we’ll discuss GraphQL errors in detail. We will discuss how errors are presented to the client and how to customise GraphQL errors in our Spring for GraphQL service.

There are broadly two kinds of GraphQL errors: request errors and field errors. We’ll walk through how GraphQL errors are presented with examples.

## Request errors

A request error is raised during a request. The GraphQL response will contain an errors key, but no data key. For example, a request error will be raised if a request contains a GraphQL syntax error, such as a missing closing curly brace `}`.

Request errors are raised before execution begins. In other words, request errors are raised before any DataFetchers are invoked. A request error is usually the fault of the requesting client.

Some [examples of request errors](https://spec.graphql.org/draft/#sec-Errors.Request-Errors) from the GraphQL spec are:

*   parsing errors, including GraphQL syntax errors
*   validation errors in the [GraphQL document](#ch006.xhtml_graphql-document), which typically indicates that the request is not compliant with the GraphQL spec
*   unable to determine which operation to execute
*   invalid input values for variables

For example, this request is invalid GraphQL syntax:

```
[](#cb164-1)query invalid {
[](#cb164-2)    {
[](#cb164-3)        foo
[](#cb164-4)    }
[](#cb164-5)}
```

The response contains an error, including a message indicating what went wrong:

```
[](#cb165-1){
[](#cb165-2)  "errors": [
[](#cb165-3)    {
[](#cb165-4)      "message": "Invalid Syntax : offending token '{' 
[](#cb165-5) at line 2 column 5",
[](#cb165-6)      "locations": [
[](#cb165-7)        {
[](#cb165-8)          "line": 2,
[](#cb165-9)          "column": 5
[](#cb165-10)        }
[](#cb165-11)      ],
[](#cb165-12)      "extensions": {
[](#cb165-13)        "classification": "InvalidSyntax"
[](#cb165-14)      }
[](#cb165-15)    }
[](#cb165-16)  ]
[](#cb165-17)}
```

Every error must contain the key `message`, with a description of the error. In this case, the message indicates the request contained invalid GraphQL syntax. If the error can be linked to a `location` in the GraphQL document, it should be presented to make the error easier to find. The location information indicates the invalid syntax is at line 2 and column 5 of the GraphQL document.

The GraphQL spec also allows for an optional key `extensions`, which is a map of additional data. There are no restrictions on the contents of this map. It’s useful for error logging to categorise errors, so GraphQL Java provides a number of common error classifications. On top of this, Spring for GraphQL adds a few extra error classifications. You can also create custom error classifications. We’ll explain classifications in more detail later in this chapter. In this example, the `InvalidSyntax` classification was added by GraphQL Java.

Note how there was no `data` key in the GraphQL response, because no DataFetchers were invoked. Execution was terminated when the syntax error was detected.

Let’s see another example of a request error, when we attempt to request a field `doesNotExist` that does not exist in the Query type of the schema.

```
[](#cb166-1)query missing {
[](#cb166-2)    doesNotExist
[](#cb166-3)}
```

```
[](#cb167-1){
[](#cb167-2)  "errors": [
[](#cb167-3)    {
[](#cb167-4)      "message": "Validation error (FieldUndefined@[doesNotExist]) : 
[](#cb167-5) Field 'doesNotExist' in type 'Query' is undefined",
[](#cb167-6)      "locations": [
[](#cb167-7)        {
[](#cb167-8)          "line": 2,
[](#cb167-9)          "column": 5
[](#cb167-10)        }
[](#cb167-11)      ],
[](#cb167-12)      "extensions": {
[](#cb167-13)        "classification": "ValidationError"
[](#cb167-14)      }
[](#cb167-15)    }
[](#cb167-16)  ]
[](#cb167-17)}
```

The `message` communicates that the field `doesNotExist` does not exist in the Query type. As this error can be linked to a `location` in the GraphQL document, it is provided.

In the `extensions` map, GraphQL Java inserts the classification `ValidationError`. It is invalid to ask for a field in a GraphQL request which does not exist in the schema.

Note that there was no `data` key in the GraphQL response, because no DataFetchers were invoked. Execution was terminated when the validation error was detected.

## Field errors

Field errors are raised during the execution of a field, resulting in a partial response. In other words, an error raised during the execution of a DataFetcher.

For example, a basic Pet schema with friends.

```
[](#cb168-1)type Query {
[](#cb168-2)    favoritePet: Pet
[](#cb168-3)}
[](#cb168-4)
[](#cb168-5)type Pet {
[](#cb168-6)    id: ID
[](#cb168-7)    name: String
[](#cb168-8)    friends: [Pet]
[](#cb168-9)}
```

We make a request with this query:

```
[](#cb169-1)query whoIsAGoodPup {
[](#cb169-2)    favoritePet {
[](#cb169-3)        name
[](#cb169-4)        friends {
[](#cb169-5)            name
[](#cb169-6)        }
[](#cb169-7)    }
[](#cb169-8)}
```

Let’s write the `friends` DataFetcher to intentionally fail, to simulate an error.

```
[](#cb170-1)package myservice.service;
[](#cb170-2)
[](#cb170-3)import java.util.List;
[](#cb170-4)
[](#cb170-5)record Pet(String id, String name, List<String> friendIds) {
[](#cb170-6)  static List<Pet> pets = List.of(
[](#cb170-7)    new Pet("1", "Luna", List.of("2")),
[](#cb170-8)    new Pet("2", "Skipper", List.of("1"))
[](#cb170-9)  );
[](#cb170-10)}
```

```
[](#cb171-1)@Controller
[](#cb171-2)class PetsController {
[](#cb171-3)  @QueryMapping
[](#cb171-4)  Pet favoritePet() {
[](#cb171-5)    // Logic to return the user's favorite pet.
[](#cb171-6)    // Logic mocked with Luna the Dog.
[](#cb171-7)    return Pet.pets.get(0);
[](#cb171-8)  }
[](#cb171-9) 
[](#cb171-10)  @SchemaMapping
[](#cb171-11)  List<Pet> friends(Pet pet) {
[](#cb171-12)    throw new RuntimeException("Something went wrong!");
[](#cb171-13)  }
[](#cb171-14)}
```

The DataFetcher that loads the `friends` of the `pet` throws an exception. This is the GraphQL response for the whole query, in JSON.

```
[](#cb172-1){
[](#cb172-2)  "errors": [
[](#cb172-3)    {
[](#cb172-4)      "message": "INTERNAL_ERROR for f8f26fdc-4",
[](#cb172-5)      "locations": [
[](#cb172-6)        {
[](#cb172-7)          "line": 4,
[](#cb172-8)          "column": 9
[](#cb172-9)        }
[](#cb172-10)      ],
[](#cb172-11)      "path": [
[](#cb172-12)        "favoritePet",
[](#cb172-13)        "friends"
[](#cb172-14)      ],
[](#cb172-15)      "extensions": {
[](#cb172-16)        "classification": "INTERNAL_ERROR"
[](#cb172-17)      }
[](#cb172-18)    }
[](#cb172-19)  ],
[](#cb172-20)  "data": {
[](#cb172-21)    "favoritePet": {
[](#cb172-22)      "name": "Luna",
[](#cb172-23)      "friends": null
[](#cb172-24)    }
[](#cb172-25)  }
[](#cb172-26)}
```

Our example demonstrates that field errors don’t cause the whole request to fail, meaning a GraphQL result can contain “partial results”, where part of the response contains data, while other parts are `null`. We were able to load Luna’s name, but none of her friends. Because we were unable to load `friends`, the “friends” key has the value null.

Partial results have consequences for the client. Clients must always inspect the “errors” of the response in order to determine whether an error occurred or not. Note that you cannot rely on a null value to indicate a GraphQL error was raised, instead the `errors` key of the response must always be inspected. A DataFetcher can return both data and errors for a given field.

We have one error with a “message” key, representing the exception thrown inside the `friends` DataFetcher. The “locations” key references the position of `friends` in the query and “path” of the field that caused the error.

In the extensions key, Spring for GraphQL inserts the classification `INTERNAL_ERROR`. We’ll expand on error classifications added by Spring for GraphQL later in this chapter.

## How errors appear in the response

To recap, a GraphQL response contains `data`, `errors`, and `extensions`. The response is returned as a JSON object. In GraphQL Java, this response is represented as an `ExecutionResult`, containing data, a `java.util.List` of `graphql.GraphQLError` objects, and a `java.util.Map` of extensions.

```
[](#cb173-1){
[](#cb173-2)  "data": <data>,
[](#cb173-3)  "errors": <list of GraphQL errors>,
[](#cb173-4)  "extensions": <map of extensions>
[](#cb173-5)}
```

The GraphQL spec defines a few rules for when `data` and `errors` are present in the response.

*   The `errors` entry will be present if there are errors raised during the request. If there are no errors raised during the request, then the `errors` entry must not be present. If the `errors` entry is present, it is a non-empty list.

*   If the `data` entry of the response is not present, the `errors` entry must be present. For example, a request error will have no data entry in the response, so the `errors` entry must be present.

*   If the `data` entry of the response is present (including the value `null`), the `errors` entry must be present if and only if one or more field errors were raised during execution.

The `extensions` entry is optional and there are no restrictions on the contents of this map.

In GraphQL Java, an individual error is represented by the `graphql.GraphQLError` interface, which contains these methods.

```
[](#cb174-1)String getMessage();
[](#cb174-2)List<SourceLocation> getLocations();
[](#cb174-3)List<Object> getPath();
[](#cb174-4)Map<String, Object> getExtensions();
[](#cb174-5)ErrorClassification getErrorType();
```

The GraphQL spec defines an error can contain up to four keys: `message`, `locations`, `path`, and `extensions`. While the first four methods directly represent keys in the JSON response, `ErrorClassification` is a GraphQL Java-specific interface that allows us to classify an error. This is what appears in the `classification` field inside the `extensions` map of the GraphQL response.

### Error classifications

Classifying errors is useful for logging and monitoring. GraphQL Java enables error classifications to be added to responses. Note that although classifying errors is not required by the GraphQL spec, we have found it invaluable for categorizing errors in metrics.

GraphQL Java includes common error classifications, and Spring for GraphQL adds a few additional classifications. You can also create custom classifications.

#### GraphQL Java provided error classifications

GraphQL Java provides commonly used error classifications in `graphql.ErrorType`. These classifications implement the `graphql.ErrorClassification` interface.

| Classification | Description |
| --- | --- |
| InvalidSyntax | Request error due to invalid GraphQL syntax |
| ValidationError | Request error due to invalid request |
| OperationNotSupported | Request error if request attempts to perform an operation not defined in the schema |
| DataFetchingException | Field error raised during data fetching |
| NullValueInNonNullableField | Field error when a field defined as non-null in the schema returns a null value |

#### Spring for GraphQL provided error classifications

Additionally, Spring for GraphQL adds a few more useful error classifications, which also implement the `graphql.ErrorClassification` interface.

*   `BAD_REQUEST`
*   `UNAUTHORIZED`
*   `FORBIDDEN`
*   `NOT_FOUND`
*   `INTERNAL_ERROR`

If an exception is unresolved, it will be categorized by default as an `INTERNAL_ERROR` with a generic message including the category name and `executionId`. You can customize this with a `DataFetcherExceptionResolverAdapter` which will be discussed later in this chapter.

GraphQL Java provided error classifications are also used in Spring for GraphQL. For example, a request with invalid GraphQL syntax will contain a response error with the classification `InvalidSyntax`. Likewise, `ValidationError`, `OperationNotSupported`, and `NullValueInNonNullableField` classifications are also used by Spring for GraphQL.

Note that an HTTP response code of 200 (OK) is always returned if the GraphQL engine is invoked, even if there are errors in the response. The error classification is included in the errors key of the GraphQL response. For example, if a database is unavailable, this will cause a field error to be raised, and a GraphQL error will appear in the response. The HTTP response code for a request with this database issue will still be 200\. This may seem surprising if you have experience with other APIs such as REST. See the discussion on [HTTP status codes](#ch010.xhtml_http-status-codes) in the previous chapter for a detailed explanation.

#### Custom error classifications

You can also create custom error classifications by implementing the `ErrorClassification` interface from GraphQL Java. Error classifications are added to the GraphQL error builder, as we’ll see later in this chapter.

For example, you could categorize different types of failed authorization checks, rather than the catch-all “UNAUTHORIZED” error classification. You can create separate error classifications for each category of authorization failure, and use these categories to monitor authorization failures with metrics on the server side.

## How to return errors

We’ve seen how errors are presented in GraphQL responses. Now let’s discuss how to return errors inside our Spring for GraphQL service. We’ll discuss two fundamental ways to return field errors: by throwing exceptions during a DataFetcher invocation or by returning errors via `DataFetcherResult`.

## Throw exception during DataFetcher invocation

One way to return errors is to raise an exception during DataFetcher invocation. When a DataFetcher throws an exception, GraphQL Java converts it into a GraphQL error, which is added to the overall GraphQL response and the value of field is set to `null`. In our earlier example where the `friends` DataFetcher raised a `RuntimeException`, the `friends` field in the data was set to `null`. In a more realistic service, the `friends` database may be unavailable, causing an exception to be raised.

When an exception is thrown during DataFetcher invocation, GraphQL Java’s `DataFetcherExceptionHandler` is called. A GraphQL Java application can register a `DataFetcherExceptionHandler`, and Spring for GraphQL provides a built-in handler `ExceptionResolversExceptionHandler`. This handler allows for a chain of exception resolvers to be registered. This is configured for use by the Spring Boot starter. As we saw in the error examples earlier in this chapter, no additional code is required to configure exception handling.

However, if you would like to customize exception resolution, you can register `DataFetcherExceptionResolver`s. Spring for GraphQL makes it easy to register custom exception resolvers, which we’ll demonstrate in the next section on [customizing exception resolution](#ch011.xhtml_customizing-exception-resolution).

Even if you have not explicitly selected Spring WebFlux as a dependency for your GraphQL service, internally Spring for GraphQL uses Reactor types such as `Mono`. Spring for GraphQL uses `reactor-core` as a dependency. Note that while Reactor is used internally by Spring for GraphQL, you do not need to use Reactor types in your code for your service. If the words `Mono` and `Flux` are unfamiliar, it is fine to skip over the discussion of Reactor types in the Spring for GraphQL internals.

Each registered exception resolver will be called, one after another, until one returns a list of GraphQL errors (which can be empty). If the returned `Mono` from the exception resolver completes empty, without emitting a list, the exception remains unresolved, and we invoke the next exception resolver.

If no exception resolver takes care of the exception, Spring for GraphQL creates a default error with an `INTERNAL_ERROR` classification with a generic error message. Spring for GraphQL makes an intentionally opaque message to avoid leaking implementation details. In general, we suggest you only show clients what they need to know to understand the response. Avoid revealing implementation details. For example, avoid dumping stack traces in the error message. You should separately monitor detailed exception information such as stack traces.

### Customizing exception resolution

If you would like to customize exception resolution, Spring for GraphQL offers a `DataFetcherExceptionResolverAdapter` abstract class that already implements much of the contract for you.

For example, let’s implement an exception resolver that overrides the actual exception message.

```
[](#cb175-1)package myservice.service;
[](#cb175-2)
[](#cb175-3)import graphql.GraphQLError;
[](#cb175-4)import graphql.GraphqlErrorBuilder;
[](#cb175-5)import graphql.schema.DataFetchingEnvironment;
[](#cb175-6)import org.springframework.graphql.execution
[](#cb175-7)  .DataFetcherExceptionResolverAdapter;
[](#cb175-8)import org.springframework.graphql.execution.ErrorType;
[](#cb175-9)import org.springframework.stereotype.Component;
[](#cb175-10)
[](#cb175-11)@Component
[](#cb175-12)class CustomErrorMessageExceptionResolver
[](#cb175-13)    extends DataFetcherExceptionResolverAdapter {
[](#cb175-14)    @Override
[](#cb175-15)    protected GraphQLError resolveToSingleError(Throwable ex,
[](#cb175-16)      DataFetchingEnvironment env) {
[](#cb175-17)      return GraphqlErrorBuilder.newError(env)
[](#cb175-18)        .errorType(ErrorType.INTERNAL_ERROR) // Error classification
[](#cb175-19)        .message("My custom message") // Overrides the message
[](#cb175-20)        .build();
[](#cb175-21)    }
[](#cb175-22)}
```

The Spring Boot starter automatically detects `DataFetcherExceptionResolver` beans as part of instantiating `GraphQlSource`, the same step that also automatically loads schema files and more. The abstract class `DataFetcherExceptionResolverAdapter` implements `DataFetcherExceptionResolver`. In this example, `CustomErrorMessageExceptionResolver` extends `DataFetcherExceptionResolverAdapter` and is annotated with `@Component` to indicate it should be scanned by the Spring Boot starter.

When extending `DataFetcherExceptionResolverAdapter`, you have the choice of either overriding the methods `resolveToSingleError` or `resolveToMultipleErrors`. As the names suggest, a `resolveToSingleError` will resolve an exception to a single GraphQL error, and `resolveToMultipleErrors` will resolve an exception to a list of GraphQL errors.

Note that the `DataFetcherExceptionResolverAdapter` does not require you to use Reactor types, as parts of the contract requiring Reactor types have already been implemented for you.

The recommended way to create new instances of `graphql.GraphQLError` is via `graphql.GraphqlErrorBuilder`. Please note the slightly different capitalization in names. This builder is more convenient than implementing the `graphql.GraphQLError` interface directly. Use the factory method that takes a `DataFetchingEnvironment`, as shown in this example.

If you are using GraphQL Java without Spring for GraphQL, note that the handler in GraphQL Java is different. GraphQL Java uses the `SimpleDataFetcherExceptionHandler` implementation. This handler creates a `ExceptionWhileDataFetching` error with the classification `ErrorType.DataFetchingException`.

## Return data and errors with `DataFetcherResult`

The only way to return both data and errors for a field is with `DataFetcherResult`. Contrast this to throwing exceptions, which will always set the field value to `null`.

For example, we have a list of some pets, but not all of it was available during execution. Let’s take a look at a simple Pet schema.

```
[](#cb176-1)type Query {
[](#cb176-2)    myPets: [Pet]
[](#cb176-3)}
[](#cb176-4)
[](#cb176-5)type Pet {
[](#cb176-6)    id: ID
[](#cb176-7)    name: String
[](#cb176-8)}
```

```
[](#cb177-1)package myservice.service;
[](#cb177-2)
[](#cb177-3)import java.util.List;
[](#cb177-4)
[](#cb177-5)record Pet(String id, String name) {
[](#cb177-6)  static List<Pet> pets = List.of(
[](#cb177-7)    new Pet("1", "Luna"),
[](#cb177-8)    new Pet("2", "Skipper")
[](#cb177-9)  );
[](#cb177-10)}
```

```
[](#cb178-1)package myservice.service;
[](#cb178-2)
[](#cb178-3)import graphql.ErrorType;
[](#cb178-4)import graphql.GraphQLError;
[](#cb178-5)import graphql.GraphqlErrorBuilder;
[](#cb178-6)import graphql.execution.DataFetcherResult;
[](#cb178-7)import graphql.schema.DataFetchingEnvironment;
[](#cb178-8)import org.springframework.graphql.data.method.annotation
[](#cb178-9)  .QueryMapping;
[](#cb178-10)import org.springframework.stereotype.Controller;
[](#cb178-11)
[](#cb178-12)import java.util.List;
[](#cb178-13)
[](#cb178-14)@Controller
[](#cb178-15)class PetsController {
[](#cb178-16)
[](#cb178-17)  @QueryMapping
[](#cb178-18)  DataFetcherResult<List<Pet>> myPets(
[](#cb178-19)    DataFetchingEnvironment env) {
[](#cb178-20)    // Your partial list of data here
[](#cb178-21)    // In-memory Pet example
[](#cb178-22)    List<Pet> result = List.of(Pet.pets.get(1));
[](#cb178-23)
[](#cb178-24)    GraphQLError error = GraphqlErrorBuilder.newError(env)
[](#cb178-25)      .errorType(ErrorType.DataFetchingException)
[](#cb178-26)      .message("Data could only be partially loaded")
[](#cb178-27)      .build();
[](#cb178-28)    return DataFetcherResult.<List<Pet>>newResult()
[](#cb178-29)      .data(result)
[](#cb178-30)      .error(error)
[](#cb178-31)      .build();
[](#cb178-32)  }
[](#cb178-33)
[](#cb178-34)}
```

In this chapter, we discussed GraphQL errors in depth. We discussed request and field errors, and how they are presented in the GraphQL response. Then we demonstrated how to raise errors in our Spring for GraphQL service, and how to customize exception handling.

# Schema design

Schema design is a critical part of implementing a GraphQL service. In this chapter, we will discuss key principles and best practices from our experiences running GraphQL services.

## Schema-first and implementation-agnostic

We should design our schema deliberately as a standalone activity. From experience, we’ve seen it is not the best approach to infer a schema or generate it from another source. Generated schemas will always be of lower quality.

GraphQL differs from a database schema or REST API that we might use to fetch data for a query.

Implementation details should not influence schema design and should never be leaked. We always need to ask: is this information really needed to be exposed and is it the right format?

For example, just because the current database backing the API doesn’t allow the `User.name` field to be null doesn’t automatically mean it should also be non-nullable in the schema. The design needs to be justified independent of the current implementation.

If we build a GraphQL API and the implementation involves calling a user service via REST, it doesn’t mean the user resource for a REST API is what we want to expose. We should design a `User` type in GraphQL based on the requirements and then look into how we can implement it.

Of course, we might need to adjust our ideal solution based on implementation constraints. We need to be pragmatic and deliver a working API. The point remains that we should always start with the schema first in order to design the best API.

## Evolution over versioning

We prefer evolution over versioning as the recommended approach for GraphQL. In REST APIs, we might see versions frequently, often as part of the URL like `/v2/`. In a GraphQL API, there is only one URL and one schema that grows over time with incremental changes.

For example, we might start out with just a User.

```
[](#cb179-1)type Query {
[](#cb179-2)    user(id: ID!): User
[](#cb179-3)}
[](#cb179-4)
[](#cb179-5)type User {
[](#cb179-6)    id: ID!
[](#cb179-7)    name: String
[](#cb179-8)}
```

Then we might change the schema to include address information for a user like this.

```
[](#cb180-1)type Query {
[](#cb180-2)    user(id: ID!): User
[](#cb180-3)}
[](#cb180-4)
[](#cb180-5)type User {
[](#cb180-6)    id: ID!
[](#cb180-7)    name: String
[](#cb180-8)    address: Address
[](#cb180-9)}
[](#cb180-10)
[](#cb180-11)type Address {
[](#cb180-12)    street: String
[](#cb180-13)    city: String
[](#cb180-14)    country: String
[](#cb180-15)}
```

This schema change makes our API is richer, clients can choose whether to use the new functionality by including an address in their user query selection fields or not.

It’s more challenging to evolve the schema when a change is a breaking change. For example, if we decide that the current `name: String` is not enough, we introduce a better `UserName` object with fields like `legalName` and `preferredName`.

```
[](#cb181-1)type Query {
[](#cb181-2)    user(id: ID!): User
[](#cb181-3)}
[](#cb181-4)
[](#cb181-5)type User {
[](#cb181-6)    id: ID!
[](#cb181-7)    name: UserName
[](#cb181-8)}
[](#cb181-9)
[](#cb181-10)type UserName {
[](#cb181-11)    legalName: String
[](#cb181-12)    preferredName: String
[](#cb181-13)}
```

However, this schema change breaks all existing clients, who are using `name`, such as this query.

```
[](#cb182-1)query broken {
[](#cb182-2)    user(id: "123") {
[](#cb182-3)        name
[](#cb182-4)    }
[](#cb182-5)}
```

The query would suddenly become invalid and always result in an error because `name` is no longer a User string field, and now it’s a UserName object that needs a sub-selection.

This is how to manage breaking changes:

1.  Introduce alternative (if applicable)
2.  Deprecate old field
3.  Monitor usage and/or wait a certain amount of time
4.  Remove old field

Let’s walk through how we would manage a breaking change in our User example.

First, we add a new field for userName, while leaving the existing User field there for now.

```
[](#cb183-1)type Query {
[](#cb183-2)    user(id: ID!): User
[](#cb183-3)}
[](#cb183-4)
[](#cb183-5)type User {
[](#cb183-6)    id: ID!
[](#cb183-7)    name: String
[](#cb183-8)    userName: UserName
[](#cb183-9)}
[](#cb183-10)
[](#cb183-11)type UserName {
[](#cb183-12)    legalName: String
[](#cb183-13)    preferredName: String
[](#cb183-14)}
```

Then we deprecate the old field with the built-in `@deprecated` directive. Note that directives appear after the declaration that they decorate such as name.

```
[](#cb184-1)type Query {
[](#cb184-2)    user(id: ID!): User
[](#cb184-3)}
[](#cb184-4)
[](#cb184-5)type User {
[](#cb184-6)    id: ID!
[](#cb184-7)    name: String
[](#cb184-8)    @deprecated(reason: "Use richer alternative `userName`.")
[](#cb184-9)    userName: UserName
[](#cb184-10)}
[](#cb184-11)
[](#cb184-12)type UserName {
[](#cb184-13)    legalName: String
[](#cb184-14)    preferredName: String
[](#cb184-15)}
```

The next step is very context specific. Depending on the kind of client API and any service guarantees, we might monitor its usage and wait until nobody uses the field anymore. Or we might simply give all clients a certain amount of time to migrate, such as 6 months, or do a combination of both.

Then in the last step, remove the field.

```
[](#cb185-1)type Query {
[](#cb185-2)    user(id: ID!): User
[](#cb185-3)}
[](#cb185-4)
[](#cb185-5)type User {
[](#cb185-6)    id: ID!
[](#cb185-7)    userName: UserName
[](#cb185-8)}
[](#cb185-9)
[](#cb185-10)type UserName {
[](#cb185-11)    legalName: String
[](#cb185-12)    preferredName: String
[](#cb185-13)}
```

Now we have finished the gradual transition from `name: String` to `userName: UserName`.

Of course, you should adjust your approach based on your situation.

For example, you may choose to immediately make a breaking change if:

*   you detect that nobody is using that particular field
*   you are certain that clients can handle the breaking change
*   the change is for an internal company testing API, which is not used in production

You might also choose to retain a deprecated field for the foreseeable future rather than removing the field.

Our other general recommendation for these kinds of breaking changes is to design the schema for evolution and avoid them as much as possible. This chapter covers specific recommendations for schema evolution.

Every production GraphQL API is bound to face breaking changes. The general goal is to minimize the amount of breaking changes, not to avoid them completely.

## Connected

A GraphQL API should resemble a connected or graph-like structure for maximum client flexibility. The client should be able to “traverse” from one piece of data to another related one, in a single request.

For example, this schema is not connected.

```
[](#cb186-1)type Query {
[](#cb186-2)    issue: Issue
[](#cb186-3)    userById(id: ID!): User
[](#cb186-4)}
[](#cb186-5)
[](#cb186-6)type Issue {
[](#cb186-7)    description: String
[](#cb186-8)    ownerId: ID
[](#cb186-9)}
[](#cb186-10)
[](#cb186-11)type User {
[](#cb186-12)    id: ID
[](#cb186-13)    name: String
[](#cb186-14)}
```

This schema requires two queries to retrieve the owner’s name for an issue.

```
[](#cb187-1)# First
[](#cb187-2)query myIssue {
[](#cb187-3)    issue {
[](#cb187-4)        ownerId
[](#cb187-5)    }
[](#cb187-6)}
[](#cb187-7)# returns "123"
[](#cb187-8)
[](#cb187-9)# Second
[](#cb187-10)query myUser {
[](#cb187-11)    userById(id: "123") {
[](#cb187-12)        name
[](#cb187-13)    }
[](#cb187-14)}
```

This is the better, more connected schema.

```
[](#cb188-1)type Query {
[](#cb188-2)    issue: Issue
[](#cb188-3)}
[](#cb188-4)
[](#cb188-5)type Issue {
[](#cb188-6)    description: String
[](#cb188-7)    owner: User
[](#cb188-8)}
[](#cb188-9)
[](#cb188-10)type User {
[](#cb188-11)    id: ID
[](#cb188-12)    name: String
[](#cb188-13)}
```

Now the client can directly query the full `User` object for the issue in one query.

```
[](#cb189-1)query connected {
[](#cb189-2)    issue {
[](#cb189-3)        owner {
[](#cb189-4)            name
[](#cb189-5)        }
[](#cb189-6)    }
[](#cb189-7)}
```

It is good to look for any `<name>Id: String/ID` or other unique identifier fields in a schema, then verify if there is a good reason to retain them, or whether you might directly connect them to some other data.

Of course, there are limitations to how connected something can be, depending on the data sources you have access to.

## Schema elements are cheap

Don’t make types and fields overly generic in an attempt to make them reusable.

For example, you might consider reusing input objects like this search filter.

```
[](#cb190-1)type Query {
[](#cb190-2)    searchPets(filter: SearchFilter): [Pet]
[](#cb190-3)    searchHumans(filter: SearchFilter): [Human]
[](#cb190-4)}
[](#cb190-5)
[](#cb190-6)input SearchFilter {
[](#cb190-7)    name: String
[](#cb190-8)    ageMin: Int
[](#cb190-9)    ageMax: Int
[](#cb190-10)}
```

Reusing the input object is not a good idea because it couples the two fields unnecessarily together. What happens if we would like to add a `breed` field for pets? Now we have either a filter for humans that includes a `breed`, or we need to deprecate fields and introduce new ones.

The same principle is true for output types. This example can seem tempting especially for mutations.

```
[](#cb191-1)type Mutation {
[](#cb191-2)    deleteUser(input: DeleteUserInput!): ChangeUserPayload
[](#cb191-3)    updateUser(input: UpdateUserInput!): ChangeUserPayload
[](#cb191-4)}
[](#cb191-5)
[](#cb191-6)type ChangeUserPayload {
[](#cb191-7)    user: User
[](#cb191-8)}
```

This example has the same problem as the reused input objects. Once we want to change the return type for just one mutation, we have a problem.

The other trap we might fall into is trying to combine multiple use cases into one field. Fields are cheap, like any other element. Our service doesn’t get slower, or have any other direct negative effects with a larger amount of fields. We should make single-purpose fields explicit with specific naming.

Compare these two examples:

```
[](#cb192-1)type Query {
[](#cb192-2)    pet(id: ID, name: String): Pet
[](#cb192-3)}
```

vs

```
[](#cb193-1)type Query {
[](#cb193-2)    petById(id: ID!): Pet
[](#cb193-3)    petByName(name: String!): Pet
[](#cb193-4)}
```

The second version is better in every aspect. We have better names and the arguments are marked as non nullable. We can also again evolve the schema much more easily.

## Nullable fields

One of the most misunderstood topics in schema design is the nullability of fields. When starting to learn GraphQL, it confuses many people that fields are nullable by default, which leads to beginners making almost all fields non-nullable.

In GraphQL, almost all fields should be nullable to allow results to return more data. Let’s take a closer look at how GraphQL handles `null` data through examples.

Consider the case where a field is marked as non-nullable, but the data is `null` during execution. The schema gives the assurance that the field is never null, so GraphQL cannot return `null`. Instead, the parent is set to `null` if possible. If the parent of the original field is also non-nullable, then we set the parent of the parent to `null` if possible, and so on. The error is propagated through the hierarchy of parent fields until a field can be set to `null`.

Let’s step through `null` result handling with a concrete schema example:

```
[](#cb194-1)type Query {
[](#cb194-2)    a: A
[](#cb194-3)}
[](#cb194-4)
[](#cb194-5)type A {
[](#cb194-6)    b: B
[](#cb194-7)}
[](#cb194-8)
[](#cb194-9)type B {
[](#cb194-10)    c: C!
[](#cb194-11)}
[](#cb194-12)
[](#cb194-13)type C {
[](#cb194-14)    d: String!
[](#cb194-15)}
```

If field `d` is `null` during execution for this query,

```
[](#cb195-1)query myQuery {
[](#cb195-2)    a {
[](#cb195-3)        b {
[](#cb195-4)            c {
[](#cb195-5)                d
[](#cb195-6)            }
[](#cb195-7)        }
[](#cb195-8)    }
[](#cb195-9)}
```

then we end up with this result.

```
[](#cb196-1){
[](#cb196-2)  "data": {
[](#cb196-3)    "a" : {
[](#cb196-4)      "b": null
[](#cb196-5)    }
[](#cb196-6)  }
[](#cb196-7)}
```

`d` was `null`, but marked as non-nullable. Therefore, we tried to set the parent `c` to `null`. But `c` is also non-nullable, therefore we try and successfully set `b` to `null`.

If we change the schema so that field `b: B!` can’t be null either, then we end up with this.

```
[](#cb197-1){
[](#cb197-2)  "data": {
[](#cb197-3)    "a" : null
[](#cb197-4)  }
[](#cb197-5)}
```

And finally, if we change field `a` to `a: A!`, then we end up with everything set to `null`.

```
[](#cb198-1){
[](#cb198-2)  "data": null
[](#cb198-3)}
```

If the error propagates all the way up, we set everything to `null` and we even lose the result of other root fields. Let’s walk through a more realistic example.

A pet and human schema:

```
[](#cb199-1)type Query {
[](#cb199-2)    pet: Pet!
[](#cb199-3)    human: Human
[](#cb199-4)}
[](#cb199-5)
[](#cb199-6)type Pet {
[](#cb199-7)    name: String
[](#cb199-8)}
[](#cb199-9)
[](#cb199-10)type Human {
[](#cb199-11)    name: String
[](#cb199-12)}
```

This looks innocent, but if we query `pet` and `human` at the same time,

```
[](#cb200-1)query petAndHuman {
[](#cb200-2)    pet {
[](#cb200-3)        name
[](#cb200-4)    }
[](#cb200-5)    human {
[](#cb200-6)        name
[](#cb200-7)    }
[](#cb200-8)}
```

and if `pet` field fails to load, but `human` field load succeeds, we still end up with no data.

```
[](#cb201-1){
[](#cb201-2)  "data": null
[](#cb201-3)}
```

This is because we marked `pet` as non-nullable and the error propagates up and wipes out all results.

Now that we understand how GraphQL handles non-null, we can rephrase what it means that we declare a field non-null: “A non-nullable field is so essential that all other fields make little sense without it”.

The most basic examples are `id` fields. Normally, if the fetching of the `id` is unsuccessful, we can’t guarantee anything else and therefore we should make it non-nullable.

```
[](#cb202-1)type User {
[](#cb202-2)    id: ID!
[](#cb202-3)    name: UserName
[](#cb202-4)    address: Address
[](#cb202-5)}
```

In this example, `name` and `address` are not as fundamental and therefore not declared non-null.

Sometimes there are other fields that we should also make non-nullable. A `User` could have a primary email to login in, but it is reasonable to assume that this is such an important field that we don’t want to serve any data if we can’t load the primary email.

```
[](#cb203-1)type User {
[](#cb203-2)    id: ID!
[](#cb203-3)    primaryEmail: String! # also non-null
[](#cb203-4)    name: UserName
[](#cb203-5)    address: Address
[](#cb203-6)}
```

An interesting consequence of thinking about non-nullability in this way is that root fields should always be nullable.

One common mistake with nullability is arguing based on the current implementation. For example:

```
[](#cb204-1)type Query {
[](#cb204-2)    orders: [Order]
[](#cb204-3)}
[](#cb204-4)
[](#cb204-5)type Order {
[](#cb204-6)    id: ID!
[](#cb204-7)    customer: Customer!
[](#cb204-8)    # And more order fields here
[](#cb204-9)}
[](#cb204-10)
[](#cb204-11)type Customer {
[](#cb204-12)    id: ID!
[](#cb204-13)}
```

Perhaps this schema looks fine because we store all the current orders in one database and if we can load an order, then we also load the customer at the same time. But now imagine that we change our architecture in the future and decide to introduce an order service and a separate customer service. Suddenly we have a situation where we could load the order, but not the customer, resulting in the whole `Order` being null when the error propagates up.

If we look at `customer` again from the angle of “which fields are essential”, then we realize that non-nullable isn’t a good choice either. Other order data (which we have not shown in the example) might be still valuable, even when we can’t load the customer.

One special case where non-nullable fields often make sense is inside lists. For example:

```
[](#cb205-1)type Query {
[](#cb205-2)    orders: [Order!]
[](#cb205-3)}
```

The root field itself is nullable, but the elements inside the list are not nullable. Even if we take current or future implementations into consideration where we could load some orders, but not all, we mostly don’t want to burden the client with special error handling.

To summarize the recommendations about non-nullable Fields:

*   Root fields are always nullable
*   Essential fields like `id` or `key` are non-nullable
*   Elements inside lists probably are non-nullable
*   All other fields probably should be nullable

## Nullable input fields and arguments

Input fields are nullable by default, but in practice, we usually want to make as many of them non-nullable as possible. Non-nullable input fields and arguments have the simple advantage of clearly communicating that we need this input to the API user, while forcing us to be specific about the use case.

A nullable input field or argument often signals that we might have a field that is too generic, and we should think about how we can make them non-nullable.

```
[](#cb206-1)type Query {
[](#cb206-2)    user(id: ID, name: String): User
[](#cb206-3)}
```

Both arguments are nullable and the field itself is too generic. It is better to change fields that must be present to be non-nullable.

Consider the counterexample where a name field inside the input type has a special behavior for null, to indicate the user ought to be deleted.

```
[](#cb207-1)input UpdateUserInput {
[](#cb207-2)    id: ID!
[](#cb207-3)    name: String # null indicating deletion of the user
[](#cb207-4)}
```

This is not a good solution because it’s harder for a user to understand. It is much better to split into two inputs.

```
[](#cb208-1)input ChangeUserInput {
[](#cb208-2)    id: ID!
[](#cb208-3)    name: String!
[](#cb208-4)}
[](#cb208-5)
[](#cb208-6)input DeleteUserInput {
[](#cb208-7)    id: ID!
[](#cb208-8)}
```

As with fields, the elements inside a list are often an excellent good candidate for making non-nullable.

## Pagination for lists with Relay’s cursor connection specification

We strongly recommend that all lists use pagination, unless the list size is small and limited based on the domain.

A simple list such as `pets: [Pet]` can quickly become too large for clients to handle. A simple list restricts clients to only two options: requesting all the data, or none at all. If requested, the list will be returned in its entirety, regardless of the size.

A list of hundreds of elements can cause a noticeable slowdown in page loading time, due to the sheer time required to send the response back to the client. As the list continues to grow in size, it will become infeasible for a service to send all list elements before the connection timeout, or before the user’s patience runs out.

We strongly recommend that all lists use pagination unless their size is very small and it is very clear that the list can’t grow further based on the domain. For example, the number of planets in the Solar System is limited, so planets would not need pagination. Based on our experience we recommend considering pagination for lists larger than 25-50 elements.

### Relay’s cursor connections specification

The most common pagination approach in GraphQL comes from [Relay’s cursor connections specification](https://relay.dev/graphql/connections.htm), and has become the de facto standard for how GraphQL schemas should handle large lists. Relay is a JavaScript framework for fetching GraphQL in React applications.

The Relay connections specification is a “cursor based pagination”, meaning requests are slices of the overall list relative to a “cursor”. This cursor identifies the position within the overall list where we start a slice from. Then we pick another cursor and slice again. We can slice backwards or forwards. Notably, we can’t skip any elements, we must request a fresh slice relative to a cursor.

The Relay connections specification implements cursor based pagination with a few concepts: Connections, Edges, Nodes, and PageInfo. We’ll explain these concepts alongside an example Pet schema.

While there is quite some ceremony around pagination, the effort is worthwhile in order to produce a good API.

### Schema

This is an example Pet schema implementing the Relay connections specification. We’ll go into further details of the specification after walking through example queries.

```
[](#cb209-1)type Query {
[](#cb209-2)    pets(first: Int, after: String, last: Int, before: String): 
[](#cb209-3)        PetConnection
[](#cb209-4)}
[](#cb209-5)
[](#cb209-6)type PetConnection {
[](#cb209-7)    edges: [PetEdge]
[](#cb209-8)    pageInfo: PageInfo!
[](#cb209-9)}
[](#cb209-10)
[](#cb209-11)type PetEdge {
[](#cb209-12)    cursor: String!
[](#cb209-13)    node: Pet!
[](#cb209-14)}
[](#cb209-15)
[](#cb209-16)type PageInfo {
[](#cb209-17)    startCursor: String
[](#cb209-18)    endCursor: String
[](#cb209-19)    hasNextPage: Boolean!
[](#cb209-20)    hasPreviousPage: Boolean!
[](#cb209-21)}
[](#cb209-22)
[](#cb209-23)type Pet {
[](#cb209-24)    name: String
[](#cb209-25)    # Your additional Pet fields here
[](#cb209-26)}
```

### Query and response

This is how to query the first 2 pets with a schema implementing the Relay connections specification.

```
[](#cb210-1)query myPets {
[](#cb210-2)    pets(first: 2) {
[](#cb210-3)        edges {
[](#cb210-4)            cursor
[](#cb210-5)            node {
[](#cb210-6)                name
[](#cb210-7)            }
[](#cb210-8)        }
[](#cb210-9)        pageInfo {
[](#cb210-10)            startCursor
[](#cb210-11)            endCursor
[](#cb210-12)            hasNextPage
[](#cb210-13)            hasPreviousPage
[](#cb210-14)        }
[](#cb210-15)    }
[](#cb210-16)}
```

Let’s start at the top of the query. The `first` argument limits the result to a maximum of 2 elements. We don’t supply any cursor argument, because we don’t yet have a cursor.

In the next layer of the query are our connection fields, `edges` and `pageInfo`.

An edge is a wrapper around the actual entity we want to iterate over, in this example a node representing a `Pet`. The `name` in this query is the name field of a `Pet`. Edges also provide metadata such as `cursor`.

At the same level of `edges`, we also query `pageInfo` for general information about the results, so can we move forward or backward in the list.

An example response to the query could look like this.

```
[](#cb211-1){
[](#cb211-2)  "pets": {
[](#cb211-3)    "edges": [
[](#cb211-4)      {
[](#cb211-5)      "cursor": "ABCD123",
[](#cb211-6)      "node": {
[](#cb211-7)        "name": "Luna"
[](#cb211-8)      },
[](#cb211-9)      {
[](#cb211-10)      "cursor": "XYZ789",
[](#cb211-11)      "node": {
[](#cb211-12)        "name": "Skipper"
[](#cb211-13)      }
[](#cb211-14)    ],
[](#cb211-15)    "pageInfo": {
[](#cb211-16)      "startCursor": "ABCD123",
[](#cb211-17)      "endCursor": "XYZ789",
[](#cb211-18)      "hasNextPage": true,
[](#cb211-19)      "hasPreviousPage": false
[](#cb211-20)    }
[](#cb211-21)  }
[](#cb211-22)}
```

### Requesting more pages

In our initial query, we received data for two pets with their corresponding cursors. In the response, `hasNextPage` was true, so we can request the next slice of data.

To request the next 10 pets after “Skipper” (which had a cursor of “XYZ789”), we would query:

```
[](#cb212-1)query morePets {
[](#cb212-2)    pets(first: 10, after: "XYZ789") {
[](#cb212-3)        edges {
[](#cb212-4)            cursor
[](#cb212-5)            node {
[](#cb212-6)                name
[](#cb212-7)            }
[](#cb212-8)        }
[](#cb212-9)        pageInfo {
[](#cb212-10)            startCursor
[](#cb212-11)            endCursor
[](#cb212-12)            hasNextPage
[](#cb212-13)            hasPreviousPage
[](#cb212-14)        }
[](#cb212-15)    }
[](#cb212-16)}
```

We could also go backwards, and request the one pet before “Skipper” (which had a cursor of “XYZ789”):

```
[](#cb213-1)query previousPet {
[](#cb213-2)    pets(last: 1, before: "XYZ789") {
[](#cb213-3)        edges {
[](#cb213-4)            cursor
[](#cb213-5)            node {
[](#cb213-6)                name
[](#cb213-7)            }
[](#cb213-8)        }
[](#cb213-9)        pageInfo {
[](#cb213-10)            startCursor
[](#cb213-11)            endCursor
[](#cb213-12)            hasNextPage
[](#cb213-13)            hasPreviousPage
[](#cb213-14)        }
[](#cb213-15)    }
[](#cb213-16)}
```

### Key concepts of Relay’s cursor connections specification

We previously walked through how to use pagination as a client. Now let’s take a closer look at how to model pagination in our schema.

#### Connection

A connection represents a page of data (`edges`), with additional metadata to enable further page requests (`pageInfo`).

Instead of returning a list, pagination means we return a connection object with the name `<Entity>Connection`, such as `PetConnection` in our example.

```
[](#cb214-1)type Query {
[](#cb214-2)    pets(
[](#cb214-3)        first: Int,
[](#cb214-4)        after: String,
[](#cb214-5)        last: Int,
[](#cb214-6)        before: String
[](#cb214-7)    ): PetConnection
[](#cb214-8)}
```

As we saw in the previous query examples, `first` and `last` are of type `Int` because they represent how many objects we want to request. `after` and `before` are of type `String` because they are cursors that identify a position within a list of elements.

Note that you can choose to support only `first/after` or `last/before`, if you don’t want to support pagination in both directions.

You could also add more arguments to filter elements, such as a `namePattern` to filter pets by name:

```
[](#cb215-1)type Query {
[](#cb215-2)    pets(
[](#cb215-3)        first: Int,
[](#cb215-4)        after: String,
[](#cb215-5)        last: Int,
[](#cb215-6)        before: String,
[](#cb215-7)        namePattern: String
[](#cb215-8)    ): PetConnection
[](#cb215-9)}
```

The `<Entity>Connection` type must have at least the two fields `edges` and `pageInfo`.

```
[](#cb216-1)type PetConnection {
[](#cb216-2)    edges: [PetEdge]
[](#cb216-3)    pageInfo: PageInfo!
[](#cb216-4)}
```

An edge is a wrapper containing the element data and additional metadata. An edge type is named `<Entity>Edge`. In our example, we are interested in pages of `Pet`s so call this type a `PetEdge`.

Pagination metadata is always called `PageInfo` and shared across all edges.

We can add more fields to a connection type. For example, a connection type could contain a `totalCount` field. Although, note that adding `totalCount` can be problematic because it might not be easy to support when the underlying architecture changes.

#### Edges

The `edges` of a connection represent a page of data. An edge is a wrapper object that contains a data element (e.g. a `Pet`) and metadata. It is named in the format `<Entity>Edge`. It must have at least two fields: the `cursor` for the current element and the actual element named `node`. Optionally, additional fields can be added.

```
[](#cb217-1)type PetEdge {
[](#cb217-2)    cursor: String!
[](#cb217-3)    node: Pet!
[](#cb217-4)}
```

#### PageInfo

The `PageInfo` type contains pagination metadata summarizing all the requested `edges` in a query. It must contain the following fields:

```
[](#cb218-1)type PageInfo {
[](#cb218-2)    startCursor: String
[](#cb218-3)    endCursor: String
[](#cb218-4)    hasNextPage: Boolean!
[](#cb218-5)    hasPreviousPage: Boolean!
[](#cb218-6)}
```

`PageInfo` summarizes the current page’s location and whether additional data can be requested before or after the current page.

#### Optional shortcut: adding nodes to a connection type

You might have noticed in previous examples, we had a `cursor` field for every element inside the `node` field, as well as a summary of `cursor` information in the `PageInfo` type. If you are only interested in `cursor` information for the overall page, and not for each individual element, you can use a shortcut to shorten your query.

You can add a direct `nodes` field on a connection type.

```
[](#cb219-1)type PetConnection {
[](#cb219-2)    edges: [PetEdge]
[](#cb219-3)    nodes: [Pet] # Optional shortcut
[](#cb219-4)    pageInfo: PageInfo!
[](#cb219-5)}
```

This allows us to directly query pet data with `nodes` rather than via `edges`. We retrieve the `startCursor` and `endCursor` for the page, rather than the `cursor` for every pet as we did in the initial pagination response example.

```
[](#cb220-1)query shortcut {
[](#cb220-2)    pets(first: 2) {
[](#cb220-3)        nodes {
[](#cb220-4)            name
[](#cb220-5)        }
[](#cb220-6)        pageInfo {
[](#cb220-7)            startCursor
[](#cb220-8)            endCursor
[](#cb220-9)            hasNextPage
[](#cb220-10)            hasPreviousPage
[](#cb220-11)        }
[](#cb220-12)    }
[](#cb220-13)}
```

Compare the query above to the initial pagination example in this section, which is longer because it queries pet data with `nodes` via the `edges` field.

```
[](#cb221-1)query myPets {
[](#cb221-2)    pets(first: 2) {
[](#cb221-3)        edges {
[](#cb221-4)            cursor
[](#cb221-5)            node {
[](#cb221-6)                name
[](#cb221-7)            }
[](#cb221-8)        }
[](#cb221-9)        pageInfo {
[](#cb221-10)            startCursor
[](#cb221-11)            endCursor
[](#cb221-12)            hasNextPage
[](#cb221-13)            hasPreviousPage
[](#cb221-14)        }
[](#cb221-15)    }
[](#cb221-16)}
```

## Expected errors

In the [GraphQL errors chapter](#ch011.xhtml_graphql-errors), we discussed errors appearing in the GraphQL response, typically arising from unexpected issues such as a database not being reachable or bugs, but they are not well suited for *expected* errors. Expected errors are situations that the client wants to handle specifically. In this section we’ll demonstrate best practice for managing expected errors.

Some typical examples of expected errors:

*   Payment details are invalid
*   New user attempts to sign up with an existing user’s email address
*   A notoriously unreliable external system is not available

If the client wants to react to these situations, GraphQL errors are not great because they exist outside the normal response data and are untyped.

For example, an error for invalid payment details could look like this.

```
[](#cb222-1){
[](#cb222-2)  "data": {
[](#cb222-3)     "makePayment": null
[](#cb222-4)  },
[](#cb222-5)  "errors": [{
[](#cb222-6)    "message": "Payment failed",
[](#cb222-7)    "extensions": {
[](#cb222-8)      "classification": "PAYMENT_ERROR",
[](#cb222-9)      "details": "Invalid credit card"
[](#cb222-10)    }
[](#cb222-11)  }]
[](#cb222-12)}
```

A client now has to parse the “message” and potentially also look at the “extensions”, which are untyped and can contain any data.

Imagine a more complex query where the response contains partial data and some errors. It would be even harder to parse and handle the error correctly.

These shortcomings of GraphQL errors led to the idea of modeling expected errors in the schema. This makes it part of the typed API contract and allows a client to handle them much more safely. The cost we have to pay is a slightly more complex schema, as we will see in the next example.

Example:

```
[](#cb223-1)type Mutation {
[](#cb223-2)    makePayment(input: MakePaymentInput!): MakePaymentPayload
[](#cb223-3)}
[](#cb223-4)
[](#cb223-5)type MakePaymentPayload {
[](#cb223-6)    payment: Payment
[](#cb223-7)    error: MakePaymentError
[](#cb223-8)}
[](#cb223-9)
[](#cb223-10)enum MakePaymentError {
[](#cb223-11)    CC_INVALID,
[](#cb223-12)    PAYMENT_SYSTEM_UNAVAILABLE
[](#cb223-13)}
```

This brings the payment errors into the response type, which appears in the `data` section of the GraphQL response. Note how these errors are no longer in the `errors` section of the GraphQL response.

```
[](#cb224-1){
[](#cb224-2)  "data": {
[](#cb224-3)    "makePayment": {
[](#cb224-4)      "payment": null,
[](#cb224-5)      "error": "CC_INVALID"
[](#cb224-6)    }
[](#cb224-7)  }
[](#cb224-8)}
```

For mutations, the `Payload` type is a natural place for mutation-specific errors. For queries, we can use a union type to allow for normal results or errors.

```
[](#cb225-1)type Query {
[](#cb225-2)    pet(id: ID!): PetLookup
[](#cb225-3)}
[](#cb225-4)
[](#cb225-5)union PetLookup = Pet | PetLookupError
[](#cb225-6)
[](#cb225-7)type Pet {
[](#cb225-8)    # Your Pet fields here
[](#cb225-9)}
[](#cb225-10)
[](#cb225-11)type PetLookupError {
[](#cb225-12)    # Your PetLookupError fields here
[](#cb225-13)}
```

We can then use inline fragments to handle the result and error cases.

```
[](#cb226-1)query myPet {
[](#cb226-2)    pet(id: "123") {
[](#cb226-3)        ... on Pet {
[](#cb226-4)            # Your Pet fields here
[](#cb226-5)        }
[](#cb226-6)        ... on PetLookupError {
[](#cb226-7)            # Your PetLookupError fields here
[](#cb226-8)        }
[](#cb226-9)    }
[](#cb226-10)}
```

## Mutation format

The GraphQL community mostly uses a specific format for mutation, [which comes originally from Relay](https://relay.dev/docs/v1.6.2/graphql-server-specification/#mutations).

*   Name the field `<verb><Entity>`.
*   The field has a single argument `input: <verb><Entity>Input!`.
*   The type of the mutation response is `<verb><Entity>Payload`

For example, a mutation to create a user:

```
[](#cb227-1)type Mutation {
[](#cb227-2)    createUser(input: CreateUserInput!): CreateUserPayload
[](#cb227-3)}
```

## Naming standards

The GraphQL community has largely come to a consensus on schema naming standards. It’s good to adhere to these standards to build consistent schemas that also align with the overall GraphQL community.

*   Fields, input fields, and argument names are “camelCase”: `userName`
*   Types are “PascalCase”: `UserName`
*   Enum values are capitalized “SNAKE_CASE”: `FIRST_NAME`

You might have noticed we have followed these standards throughout the book.

In this chapter we covered key principles and best practices from our experiences running GraphQL services. We hope this chapter helps you design your own production ready GraphQL schemas.

# DataFetchers in depth

In this chapter we will build on the earlier [DataFetchers](#ch007.xhtml_datafetchers-part-1) chapter and discuss more advanced details, including how to make use of global and local context, and reactive patterns.

## More DataFetcher inputs

In the first [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1) we discussed inputs to Spring for GraphQL’s schema mapping controller methods, such as source (parent) objects, arguments, and more. In this section, we’ll discuss two additional inputs, global context and local context.

### Global context

In GraphQL Java, `GraphQLContext` is a mutable map containing arbitrary data, which is made available to every DataFetcher. It provides a “global context” per execution. In Spring for GraphQL, the global `GraphQLContext` can be accessed by adding it as a method parameter to a schema mapping handler or batch mapping method. In pure GraphQL Java, it can be accessed via `ExecutionInput.getGraphQLContext()`. For example, let’s say we want to make a “userId” accessible to every DataFetcher. In Spring for GraphQL, we can access `GraphQLContext` via a schema mapping or batch mapping method parameter and add a `userId`:

```
[](#cb228-1)@SchemaMapping
[](#cb228-2)MyType myField(GraphQLContext context) {
[](#cb228-3)  context.put("userId", 123);
[](#cb228-4)  // Your logic here
[](#cb228-5)}
```

It’s also possible to access and add to `GraphQLContext` via `ExecutionInput`. As we saw in the [Requests](#ch010.xhtml_intercepting-requests) chapter, Spring for GraphQL provides an interface for intercepting requests and accessing `ExecutionInput`.

```
[](#cb229-1)package myservice.service;
[](#cb229-2)
[](#cb229-3)import org.springframework.graphql.server.WebGraphQlInterceptor;
[](#cb229-4)import org.springframework.graphql.server.WebGraphQlRequest;
[](#cb229-5)import org.springframework.graphql.server.WebGraphQlResponse;
[](#cb229-6)import org.springframework.stereotype.Component;
[](#cb229-7)import reactor.core.publisher.Mono;
[](#cb229-8)
[](#cb229-9)@Component
[](#cb229-10)class UserIdInterceptor implements WebGraphQlInterceptor {
[](#cb229-11)
[](#cb229-12)  @Override
[](#cb229-13)  public Mono<WebGraphQlResponse> intercept(
[](#cb229-14)    WebGraphQlRequest request, Chain chain
[](#cb229-15)  ) {
[](#cb229-16)    request.configureExecutionInput((executionInput, builder) -> {
[](#cb229-17)      executionInput
[](#cb229-18)        .getGraphQLContext()
[](#cb229-19)        .put("userId", "123");
[](#cb229-20)      return executionInput;
[](#cb229-21)    });
[](#cb229-22)
[](#cb229-23)    return chain.next(request);
[](#cb229-24)  }
[](#cb229-25) 
[](#cb229-26)}
```

Retrieve the `userId` value by using the `@ContextValue` parameter, which retrieves a specific value from the `GraphQLContext` in schema mapping or batch mapping handlers.

```
[](#cb230-1)@SchemaMapping
[](#cb230-2)MyType myField(@ContextValue String userId) {
[](#cb230-3)  // Your logic here
[](#cb230-4)}
```

In pure GraphQL Java, we can add `userId` to `GraphQLContext` via `ExecutionInput` or via `DataFetchingEnvironment`:

```
[](#cb231-1)ExecutionInput executionInput = ...;
[](#cb231-2)executionInput.getGraphQLContext().put("userId", "123");
```

Note: the capitalisation of “L” is slightly different for the getter in `DataFetchingEnvironment`.

```
[](#cb232-1)DataFetcher df = (env) -> {
[](#cb232-2)    env.getGraphQlContext().put("userId", "123");
[](#cb232-3)    ...
[](#cb232-4)}
```

Retrieve the `userId` value via the `DataFetchingEnvironment`.

```
[](#cb233-1)DataFetcher df = (env) -> {
[](#cb233-2)    String userId = env.getGraphQlContext().get("userId");
[](#cb233-3)    ...
[](#cb233-4)}
```

### Local context

It’s also possible to set local context which only provides data to child DataFetchers, rather than changing global context.

A GraphQL request is a tree of fields and every field has an associated DataFetcher. Child DataFetchers are only invoked after the current DataFetcher finishes. We’ll discuss the tree of fields concept in more detail in the [Execution](#ch015.xhtml_fetching-data) chapter. Therefore, we can ensure that information set in local context will only be made accessible to child DataFetchers.

We can set the local context by returning a new `DataFetcherResult` where `localContext` is not null. We discussed how `DataFetcherResult` can be used to return data and errors in the [Errors](#ch011.xhtml_DataFetcherResult) chapter. Now we’ll show how it can also be used to set the local context.

For example, we have the following schema for customers and their orders.

```
[](#cb234-1)type Query {
[](#cb234-2)    order: Order
[](#cb234-3)    customerById(id: ID!): Customer
[](#cb234-4)}
[](#cb234-5)
[](#cb234-6)type Order {
[](#cb234-7)    id: ID
[](#cb234-8)    customer: Customer
[](#cb234-9)}
[](#cb234-10)
[](#cb234-11)type Customer {
[](#cb234-12)    id: ID
[](#cb234-13)    contact: Person
[](#cb234-14)}
[](#cb234-15)
[](#cb234-16)type Person {
[](#cb234-17)    name: String
[](#cb234-18)}
```

We can directly query a customer as a root field or via an order.

```
[](#cb235-1)query customerDetails {
[](#cb235-2)    customerById(id: "ID-1") {
[](#cb235-3)        contact { 
[](#cb235-4)            name 
[](#cb235-5)        } 
[](#cb235-6)    }
[](#cb235-7)}
```

or

```
[](#cb236-1)query orderDetails { 
[](#cb236-2)    order {
[](#cb236-3)        customer {
[](#cb236-4)            contact {
[](#cb236-5)                name
[](#cb236-6)            } 
[](#cb236-7)        }
[](#cb236-8)    }
[](#cb236-9)}
```

Add the following Java classes.

```
[](#cb237-1)package myservice.service;
[](#cb237-2)
[](#cb237-3)record Order(String id, String customerId) {
[](#cb237-4)}
```

```
[](#cb238-1)package myservice.service;
[](#cb238-2)
[](#cb238-3)record Customer(String id, String contactId) {
[](#cb238-4)}
```

```
[](#cb239-1)package myservice.service;
[](#cb239-2)
[](#cb239-3)record Person(String name) {
[](#cb239-4)}
```

Imagine that our persistence layer stores the full customer next to the order. That means, when we load an order, we have already loaded the full customer including their contact information. However, in our persistence layer, a customer loaded directly does not include the corresponding contact information.

For queries including the `order` field, we can avoid a second fetch for customer contact information by setting the local context when loading the `order` and make use of it in the customer `contact` DataFetcher.

In Spring for GraphQL, local context must be a `GraphQLContext` object, set by returning a `DataFetcherResult` in the `Query.order` DataFetcher. Note that this local instance of `GraphQLContext` is local to a DataFetcher and its children, it is different to the instance of `GraphQLContext` available globally.

We can retrieve the local context from the `DataFetchingEnvironment`. If the `Person` is in the context, we can reuse the information. Otherwise, we’ll make a request to the `Person` service for contact information.

In the example below, we have used placeholder data retrieval methods. Replace these methods with your logic. If you prefer to quickly test this end-to-end, you can mock these methods with in-memory objects.

```
[](#cb240-1)package myservice.service;
[](#cb240-2)
[](#cb240-3)import graphql.GraphQLContext;
[](#cb240-4)import graphql.execution.DataFetcherResult;
[](#cb240-5)import graphql.schema.DataFetchingEnvironment;
[](#cb240-6)import org.springframework.graphql.data.method.annotation
[](#cb240-7)  .Argument;
[](#cb240-8)import org.springframework.graphql.data.method.annotation
[](#cb240-9)  .QueryMapping;
[](#cb240-10)import org.springframework.graphql.data.method.annotation
[](#cb240-11)  .SchemaMapping;
[](#cb240-12)import org.springframework.stereotype.Controller;
[](#cb240-13)
[](#cb240-14)@Controller
[](#cb240-15)record OrderController(OrderService orderService,
[](#cb240-16)                       PersonService personService) {
[](#cb240-17) 
[](#cb240-18)  @QueryMapping
[](#cb240-19)  DataFetcherResult<Order> order() {
[](#cb240-20)    Order order = orderService.getOrder();
[](#cb240-21)    Person personForContact = order.getPersonForContact();
[](#cb240-22)    // Local instance of GraphQLContext
[](#cb240-23)    GraphQLContext localContext = GraphQLContext.newContext()
[](#cb240-24)      .put("personForContact", personForContact)
[](#cb240-25)      .build();
[](#cb240-26)    // Return data and a new local context
[](#cb240-27)    return DataFetcherResult.<Order>newResult()
[](#cb240-28)      .data(order)
[](#cb240-29)      .localContext(localContext)
[](#cb240-30)      .build();
[](#cb240-31)  }
[](#cb240-32)
[](#cb240-33)  @SchemaMapping
[](#cb240-34)  Customer customer(Order order) {
[](#cb240-35)    return orderService.getCustomer(order);
[](#cb240-36)  }
[](#cb240-37)
[](#cb240-38)  @SchemaMapping
[](#cb240-39)  Person contact(Customer customer, DataFetchingEnvironment env) {
[](#cb240-40)    GraphQLContext localContext = env.getLocalContext();
[](#cb240-41)    if (localContext != null 
[](#cb240-42)      && localContext.get("personForContact") instanceof Person) {
[](#cb240-43)      return localContext.get("personForContact");
[](#cb240-44)    }
[](#cb240-45)    return personService.getPerson(customer.contactId());
[](#cb240-46)  }
[](#cb240-47)
[](#cb240-48)  @QueryMapping
[](#cb240-49)  Customer customerById(@Argument String id) {
[](#cb240-50)    return orderService.getCustomerById(id);
[](#cb240-51)  }
[](#cb240-52)
[](#cb240-53)}
```

In this example, the `Person` is not guaranteed to be set in the local context. If a query is for customer details only, without an order, there will be no `personForContact` in the local context. As we cannot be sure if `personForContact` will be in the local context, we must access the local `GraphQLContext` via the `DataFetchingEnvironment` and then check if a `Person` has been set under the `personForContact` key.

If you are certain that the local context will always contain a particular key, you can pass in a parameter to the schema mapping method, annotated with `@LocalContextValue`. In this example, we could not use this annotation, as a runtime exception would be raised whenever `personForContact` is not set.

In pure GraphQL Java, the local context is also set via a `DataFetcherResult` in the `Query.order` DataFetcher. If using GraphQL Java without Spring for GraphQL, the object inserted into local context can be of any type, and does not have to be an instance of `GraphQLContext`.

```
[](#cb241-1)// DataFetcher for Query.order
[](#cb241-2)OrderService orderService;
[](#cb241-3)DataFetcher<DataFetcherResult<Order>> orderDf = (env) -> {
[](#cb241-4)  Order order = orderService.getOrder();
[](#cb241-5)  Person personForContact = order.getPersonForContact();
[](#cb241-6)  // Return data and a new local context
[](#cb241-7)  return DataFetcherResult.<Order>newResult()
[](#cb241-8)    .data(order)
[](#cb241-9)    .localContext(personForContact)
[](#cb241-10)    .build();
[](#cb241-11)};
```

Then the DataFetcher for `Customer.contact` can make use of the pre-loaded `Person` in local context, if it is available. If the `Person` is not available, a request to the `Person` service will be made.

```
[](#cb242-1)// DataFetcher for Customer.contact
[](#cb242-2)PersonService personService;
[](#cb242-3)DataFetcher<Person> contactDf = (env) -> {
[](#cb242-4)  // If we already loaded the person earlier
[](#cb242-5)  if (env.getLocalContext() instanceof Person) {
[](#cb242-6)        return env.getLocalContext();
[](#cb242-7)  }
[](#cb242-8)  Customer customer = env.getSource();
[](#cb242-9)  return personService.getPerson(customer.getContactId());
[](#cb242-10)};
```

## DataFetcher implementation patterns

There are a few considerations when implementing a DataFetcher:

*   Does it involve I/O? (e.g. HTTP calls to another service)
*   Is it computationally intensive?
*   Should it be reactive or not?

We will discuss these three patterns and when to use them. As the next few examples demonstrate DataFetcher patterns, we will show snippets rather than a full Spring for GraphQL controller.

#### Non-reactive DataFetcher

A non-reactive DataFetcher can involve blocking I/O or computation work. Regardless of the type of work, the structure is the same.

```
[](#cb243-1)@Controller
[](#cb243-2)record ThingController(DoSomeThing service) {
[](#cb243-3)    @SchemaMapping
[](#cb243-4)    MyType myField() {
[](#cb243-5)        return service.doSomething();
[](#cb243-6)    }
[](#cb243-7)}
```

Or the same DataFetcher in pure GraphQL Java:

```
[](#cb244-1)DoSomeThing service;
[](#cb244-2)DataFetcher<MyType> myField = (env) -> {
[](#cb244-3)    return service.doSomething();
[](#cb244-4)};
```

This is the most straightforward pattern. If you are developing a non-reactive service, this is the only pattern you need.

In a reactive service, this is still a valid option if the work is only fast computation work, meaning no I/O is involved. The exact definition of “fast” is domain-specific, but as a rough guide, “fast” would be work that takes less than one millisecond to complete.

#### Wrapping blocking I/O

If the DataFetcher involves blocking I/O, we can offload the blocking call to another thread.

In pure GraphQL Java, it could look like:

```
[](#cb245-1)Executor threadPool;
[](#cb245-2)DataFetcher<CompletableFuture<MyType> df = (env) -> {
[](#cb245-3)  return CompletableFuture.supplyAsync(
[](#cb245-4)    () -> client.blockingCall(),
[](#cb245-5)    threadPool);
[](#cb245-6)};
```

Although wrapping an I/O call does not make the whole service completely reactive, it may still be worth doing as it doesn’t block GraphQL Java itself and allows for parallel fetching of fields.

In Spring for GraphQL, we recommend using a reactive approach with Reactor rather than using Java’s `CompletableFuture`. As we’ll see [later in this chapter](#ch013.xhtml_reactor-support), Reactor DataFetchers in Spring for GraphQL are available without any additional code or configuration. Using Reactor DataFetchers also enables the use of Reactor context.

#### Reactive I/O

A reactive DataFetcher usually involves using a reactive library such as [Async Http Client](https://github.com/AsyncHttpClient/async-http-client) or [Spring WebClient](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/reactive/function/client/WebClient.html). While the library details may vary, essentially it involves calling the library and returning a `CompletableFuture`.

```
[](#cb246-1)ReactiveClient client;
[](#cb246-2)DataFetcher<CompletableFuture<Something> df = (env) -> {
[](#cb246-3)  return client.call();
[](#cb246-4)};
```

This pattern should be used in a reactive service every time I/O is involved.

#### Reactive compute work

Reactive compute work requires a bit more effort compared to the previous example, as it requires offloading the actual work onto another thread.

The main pattern looks like this:

```
[](#cb247-1)Executor threadPool;
[](#cb247-2)DataFetcher<CompletableFuture<Something> df = (env) -> {
[](#cb247-3)  return CompletableFuture.supplyAsync(
[](#cb247-4)    () -> client.call(),
[](#cb247-5)    threadPool);
[](#cb247-6)};
```

This ensures that the compute-intense work is completed in a separate thread, so it does not block GraphQL Java.

In Spring for GraphQL, we recommend using a reactive approach with Reactor rather than using Java’s `CompletableFuture`, we’ll discuss this [later in this chapter](#ch013.xhtml_reactor-support).

#### Reactive or not?

Whether to use reactive patterns is a general question, which is not specific to GraphQL. Here are some high-level considerations to keep in mind.

The main tradeoff is between improved scalability or more complicated code. A reactive service is more stable and predictable under load than a non-reactive one. If you are going to run a service with a high load that also needs to be very stable, reactive is our recommendation.

However, it comes with the cost of maintaining and running a reactive code base. Reactive is not a concept inherent to the Java language itself. The concept was added later via `CompletableFuture` and other libraries such as Reactor. The cost is code that is not as simple to read, write, and debug as “normal” Java code.

A critical consideration is that everything must be reactive in order to achieve the full benefits of a reactive code base. This means that if your HTTP client inside a DataFetcher is not reactive, you can’t make that DataFetcher fully reactive. The following example may seem to make sense at first glance, but it is not a suitable solution.

```
[](#cb248-1)RestTemplate restTemplate;
[](#cb248-2)URI url;
[](#cb248-3)Executor threadPool;
[](#cb248-4)
[](#cb248-5)DataFetcher<CompletableFuture<MyType> df = (env) -> {
[](#cb248-6)    return CompletableFuture.supplyAsync(
[](#cb248-7)    () -> restTemplate.getForObject(url, MyType.class), // blocking call
[](#cb248-8)    threadPool);
[](#cb248-9)};
```

This DataFetcher returns a `CompletableFuture`, but it actually does a blocking call via the [Spring RestTemplate](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/client/RestTemplate.html) HTTP client, which is a blocking call. Whilst this does not block the GraphQL Java engine directly, there is still a thread being blocked by the `.getObject` call. This means we will not achieve the full benefits of a reactive service.

## Spring for GraphQL Reactor support

Spring WebFlux is an asynchronous and non-blocking framework based on [Reactor](https://projectreactor.io/docs/core/release/reference/index.html#intro-reactive). You can use Spring WebFlux together with Spring for GraphQL to build Reactor DataFetchers.

Spring for GraphQL supports the Reactor types `Mono` and `Flux` as return values, which enables us to write reactive DataFetchers. If the words `Mono` and `Flux` are new to you, please see the [Reactor documentation](https://projectreactor.io/docs/core/release/reference/index.html#core-features).

We recommend using the Reactor types `Mono` and `Flux` rather than Java’s `CompletableFuture` with Spring for GraphQL to make use of Reactor context. However, it is still possible to return `CompletableFuture` values.

To use Spring WebFlux, include `org.springframework.boot:spring-boot-starter-webflux` as a dependency. We previously walked through how to use Spring WebFlux in the [Building a GraphQL service chapter](#ch008.xhtml_webflux-or-webmvc).

No additional code nor configuration is required to make use of Reactor. Simply write a DataFetcher that returns a Reactor type. For example:

```
[](#cb249-1)@SchemaMapping(type = "Foo", field = "bar")
[](#cb249-2)Mono<String> bar() {
[](#cb249-3)  ...
[](#cb249-4)}
[](#cb249-5)
[](#cb249-6)or
[](#cb249-7)
[](#cb249-8)@SchemaMapping(type = "Foo", field = "bar")
[](#cb249-9)Flux<String> bar() {
[](#cb249-10)  ...
[](#cb249-11)}
```

To see more examples of DataFetchers returning Reactor types, see the examples in the [Building a GraphQL service](#ch008.xhtml_fetching-data-external) chapter.

One challenge when using Reactor with GraphQL Java is that GraphQL Java itself is based on `CompletableFuture`. Spring for GraphQL manages conversion between Reactor types and `CompletableFuture`. To prevent the [Reactor Context](https://projectreactor.io/docs/core/release/reference/#context) from being lost between conversions to and from `CompletableFuture`, Spring for GraphQL saves and restores the Reactor context across different DataFetcher invocations.

For example, if we want to propagate a logging prefix via Reactor context:

```
[](#cb250-1)package myservice.service;
[](#cb250-2)
[](#cb250-3)import org.springframework.graphql.server.WebGraphQlInterceptor;
[](#cb250-4)import org.springframework.graphql.server.WebGraphQlRequest;
[](#cb250-5)import org.springframework.graphql.server.WebGraphQlResponse;
[](#cb250-6)import org.springframework.stereotype.Component;
[](#cb250-7)import reactor.core.publisher.Mono;
[](#cb250-8)import reactor.util.context.Context;
[](#cb250-9)
[](#cb250-10)// Set initial values for the Reactor context
[](#cb250-11)@Component
[](#cb250-12)class WebInterceptor implements WebGraphQlInterceptor {
[](#cb250-13)
[](#cb250-14)  @Override
[](#cb250-15)  public Mono<WebGraphQlResponse> intercept(WebGraphQlRequest request,
[](#cb250-16)                                            Chain chain) {
[](#cb250-17)    return chain.next(request)
[](#cb250-18)      .contextWrite(Context.of("loggingPrefix", "123"));
[](#cb250-19)  }
[](#cb250-20) 
[](#cb250-21)}
```

For more details about `WebGraphQlInterceptor`, see the intercepting requests section in the [Requests](#ch010.xhtml_intercepting-requests) chapter.

Every DataFetcher and any other code called by a DataFetcher can access the prefix.

```
[](#cb251-1)@QueryMapping
[](#cb251-2)Mono<String> foo() {
[](#cb251-3)  return Mono.deferContextual(contextView -> {
[](#cb251-4)    String loggingPrefix = contextView.get("loggingPrefix");
[](#cb251-5)    return Mono.just(loggingPrefix);
[](#cb251-6)  });
[](#cb251-7)}
```

In this chapter we covered more advanced details about DataFetchers, including how to make use of global and local context, and reactive patterns. We also discussed how to use Reactor types with Spring for GraphQL.

# Directives

Directives are a powerful feature of GraphQL that allows us to declare any kind of additional data to a schema or document. This data can be used to change runtime execution or type validation behavior.

In this advanced chapter, we will discuss directives in depth and demonstrate use cases for directives.

## Schema and operation directives

There are two broad categories of directives, schema and operation directives. Schema directives are used on schema elements, and operation directives are used in operations within a [GraphQL document](#ch006.xhtml_graphql-document).

Schema and operation directives have a name starting with `@`, followed by an optional list of arguments in parentheses. For example, here is the built-in `@deprecated` schema directive which is used to indicate deprecated schema elements.

```
[](#cb252-1)type Query {
[](#cb252-2)    search: String @deprecated(reason: "Too slow, please use searchFast")
[](#cb252-3)    searchFast: String
[](#cb252-4)}
```

Every directive has a schema definition. As `@deprecated` is a built-in directive, this definition is automatically added by every GraphQL implementation. You should not manually add this definition to your schema.

```
[](#cb253-1)directive @deprecated(reason: String = "No longer supported") 
[](#cb253-2) on FIELD_DEFINITION | ARGUMENT_DEFINITION | INPUT_FIELD_DEFINITION 
[](#cb253-3)    | ENUM_VALUE
```

Schema and operation directive definitions have a name starting with `@`, an optional list of arguments in parentheses, followed by `on` and a list of allowed locations where it can be used, separated by `|`. Schema and operation directive definitions are declared in the schema.

The allowed locations will determine whether this directive is a schema or operation directive. For example, a directive on a `FIELD_DEFINITION` is a schema directive, whereas a directive on a `FIELD` is an operation directive. We’ll discuss the full list of locations for schema and operation directives later in this chapter when we create our own directives.

The GraphQL spec defines four built-in directives: `@skip`, `@include`, `@deprecated` and `@specifiedBy`. `@skip` and `@include` are operation directives, whereas `@deprecated` and `@specifiedBy` are schema directives. You can also create your own schema and operation directives, which we’ll cover in this chapter.

## Built-in directives

The GraphQL spec defines four built-in directives, which must be supported by all GraphQL implementations. Built-in directives can be used without being declared. Later in this chapter, we’ll see how to declare and implement our own directives.

### `@skip` and `@include`

`@skip` and `@include` are operation directives that allow us to skip or include certain fields during execution.

You should not declare these built-in directives in your schema. To illustrate how they can be used, this is how `@skip` and `@include` are defined:

```
[](#cb254-1)directive @skip(if: Boolean!) 
[](#cb254-2)  on FIELD | FRAGMENT_SPREAD | INLINE_FRAGMENT
[](#cb254-3)directive @include(if: Boolean!) 
[](#cb254-4)  on FIELD | FRAGMENT_SPREAD | INLINE_FRAGMENT
```

The `if` argument is a Boolean indicating whether the `@skip` or `@include` directive is active. The exclamation mark `!` indicates that this argument is non-nullable.

Skipping (or not including) a field is like a request that doesn’t contain this field at all. These queries produce the same result:

```
[](#cb255-1)query myPets {
[](#cb255-2)    pets {
[](#cb255-3)        name
[](#cb255-4)    }
[](#cb255-5)}
[](#cb255-6)
[](#cb255-7)# same as:
[](#cb255-8)query myPets2 {
[](#cb255-9)    pets {
[](#cb255-10)        name
[](#cb255-11)        age @skip(if: true)
[](#cb255-12)    }
[](#cb255-13)}
[](#cb255-14)
[](#cb255-15)# same as:
[](#cb255-16)query myPets3 {
[](#cb255-17)    pets {
[](#cb255-18)        name
[](#cb255-19)        age @include(if: false)
[](#cb255-20)    }
[](#cb255-21)}
```

To be more useful, `@skip` and `@include` should be combined with variables rather than hard coded booleans. For example, we could include an experimental field based on a variable value:

```
[](#cb256-1)query myQuery($someTest: Boolean!) {
[](#cb256-2)    experimentalField @include(if: $someTest)
[](#cb256-3)}
```

### `@deprecated`

`@deprecated` is a schema directive that can be used to mark fields, enum values, input fields, and arguments as deprecated in the schema. It provides a structured way to document deprecations. By default, the introspection API filters out deprecated schema elements.

As `@deprecated` is a built-in directive, you should not declare it in your schema. To illustrate how `@deprecated` is used, this is how it is defined:

```
[](#cb257-1)directive @deprecated(reason: String = "No longer supported") 
[](#cb257-2)  on FIELD_DEFINITION | ARGUMENT_DEFINITION | INPUT_FIELD_DEFINITION 
[](#cb257-3)    | ENUM_VALUE
```

You can optionally provide a `reason` for deprecation, which will appear in automatically generated documentation and tooling. The default `reason` is “No longer supported”.

This is an example of how to mark fields and enums as deprecated in the schema:

```
[](#cb258-1)type Query {
[](#cb258-2)    search: String @deprecated(reason: "Too slow, please use searchFast")
[](#cb258-3)    searchFast: String
[](#cb258-4)}
[](#cb258-5)
[](#cb258-6)enum Format {
[](#cb258-7)    LEGACY @deprecated(reason: "Legacy format")
[](#cb258-8)    NEW
[](#cb258-9)}
```

The `@deprecated` directive is used to automatically generate documentation. For example, this is how the schema above appears in the documentation tab of GraphiQL. Click on the book icon in the top left corner of the page, as shown in the screenshot “Deprecated documentation in GraphiQL”.

![Deprecated documentation in GraphiQL](media/file14.png)

Deprecated documentation in GraphiQL

### `@specifiedBy`

`@specifiedBy` allows us to provide a scalar specification URL to describe the behavior of custom scalar types.

[Custom scalars](#ch005.xhtml_scalar) are a powerful feature of GraphQL which enables the type system to be extended. Initially in the GraphQL specification, custom scalars could only be defined in the schema by name. For example:

```
[](#cb259-1)scalar DateTime
```

And this is still a valid way to define custom scalars in a schema. However, only a name in the schema is not enough to explain the behaviour of custom scalars. For example, `DateTime` implementations can vary across services, but they might both contain a schema element with the same name `DateTime`. The `@specifiedBy` directive was introduced later to provide a way to clearly document the behavior of custom scalars. The provided URL should link to a specification including data format, serialization, and coercion rules. For the full details and specification templates, see the [GraphQL Scalars project](https://scalars.graphql.org/).

We recommend using `@specifiedBy` to clearly describe your custom scalar. However, using this directive with custom scalars is not compulsory.

As `@specifiedBy` is a built-in directive, you should not declare it in your schema. To illustrate how `@specifiedBy` is used, this is how it is defined:

```
[](#cb260-1)directive @specifiedBy(url: String!) on SCALAR
```

This is an example for a `DateTime` scalar:

```
[](#cb261-1)scalar DateTime @specifiedBy(url: 
[](#cb261-2)    "https://scalars.graphql.org/andimarek/date-time")
```

With the [GraphQL Scalars](https://scalars.graphql.org/) project, you can create your own custom scalars specifications and host them on the GraphQL Foundation’s `scalars.graphql.org` domain, like the linked URL in the previous example. You can also read and link to other contributed specifications. See the [GraphQL Scalars](https://scalars.graphql.org/) project for more information.

## Defining your own schema and operation directives

Schema and operation directives have a name starting with `@`, an optional list of arguments in parentheses, followed by `on` and a list of allowed locations where it can be used. The allowed locations determine whether the directive is an operation directive or schema directive. When creating your own schema and operation directives, they must be defined in the schema.

It’s important to understand that **all custom schema and operation directives don’t have any effect until we implement the custom behavior**. We’ll first discuss how to define schema and operation directives, then how to implement them.

## Defining schema directives

Let’s walk through some examples. Let’s create an `@important` directive. The directive can only be used on field definitions, which makes it a schema directive:

```
[](#cb262-1)# No arguments and can only be used on field definitions
[](#cb262-2)directive @important on FIELD_DEFINITION
```

Our new `@important` directive can be used to indicate certain schema fields are important.

```
[](#cb263-1)type Query {
[](#cb263-2)    hello: String @important # usage of the directive
[](#cb263-3)}
```

We have defined the `@important` directive to only be allowed on fields inside the schema. Other locations will be invalid, for example:

```
[](#cb264-1)# No arguments and can only be used on field definitions
[](#cb264-2)directive @important on FIELD_DEFINITION
```

```
[](#cb265-1)type Query @important { # Invalid usage
[](#cb265-2)    hello: String
[](#cb265-3)}
```

By using the directive on the Query type, we have created an invalid schema.

To make this a valid schema, we could add another location to the directive definition. Provide multiple locations by separating them with `|`.

```
[](#cb266-1)# Can be used in two locations
[](#cb266-2)directive @important on FIELD_DEFINITION | OBJECT
[](#cb266-3)
[](#cb266-4)type Query @important { # Now it is valid
[](#cb266-5)    hello: String
[](#cb266-6)}
```

All custom schema and operation directives don’t have any effect until we implement new custom behavior. The `@important` directive won’t have any effect until we implement new logic, which we’ll cover later in this chapter. This differs from the built-in directives, which all have a well-defined effect.

The difference between schema directives and operation directives is the list of allowed locations. Here is an example of a schema directive `@foo` with all possible eleven locations in a schema.

```
[](#cb267-1)type @foo on SCHEMA | SCALAR | OBJECT |
[](#cb267-2)FIELD_DEFINITION | ARGUMENT_DEFINITION | INTERFACE |
[](#cb267-3)| UNION | ENUM | ENUM_VALUE | INPUT_OBJECT | INPUT_FIELD_DEFINITION
[](#cb267-4)
[](#cb267-5)schema @foo { # Schema
[](#cb267-6)    query: Query
[](#cb267-7)}
[](#cb267-8)
[](#cb267-9)scalar CustomScalar @foo # Scalar
[](#cb267-10)
[](#cb267-11)type Query @foo { # Object
[](#cb267-12)    hello(
[](#cb267-13)        arg: SomeInput @foo # Argument
[](#cb267-14)    ): String @foo # Field definition
[](#cb267-15)}
[](#cb267-16)
[](#cb267-17)interface SomeInterface @foo { # Interface
[](#cb267-18)    hello: String
[](#cb267-19)}
[](#cb267-20)
[](#cb267-21)type SomeImplementation implements SomeInterface  {
[](#cb267-22)    hello: String
[](#cb267-23)}
[](#cb267-24)
[](#cb267-25)union SomeUnion = SomeImplementation @foo # Union
[](#cb267-26)
[](#cb267-27)enum SomeEnum @foo { # Enum
[](#cb267-28)    ENUM_VALUE @foo # Enum value
[](#cb267-29)}
[](#cb267-30)
[](#cb267-31)input SomeInput @foo {  # Input object
[](#cb267-32)  inputField: String @foo # Input field
[](#cb267-33)}
```

Whilst it is technically possible to define a directive that includes locations for both schema and operation directives, in practice this is not common.

### Defining operation directives

Let’s define an operation directive `@cache`, which can be used on operation fields. Note that `FIELD` in the example below refers to operation fields, and `FIELD_DEFINITION` used in the previous schema directive example refers to schema fields.

```
[](#cb268-1)# Can only be used on a field in a GraphQL document
[](#cb268-2)directive @cache on FIELD
[](#cb268-3)
[](#cb268-4)type Query {
[](#cb268-5)    pet: Pet
[](#cb268-6)}
[](#cb268-7)
[](#cb268-8)type Pet {
[](#cb268-9)    name: String
[](#cb268-10)    lastTimeOutside: String
[](#cb268-11)}
```

We can only use this `@cache` directive on fields in a GraphQL document, which contains operations.

```
[](#cb269-1)query myPet {
[](#cb269-2)    pet {
[](#cb269-3)        name
[](#cb269-4)        lastTimeOutside @cache
[](#cb269-5)    }
[](#cb269-6)}
```

Directives can also have arguments. Let’s add a `maxAge` argument, with a default value of 1000.

```
[](#cb270-1)# Argument with a default value
[](#cb270-2)directive @cache(maxAge: Int = 1000) on FIELD
```

In a GraphQL document, we could use our updated `@cache` directive to specify a maxAge value:

```
[](#cb271-1)query myPet {
[](#cb271-2)    pet {
[](#cb271-3)        name
[](#cb271-4)        lastTimeOutside @cache(maxAge: 500)
[](#cb271-5)    }
[](#cb271-6)}
```

All custom schema and operation directives don’t have any effect until we implement new custom behavior. For example, the operation above where `lastTimeOutside` has a `@cache` directive behaves exactly the same as without it, until we have implemented some new logic. We’ll demonstrate implementation of behavior for directives later in this chapter. You don’t need to define behaviour for the built-in directives, which all have a well-defined effect that is implemented by every GraphQL implementation.

The difference between schema directives and operation directives is the list of allowed locations. Here is an operation directive with all possible eight locations in a GraphQL document, which contains operations.

```
[](#cb272-1)type @foo on QUERY | MUTATION | SUBSCRIPTION |
[](#cb272-2)  FIELD | FRAGMENT_DEFINITION | FRAGMENT_SPREAD |
[](#cb272-3)  INLINE_FRAGMENT | VARIABLE_DEFINITION
[](#cb272-4)
[](#cb272-5)query someQuery(
[](#cb272-6)    $var: String @foo # Variable definition
[](#cb272-7)    ) @foo # Query
[](#cb272-8)    {
[](#cb272-9)        field @foo  # Field
[](#cb272-10)        ... on Query @foo { # Inline fragment
[](#cb272-11)            field
[](#cb272-12)        }
[](#cb272-13)        ...someFragment @foo # Fragment spread
[](#cb272-14)}
[](#cb272-15)
[](#cb272-16)fragment someFragment @foo { # Fragment
[](#cb272-17)    field
[](#cb272-18)}
[](#cb272-19)
[](#cb272-20)mutation someMutation @foo { # Mutation
[](#cb272-21)    field
[](#cb272-22)}
[](#cb272-23)
[](#cb272-24)subscription someSubscription @foo { # Subscription
[](#cb272-25)    field
[](#cb272-26)}
```

Although it is technically possible to define a directive that includes locations associated with schema and operation directives, in practice this is not common.

## Repeatable directives

We can define schema and operation directives as `repeatable`, enabling it to be used multiple times in the same location. If `repeatable` is not included in the directive definition, the directive will be non-repeatable by default.

For example, a repeatable schema directive `@owner`:

```
[](#cb273-1)directive @owner(name: String!) repeatable on FIELD_DEFINITION
[](#cb273-2)
[](#cb273-3)type Query {
[](#cb273-4)    # Multiple owners per field possible
[](#cb273-5)    hello: String @owner(name: "Brian") @owner(name: "Josh")
[](#cb273-6)}
```

## Implementing logic for schema directives

To create a new schema directive, we have to define the directive and implement the logic for it.

As this is an advanced chapter, the code examples which follow are more complicated and involve schema traversal and transformation.

### Changing execution logic with schema directives

Let’s implement the logic for a new `@important` directive, which indicates which schema fields are important, and the reason for its importance. It is defined as:

```
[](#cb274-1)directive @important(reason: String!) on FIELD_DEFINITION
```

And could be used in a schema on a field:

```
[](#cb275-1)type Query {
[](#cb275-2)    hello: String @important(reason: "Being friendly")
[](#cb275-3)}
```

To explain how schema directive definition and usage are represented in code, we will walk through sample code with pure GraphQL Java. Then we’ll wrap up this section with an implementation for `@important` in Spring for GraphQL.

Schemas are represented as an instance of `GraphQLSchema` inside GraphQL Java. A `GraphQLSchema` instance will contain a `GraphQLDirective` instance representing a schema directive’s declaration.

In pure GraphQL Java, we could access this `GraphQLDirective` instance via `GraphQLSchema.getDirective`, which contains the name, arguments, valid locations, and whether the directive is repeatable. In this example `schema` is the name of an instance of `GraphQLSchema`.

```
[](#cb276-1)GraphQLDirective importantDirective = schema.getDirective("important");
[](#cb276-2)String name = importantDirective.getName();
[](#cb276-3)List<GraphQLArgument> arguments = importantDirective.getArguments();
[](#cb276-4)boolean repeatable = importantDirective.isRepeatable();
[](#cb276-5)EnumSet<Introspection.DirectiveLocation> directiveLocations =
[](#cb276-6)  importantDirective.validLocations();
```

`GraphQLDirective` represents the definition of a directive, and `GraphQLArgument` represents an argument definition.

Then we have an instance of `GraphQLAppliedDirective`, which represents the usage of the directive in a schema. In our example, we only have one usage.

In pure GraphQL Java, usage of our schema directive can be accessed via our instance of `GraphQLSchema` called `schema`:

```
[](#cb277-1)GraphQLSchema schema = ...;
[](#cb277-2)GraphQLObjectType query = schema.getObjectType("Query");
[](#cb277-3)GraphQLFieldDefinition hello = query.getFieldDefinition("hello");
[](#cb277-4)GraphQLAppliedDirective appliedDirective 
[](#cb277-5)        = hello.getAppliedDirective("important");
[](#cb277-6)GraphQLAppliedDirectiveArgument reason 
[](#cb277-7)        = appliedDirective.getArgument("reason");
[](#cb277-8)String reasonValue = reason.getValue(); // "Being friendly"
```

In our example, the `GraphQLAppliedDirective` contains one `GraphQLAppliedDirectiveArgument` for our one argument “reason” with the value “Being friendly”. To highlight the difference, an instance of `GraphQLDirective` has `GraphLArgument`s, and `GraphQLAppliedDirective` has `GraphQLAppliedDirectiveArgument`s. `GraphQLDirective` represents the definition, and `GraphQLAppliedDirective` represents the usage of the directive in the schema.

In practice, we often use schema directives inside a DataFetcher. For example, we could use the `@important` directive like this in a Spring for GraphQL DataFetcher to change how important fields are handled:

```
[](#cb278-1)package myservice.service;
[](#cb278-2)
[](#cb278-3)import graphql.schema.DataFetchingEnvironment;
[](#cb278-4)import graphql.schema.GraphQLAppliedDirective;
[](#cb278-5)import graphql.schema.GraphQLFieldDefinition;
[](#cb278-6)import org.springframework.graphql.data.method.annotation
[](#cb278-7)  .QueryMapping;
[](#cb278-8)import org.springframework.stereotype.Controller;
[](#cb278-9)
[](#cb278-10)@Controller
[](#cb278-11)class GreetingController {
[](#cb278-12)  @QueryMapping
[](#cb278-13)  String hello(DataFetchingEnvironment env) {
[](#cb278-14)    GraphQLFieldDefinition fieldDefinition = env.getFieldDefinition();
[](#cb278-15)    GraphQLAppliedDirective important
[](#cb278-16)      = fieldDefinition.getAppliedDirective("important");
[](#cb278-17)    if (important != null) {
[](#cb278-18)      return handleImportantFieldsDifferently(env);
[](#cb278-19)    }
[](#cb278-20)    return "Hello";
[](#cb278-21)  }
[](#cb278-22)}
```

### Validation with schema directives

Directives can also be used for validation. For example, a `@size` schema directive for arguments, which enforces a minimum quantity.

```
[](#cb279-1)directive @size(min : Int = 0) on ARGUMENT_DEFINITION
```

It could be applied to an argument definition to validate if there are enough `Application`s in the input:

```
[](#cb280-1)type Query {
[](#cb280-2)    hired(applications : [Application!] @size(min : 3)) : [Boolean]
[](#cb280-3)}
```

Validation is such a useful and commonly requested idea that there is an [extended validation library](https://github.com/graphql-java/graphql-java-extended-validation) for GraphQL Java, which is maintained by the GraphQL Java team.

To use the validation directives in the graphql-java-extended-validation library, add the package.

For Gradle, add this to your `build.gradle` file:

```
[](#cb281-1)implementation 'com.graphql-java:graphql-java-extended-validation:19.1'
```

For Maven:

```
[](#cb282-1)<dependency>
[](#cb282-2)  <groupId>com.graphql-java</groupId>
[](#cb282-3)  <artifactId>graphql-java-extended-validation</artifactId>
[](#cb282-4)  <version>19.1</version>
[](#cb282-5)</dependency>
```

Note: the major version number corresponds to the linked major version of the main GraphQL Java release. At the time of writing, the latest version of Spring for GraphQL 1.1.2, uses GraphQL Java 19.

To wire these validation directives in Spring for GraphQL, create a `RuntimeWiringConfigurer` bean. This will add a default selection of directive implementations from graphql-java-extended-validation. You should separately define the directives for your service in your schema.

```
[](#cb283-1)@Configuration
[](#cb283-2)class GraphQlConfig {
[](#cb283-3)    @Bean
[](#cb283-4)    RuntimeWiringConfigurer runtimeWiringConfigurer() {
[](#cb283-5)        // Adds all default validation rules in library
[](#cb283-6)        ValidationRules possibleRules 
[](#cb283-7)            = ValidationRules.newValidationRules().build();
[](#cb283-8)        // ValidationSchemaWiring implements SchemaDirectiveWiring
[](#cb283-9)        ValidationSchemaWiring validationDirectiveWiring 
[](#cb283-10)            = new ValidationSchemaWiring(possibleRules);
[](#cb283-11)        return wiringBuilder -> wiringBuilder
[](#cb283-12)                .directiveWiring(validationDirectiveWiring);
[](#cb283-13)    }
[](#cb283-14)}
```

The Spring Boot starter automatically detects all `RuntimeWiringConfigurer` beans.

### Adding metadata with schema directives

Another very common use case of schema directives is providing metadata, which does not change execution but is only relevant for the schema itself.

For example, we work in a large team and we want to document the ownership of certain types with an `@owner` directive:

```
[](#cb284-1)directive @owner(name: String) on OBJECT
[](#cb284-2)
[](#cb284-3)type User @owner(name: "Antoine") {
[](#cb284-4)    # More fields here
[](#cb284-5)}
[](#cb284-6)
[](#cb284-7)type Order @owner(name: "Felipe") {
[](#cb284-8)    # More fields here
[](#cb284-9)}
[](#cb284-10)
[](#cb284-11)type Payment @owner(name: "Stephan") {
[](#cb284-12)    # More fields here
[](#cb284-13)}
```

A significant benefit of using directives is the ability to process them programmatically. For example, we could create an automatic report, showing which types are owned by whom. This ownership report example is more like a script rather than part of a Spring for GraphQL service. Therefore, we’ll demonstrate this example in pure GraphQL Java.

GraphQL Java provides tools to programmatically visit schema elements. In pure GraphQL Java code, we can map owners to types with the `SchemaTraverser` class, together with a `GraphQLTypeVisitor`. In this example, we will visit `GraphQLObjectType`s. There are many more options and hooks to customize visitors in GraphQL Java.

```
[](#cb285-1)GraphQLSchema schema = ...;
[](#cb285-2)Map<String, List<GraphQLObjectType>> ownerToTypes
[](#cb285-3)  = new LinkedHashMap<>();
[](#cb285-4)
[](#cb285-5)SchemaTraverser schemaTraverser = new SchemaTraverser();
[](#cb285-6)schemaTraverser.depthFirstFullSchema(new GraphQLTypeVisitorStub() {
[](#cb285-7)  @Override
[](#cb285-8)  public TraversalControl visitGraphQLObjectType(
[](#cb285-9)    GraphQLObjectType objectType,
[](#cb285-10)    TraverserContext<GraphQLSchemaElement> context
[](#cb285-11)  ) {
[](#cb285-12)    GraphQLAppliedDirective directive
[](#cb285-13)      = objectType.getAppliedDirective("owner");
[](#cb285-14)    if (directive != null) {
[](#cb285-15)      String owner = directive.getArgument("name").getValue();
[](#cb285-16)      ownerToTypes.putIfAbsent(owner, new ArrayList<>());
[](#cb285-17)      ownerToTypes.get(owner).add(objectType);
[](#cb285-18)    }
[](#cb285-19)    return TraversalControl.CONTINUE;
[](#cb285-20)  }
[](#cb285-21)}, schema);
```

We visit every `GraphQLObjectType` in the schema, and check the owner of each object type. We then assemble a map of the owner to a list of object types.

This `@owner` example was more like a script rather than core functionality in a Spring for GraphQL service. However, if you want to traverse a schema in Spring for GraphQL, you can register `graphql.schema.GraphQLTypeVisitor` via the `GraphQlSource.builder` with `builder.schemaResources(..).typeVisitors(..)`.

Taking a step further, we can even change the global `GraphQLSchema` with schema directives. For example, we could automatically add a suffix to every field based on a directive.

```
[](#cb286-1)directive @suffix(name: String) on OBJECT
[](#cb286-2)
[](#cb286-3)type Dog @suffix(name:"__bark") {
[](#cb286-4)    name: String
[](#cb286-5)}
[](#cb286-6)
[](#cb286-7)type Cat @suffix(name: "__meow") {
[](#cb286-8)    name: String
[](#cb286-9)}
```

With pure GraphQL Java, we can make use of schema transformer and type visitor tools.

```
[](#cb287-1)GraphQLSchema newSchema = SchemaTransformer.transformSchema(
[](#cb287-2)  schema, new GraphQLTypeVisitorStub() {
[](#cb287-3)
[](#cb287-4)  @Override
[](#cb287-5)  public TraversalControl visitGraphQLFieldDefinition(
[](#cb287-6)    GraphQLFieldDefinition fieldDefinition,
[](#cb287-7)    TraverserContext<GraphQLSchemaElement> context
[](#cb287-8)  ) {
[](#cb287-9)    GraphQLSchemaElement parentNode = context.getParentNode();
[](#cb287-10)    if (!(parentNode instanceof GraphQLObjectType)) {
[](#cb287-11)      return TraversalControl.CONTINUE;
[](#cb287-12)    }
[](#cb287-13)    GraphQLObjectType objectType = (GraphQLObjectType) parentNode;
[](#cb287-14)    GraphQLAppliedDirective directive = objectType
[](#cb287-15)      .getAppliedDirective("suffix");
[](#cb287-16)
[](#cb287-17)    if (directive != null) {
[](#cb287-18)      String suffix = directive.getArgument("name").getValue();
[](#cb287-19)      GraphQLFieldDefinition newFieldDefinition
[](#cb287-20)        = fieldDefinition.transform(builder 
[](#cb287-21)          -> builder.name(fieldDefinition.getName() + suffix));
[](#cb287-22)      return changeNode(context, newFieldDefinition);
[](#cb287-23)    }
[](#cb287-24)
[](#cb287-25)    return TraversalControl.CONTINUE;
[](#cb287-26)  }
[](#cb287-27)});
```

We are using the `SchemaTransformer` class to change a schema whilst traversing it. `SchemaTransformer` leverages the same `GraphQLTypeVisitor` as the `SchemaTraverser` used in the previous example.

We visit every field definition and try to get the object containing the field via `context.getParentNode()`. Then we get the `GraphQLAppliedDirective` for the suffix. We use this to create a `GraphQLFieldDefinition` with the changed name. The last thing to do is to call `changeNode` (from `GraphQLTypeVisitor`) which actually changes the field.

To use this same schema transformation example in Spring for GraphQL, register a `graphql.schema.GraphQLTypeVisitor` via the `GraphQlSource.Builder` with `builder.schemaResources(..).typeVisitorsToTransformSchema(..)`.

A word of caution: as you can see from this code example, transforming a schema is not trivial. Be careful not to inadvertently create an invalid schema during schema transformation. To view a more complex example, please see `graphql.util.Anonymizer` in GraphQL Java. This is a utility to help users of GraphQL Java anonymize their schemas to provide realistic examples when reporting issues or suggesting improvements to the maintainer team.

## Implementing logic for operation directives

Operation directives are used with GraphQL operations. Note that this concept is also often referred to as “query” directives, although this type of directive can be used on all three operations: queries, mutations, and subscriptions.

Let’s implement the logic for a `@cache` operation directive:

```
[](#cb288-1)directive @cache(maxAge: Int) on FIELD
```

This is an operation directive that enables clients to specify how recent cache entries must be. This is an example of an operation directive that can change execution.

For example, a client specifies that `hello` cache entries must not be older than 500 ms, otherwise we re-fetch these entries.

```
[](#cb289-1)query caching {
[](#cb289-2)    hello @cache(maxAge: 500)
[](#cb289-3)}
```

In GraphQL Java, operation directive definitions are represented as `GraphQLDirective`s. Operation directive usages are represented as `QueryAppliedDirective`s. Note that the word “query” here is misleading, as it actually refers to a directive that applies to any of the three GraphQL operations: queries, mutations, or subscriptions. Operation directives are still commonly referred to as “query” directives, hence the class name.

To explain how operation directive definition and usage are represented in code, we will walk through sample code with pure GraphQL Java. Then we’ll wrap up this section with an implementation for `@cache` in Spring for GraphQL.

In pure GraphQL Java, we can access an operation directive’s definition in the schema via an instance of `GraphQLSchema`, in this example called `schema`. We can access the operation directive’s name, arguments, locations, and whether it is repeatable.

```
[](#cb290-1)GraphQLSchema schema = ...;
[](#cb290-2)GraphQLDirective cacheDirective = schema.getDirective("cache");
[](#cb290-3)String name = cacheDirective.getName();
[](#cb290-4)List<GraphQLArgument> arguments = cacheDirective.getArguments();
[](#cb290-5)boolean repeatable = cacheDirective.isRepeatable();
[](#cb290-6)EnumSet<Introspection.DirectiveLocation> directiveLocations 
[](#cb290-7)        = cacheDirective.validLocations();
```

Usages of operation directives are represented in GraphQL Java as instances of `QueryAppliedDirective`, and provided argument values are represented as `QueryAppliedDirectiveArgument`.

We can access operation directives usage during execution via `getQueryDirectives()` in `DataFetchingEnvironment`. For example:

```
[](#cb291-1)package myservice.service;
[](#cb291-2)
[](#cb291-3)import graphql.execution.directives.QueryAppliedDirective;
[](#cb291-4)import graphql.execution.directives
[](#cb291-5)  .QueryAppliedDirectiveArgument;
[](#cb291-6)import graphql.execution.directives.QueryDirectives;
[](#cb291-7)import graphql.schema.DataFetchingEnvironment;
[](#cb291-8)import org.springframework.graphql.data.method.annotation
[](#cb291-9)  .QueryMapping;
[](#cb291-10)import org.springframework.stereotype.Controller;
[](#cb291-11)
[](#cb291-12)import java.util.List;
[](#cb291-13)
[](#cb291-14)@Controller
[](#cb291-15)class GreetingController {
[](#cb291-16) 
[](#cb291-17)  @QueryMapping
[](#cb291-18)  String hello(DataFetchingEnvironment env) {
[](#cb291-19)    QueryDirectives queryDirectives = env.getQueryDirectives();
[](#cb291-20)    List<QueryAppliedDirective> cacheDirectives = queryDirectives
[](#cb291-21)      .getImmediateAppliedDirective("cache");
[](#cb291-22)    // We get a List, because we could have
[](#cb291-23)    // repeatable directives
[](#cb291-24)    if (cacheDirectives.size() > 0) {
[](#cb291-25)      QueryAppliedDirective cache = cacheDirectives.get(0);
[](#cb291-26)      QueryAppliedDirectiveArgument maxAgeArgument
[](#cb291-27)        = cache.getArgument("maxAge");
[](#cb291-28)      int maxAge = maxAgeArgument.getValue();
[](#cb291-29)
[](#cb291-30)      // Now we know the max allowed cache time and
[](#cb291-31)      // can make use of it
[](#cb291-32)      // Your logic here
[](#cb291-33)    }
[](#cb291-34)    // Your logic here
[](#cb291-35)  }
[](#cb291-36) 
[](#cb291-37)}
```

In this chapter, we covered directives, a powerful GraphQL feature that enables us to change runtime execution and type validation. We covered the built-in directives and how to write our own directives.

# Execution

Execution is handled by the GraphQL Java engine. In this advanced chapter, we will look under the hood into how GraphQL Java executes a request based on a schema. By the end of this chapter, you’ll have a deeper understanding of how requests are executed by the GraphQL Java engine.

## Initializing execution objects

Before executing any GraphQL requests, Spring for GraphQL has to understand the schema and relevant configuration. To achieve this, Spring for GraphQL initializes an instance of GraphQL Java’s `graphql.GraphQL` class, which contains all the objects needed to execute a GraphQL operation, including the schema and execution strategies. Usually only one instance of `graphql.GraphQL` is initialized for all requests.

As part of the `graphql.GraphQL` initialization process, Spring for GraphQL loads schema files, exposes relevant properties, detects `RuntimeWiringConfigurer` beans and more. See the [Spring for GraphQL documentation](https://docs.spring.io/spring-graphql/docs/current/reference/html/#execution.graphqlsource) for detailed information.

While Spring for GraphQL initializes `graphql.GraphQL`, if there is anything you want to change, the instance can be accessed and modified via the `GraphQlSource` [contract](https://docs.spring.io/spring-graphql/docs/current/reference/html/#execution.graphqlsource). For example, to add a custom execution ID provider, create a `GraphQlSourceBuilderCustomizer` bean:

```
[](#cb292-1)package myservice.service;
[](#cb292-2)
[](#cb292-3)import org.springframework.boot.autoconfigure.graphql
[](#cb292-4)  .GraphQlSourceBuilderCustomizer;
[](#cb292-5)import org.springframework.context.annotation.Bean;
[](#cb292-6)import org.springframework.context.annotation.Configuration;
[](#cb292-7)
[](#cb292-8)@Configuration
[](#cb292-9)class GraphQlConfig {
[](#cb292-10)    @Bean
[](#cb292-11)    GraphQlSourceBuilderCustomizer sourceBuilderCustomizer() {
[](#cb292-12)        return (builder) ->
[](#cb292-13)            builder.configureGraphQl(graphQlBuilder ->
[](#cb292-14)                // Here we can use `GraphQL.Builder`
[](#cb292-15)                // For example, executionIdProvider
[](#cb292-16)                graphQlBuilder
[](#cb292-17)                    .executionIdProvider(new MyExecutionIdProvider()));
[](#cb292-18)    }
[](#cb292-19)}
```

Note that customizing the `GraphQlSource` is entirely optional. Spring for GraphQL already initializes enough to start executing requests without additional custom configuration.

If you are using GraphQL Java without Spring for GraphQL, this is how to manually initialize the `graphql.GraphQL` object.

```
[](#cb293-1)String sdl = "type Query { foo: String }"; // Your schema here
[](#cb293-2)TypeDefinitionRegistry parsedSdl = new SchemaParser().parse(sdl);
[](#cb293-3)
[](#cb293-4)DataFetcher<String> foo = (env) -> "foo";
[](#cb293-5)TypeRuntimeWiring queryWiring = newTypeWiring("Query")
[](#cb293-6)  .dataFetcher("foo", foo)
[](#cb293-7)  .build();
[](#cb293-8)RuntimeWiring runtimeWiring = newRuntimeWiring()
[](#cb293-9)  .type(queryWiring)
[](#cb293-10)  .build();
[](#cb293-11)
[](#cb293-12)GraphQLSchema schema = new SchemaGenerator()
[](#cb293-13)  .makeExecutableSchema(parsedSdl, runtimeWiring);
[](#cb293-14)GraphQL graphQL = GraphQL.newGraphQL(schema).build();
```

## How Spring for GraphQL starts execution

In the [request and response chapter](#ch010.xhtml_request-and-response-chapter), we discussed how Spring for GraphQL handles requests and responses over HTTP. In this chapter, we will focus on the execution steps after a request is received. These execution steps take place inside the GraphQL Java engine.

Recall from the [request and response chapter](#ch010.xhtml_request-and-response-chapter) that Spring for GraphQL automatically handles the HTTP protocol. A GraphQL request is an HTTP POST encoded as `application/json`.

For every received HTTP request, Spring for GraphQL automatically creates an instance of GraphQL Java’s `ExecutionInput`. Recall from the [request and response chapter](#ch010.xhtml_request-and-response-chapter) that `ExecutionInput` is the GraphQL Java object that represents a GraphQL request, without transport concerns. Inside Spring for GraphQL, this happens in the `DefaultExecutionGraphQlService`. It is possible to replace this with a custom implementation of `ExecutionGraphQlService`.

Control then passes to GraphQL Java, which executes the GraphQL request represented by an `ExecutionInput` instance. Following execution, an `ExecutionResult` instance containing response data and/or errors is returned. What happens in the GraphQL Java engine between `ExecutionInput` and `ExecutionResult` is the focus of the remainder of the chapter.

If you are using GraphQL Java without Spring for GraphQL, this is how to manually create an `ExecutionInput` and execute the request.

```
[](#cb294-1)GraphQL graphQL = GraphQL.newGraphQL(schema).build();
[](#cb294-2)
[](#cb294-3)ExecutionInput request = ExecutionInput.newExecutionInput()
[](#cb294-4)  .query("query test {foo}")
[](#cb294-5)  .build();
[](#cb294-6)
[](#cb294-7)ExecutionResult result = graphQL.execute(request);
```

## Execution steps

In GraphQL Java, execution includes the following steps:

1.  parsing the “query” (document) value from the request as a GraphQL document
2.  validating the document
3.  coercing variables
4.  fetching data

These are the steps between the GraphQL Java engine receiving a `ExecutionInput` request and returning a `ExecutionResult` instance with data and/or errors.

### Parsing and validation

Recall from the [request and response chapter](#ch010.xhtml_request-and-response-chapter) that the “query” in a GraphQL request is actually a GraphQL document, which can contain one or more operations. This “query” value is inserted into an instance of GraphQL Java’s `ExecutionInput`, which represents a GraphQL request.

The first step is parsing the “query” (document) value from the `ExecutionInput` and validating it. If the document contains invalid syntax, the parsing fails immediately. Otherwise, if the document is syntactically valid, it then is validated against the schema.

### Coercing variables

See the [query language chapter](#ch006.xhtml_variables) for an overview of GraphQL variables and see how variables are sent in an HTTP request in the [request and response chapter](#ch010.xhtml_request).

If the request contains variables, they need to be “coerced”. The *coercing* process converts the variable values provided in the request into an internal representation and also validates the variables. For example:

```
[](#cb295-1)query myQuery($name: String) {
[](#cb295-2)    echo(value: $name)
[](#cb295-3)}
```

This query has one variable `$name` with the type String. If the request now contains the following variables, variable coercing would fail since we expect a single `String` for `name`, not a list of `String`s.

```
[](#cb296-1){
[](#cb296-2)  "name": ["Luna", "Skipper"]
[](#cb296-3)}
```

### Fetching data

The last step is the core of execution: GraphQL Java fetching the data needed to fulfill the request.

As detailed in the [DataFetchers chapter](#ch007.xhtml_datafetchers-part-1), a DataFetcher in GraphQL Java is a generic function that loads data for one specific field. Spring for GraphQL implements DataFetchers via the `@SchemaMapping` controller annotation and shortcut annotations such as `@QueryMapping`.

Every field in the schema has a DataFetcher assigned to it. DataFetchers associated with fields in a GraphQL request will be invoked by GraphQL Java to fetch the data.

It is possible to for a field to accidentally not be mapped to any DataFetcher, even after PropertyDataFetchers are generated. This could happen by forgetting a `@SchemaMapping` annotation or missing a Java property. A forgotten DataFetcher will be treated as DataFetcher returning a `null` result. As you usually don’t want to forget any DataFetchers, the forthcoming [1.2 version of Spring for GraphQL](https://spring.io/blog/2023/03/21/spring-for-graphql-1-2-0-m1-released) will add schema mapping checks on startup.

Let’s look more closely at an example schema and query, which will help us understand the overall execution algorithm.

```
[](#cb297-1)type Query {
[](#cb297-2)    dogs: [Dog]
[](#cb297-3)}
[](#cb297-4)
[](#cb297-5)type Dog {
[](#cb297-6)    name: String
[](#cb297-7)    owner: Person
[](#cb297-8)    friends: [Dog]
[](#cb297-9)    details: DogDetails
[](#cb297-10)}
[](#cb297-11)
[](#cb297-12)type Person {
[](#cb297-13)    firstName: String
[](#cb297-14)    lastName: String
[](#cb297-15)}
[](#cb297-16)
[](#cb297-17)type DogDetails {
[](#cb297-18)    barking: Boolean
[](#cb297-19)    shedding: Boolean
[](#cb297-20)}
```

```
[](#cb298-1)query myDogs {
[](#cb298-2)    dogs {
[](#cb298-3)        name
[](#cb298-4)        owner {
[](#cb298-5)            firstName
[](#cb298-6)            lastName
[](#cb298-7)        }
[](#cb298-8)        friends {
[](#cb298-9)            name
[](#cb298-10)        }
[](#cb298-11)        details {
[](#cb298-12)            barking
[](#cb298-13)            shedding
[](#cb298-14)        }
[](#cb298-15)    }
[](#cb298-16)}
```

GraphQL Java interprets every GraphQL operation as a tree of fields. Each field has an associated DataFetcher. It is therefore equally valid to describe an operation as a tree of DataFetcher closures (unnamed functions).

![Tree of Fields](media/file15.png)

Tree of Fields

This query, as shown in the diagram “Tree of Fields”, has three levels, with `dogs` as the single root field. GraphQL Java traverses the query breadth-first and invokes the corresponding DataFetcher when visiting each field. Once a field’s DataFetcher has successfully returned data, we invoke the DataFetcher for each of its children. So the first DataFetcher being invoked is `/dogs`, followed by `/dogs/name`, `/dogs/owner`, `/dogs/friends` and `/dogs/details`.

A critical detail is that GraphQL Java fetches the children of a field in parallel, if possible.

For this example, let’s assume all DataFetchers allow parallel execution. The next steps of the execution depend on the order the DataFetchers finish. Let’s say `/dogs/friends` finishes first, followed by `/dogs/owner` then `/dogs/details`. This leads us to the execution order as shown in the diagram “Execution Order”.

![Execution Order](media/file16.png)

Execution Order

In this diagram, the numbers show the order of execution. Fields with the same number are executed in parallel.

To summarize, the execution is a breadth-first traversal of the fields, with each field finishing when its DataFetcher completes. We execute the children of a field in parallel, if possible.

## Reactive concurrency-agnostic

GraphQL Java is reactive concurrency-agnostic. This means GraphQL Java doesn’t prescribe a specific number of threads nor when they are used during execution. This is achieved by leveraging `java.util.concurrent.CompletableFuture`. Every DataFetcher can return a `CompletableFuture`, or if not, GraphQL Java wraps the returned value into a `CompletableFuture`.

This enables GraphQL Java to invoke all the child DataFetchers of a field at once, similar to this:

```
[](#cb299-1)// All happens in the same thread.
[](#cb299-2)// GraphQL Java doesn't create a new thread
[](#cb299-3)// or use a thread pool.
[](#cb299-4)List<CompletableFuture> dataFetchersCFs
[](#cb299-5)  = new ArrayList<CompletableFuture>();
[](#cb299-6)for (DataFetcher df: childrenDFs) {
[](#cb299-7)  Object cf = df.get(env);
[](#cb299-8)  // Wrapping non-CF
[](#cb299-9)  if (!(cf instanceof CompletableFuture)) {
[](#cb299-10)    cf = CompletableFuture.completedFuture(cf);
[](#cb299-11)  }
[](#cb299-12)  dataFetchersCFs.add((CompletableFuture) cf);
[](#cb299-13)}
```

A key question is **how much work does the DataFetcher perform in the current thread?** If no work or only very minimal work is done in the current thread, then GraphQL Java itself works as efficiently as possible. If a DataFetcher is using the current thread (by either doing computation, or waiting for some I/O to return), this blocks GraphQL Java itself, which then can’t invoke another DataFetcher.

Here are a few DataFetcher examples to make this clear. Note that it is equivalent in Spring for GraphQL to implement these DataFetchers via controller methods annotated with `@SchemaMapping`.

```
[](#cb300-1)// Intensive compute work in the current thread
[](#cb300-2)DataFetcher<String> df = (env) -> {
[](#cb300-3)  String str = intensiveComputeString();
[](#cb300-4)  return str;
[](#cb300-5)};
[](#cb300-6)
[](#cb300-7)// Still doing the actual work in the current thread
[](#cb300-8)DataFetcher<CompletableFuture<String>> df = (env) -> {
[](#cb300-9)  String str = intensiveComputeString();
[](#cb300-10)  return CompletableFuture.completedFuture(str);
[](#cb300-11)};
[](#cb300-12)
[](#cb300-13)// Blocking I/O call
[](#cb300-14)DataFetcher<String> df = (env) -> {
[](#cb300-15)  String str = makeHttpCallAndWaitForIt();
[](#cb300-16)  return str;
[](#cb300-17)};
[](#cb300-18)
[](#cb300-19)// Quick compute work in the current thread
[](#cb300-20)DataFetcher<String> df = (env) -> {
[](#cb300-21)  return "Hello";
[](#cb300-22)};
[](#cb300-23)
[](#cb300-24)// Offloaded compute work on another thread
[](#cb300-25)DataFetcher<CompletableFuture<String>> df = (env) -> {
[](#cb300-26)  Executor threadPool = ...;
[](#cb300-27)  return CompletableFuture.supplyAsync( () -> {
[](#cb300-28)    String str = intensiveComputeString();
[](#cb300-29)    return str;
[](#cb300-30)  },threadPool);
[](#cb300-31)};
[](#cb300-32)
[](#cb300-33)// Offloaded blocking I/O calls to another thread
[](#cb300-34)DataFetcher<CompletableFuture<String>> df = (env) -> {
[](#cb300-35)  Executor threadPool = ...;
[](#cb300-36)  return CompletableFuture.supplyAsync( () -> {
[](#cb300-37)    String str = makeHttpCallAndWaitForIt();
[](#cb300-38)    return str;
[](#cb300-39)  },threadPool);
[](#cb300-40)};
[](#cb300-41)
[](#cb300-42)// Using a reactive API to make an HTTP call
[](#cb300-43)DataFetcher<CompletableFuture<String>> df = (env) -> {
[](#cb300-44)  return makeReactiveHttpCall();
[](#cb300-45)};
```

We recommend that a DataFetcher should never occupy the thread it is called in, in order to achieve maximum efficiency.

Spring for GraphQL also enables DataFetchers to return Reactor values, in addition to `CompletableFuture`, as we saw in the [Reactor support section in the DataFetchers Part 2 chapter](#ch013.xhtml_reactor-support).

## Completing a field

After a DataFetcher returns a value for a field, GraphQL Java needs to process it. This phase is called “completing a field”.

If the value is `null`, completing terminates and does nothing further.

If the field type is a list, we complete all elements inside the list, depending on the generic type of the list.

For scalars and enums, the value is “coerced”. Coercing has two different purposes: first is making sure the value is valid, the second one is converting the value to an internal Java representation. Every `GraphQLScalarType` references a `graphql.schema.Coercing` instance. For enums, the `GraphQLEnumType.serialize` method is called.

For example, the built-in scalar `Scalars.GraphQLInt` only accepts Java `Number` values.

This means if we have a DataFetcher for a field of type `Int` and it returns the Boolean `false`, it would cause an error.

```
[](#cb301-1)type Query {
[](#cb301-2)    someInt: Int
[](#cb301-3)}
```

```
[](#cb302-1)DataFetcher invalidDf = (env) -> {
[](#cb302-2)  return true; // Will cause an error during execution
[](#cb302-3)}
```

### TypeResolver

If the type of the field is an interface or union, GraphQL Java needs to determine the actual object type of the value via a `TypeResolver`. See the DataFetchers chapter for an introduction to `TypeResolver`s and how to use them in [Spring for GraphQL](#ch007.xhtml_typeresolver-spring) and [GraphQL Java](#ch007.xhtml_typeresolver-in-graphql-java). This section focuses on the execution of `TypeResolver`s.

In our schema, we have a Pet interface:

```
[](#cb303-1)type Query {
[](#cb303-2)    pet: Pet
[](#cb303-3)}
[](#cb303-4)
[](#cb303-5)interface Pet {
[](#cb303-6)    name: String
[](#cb303-7)}
[](#cb303-8)
[](#cb303-9)type Dog implements Pet {
[](#cb303-10)    name: String
[](#cb303-11)    barks: Boolean
[](#cb303-12)}
[](#cb303-13)
[](#cb303-14)type Cat implements Pet {
[](#cb303-15)    name: String
[](#cb303-16)    meows: Boolean
[](#cb303-17)}
```

After a `TypeResolver` returns the type of the value, this information is used to determine the actual sub-selection of this field that needs to be fetched.

A sample query could look like:

```
[](#cb304-1)query myPet {
[](#cb304-2)    pet {
[](#cb304-3)        ...on Dog {
[](#cb304-4)            barks
[](#cb304-5)        }
[](#cb304-6)        ...on Cat {
[](#cb304-7)            meows
[](#cb304-8)        }
[](#cb304-9)    }
[](#cb304-10)}
```

Here the sub-selection for `pet` is `{ ...on Dog { barks } ...on Cat { meows } }`. If the returned value from the DataFetcher is a `Dog`, we need to fetch the field `barks`; if it is a `Cat`, we need to fetch `meows`.

Then the DataFetcher for all the fields in the sub-selection are called, as explained in the previous sections. This is a recursive step, which then again leads to the completion of each of the fields.

## Query vs mutation

Queries and mutations are executed in an almost identical way. The only difference is that the spec requires serial execution for multiple mutations in one operation.

For example:

```
[](#cb305-1)mutation modifyUsers {
[](#cb305-2)    deleteUser( ... ) { ... }
[](#cb305-3)    addOrder( ... ) { ... }
[](#cb305-4)    changeUser( ... ) { ... }
[](#cb305-5)}
```

vs

```
[](#cb306-1)query getUsersAndOrders {
[](#cb306-2)    searchUsers( ... ) { ... }
[](#cb306-3)    userById( ... ) { ... }
[](#cb306-4)    allOrders { ... }
[](#cb306-5)}
```

`DataFetchers` for the mutation are invoked serially. The DataFetcher for the mutation field `addOrder` is only invoked after `deleteUser` finishes. Likewise, the DataFetcher for `changeUser` is only invoked after `addOrder` finishes. Contrast this behaviour to the query where we invoke the DataFetchers in parallel for all three fields: `searchUsers`, `userById`, and `allOrders`.

This is the only difference in execution between queries and mutations. We implement a mutation as a DataFetcher, but there is a rule to follow when using GraphQL Java. A mutation DataFetcher may have side effects, whereas queries must not, although this is not enforced by GraphQL Java.

In this advanced chapter, we took a deep dive into execution inside the GraphQL Java engine. We also discussed how Spring for GraphQL initializes execution objects, and how it starts execution in GraphQL Java after receiving a request.

# Instrumentation

Instrumentation is a general mechanism to hook into GraphQL Java. You can inject code that can observe the execution of a query and also change runtime behavior. Instrumentation is particularly useful for performance monitoring and custom logging.

## Instrumentation in Spring for GraphQL

The Spring Boot starter will automatically detect `Instrumentation` beans as part of the `graphql.GraphQL` initialization process. `graphql.GraphQL` is a key GraphQL Java class containing information necessary to execute a request.

Let’s add our first instrumentation, `MaxQueryDepth`. This instrumentation will detect when an operation’s depth is above the specified number and abort execution early. You may want to add this instrumentation to enforce a hard limit on operation depth, as a way to limit resource use.

For example, imagine a query that requests for the names of friends, and in turn, the names of their friends, and so on. The sheer depth of this query may result in the service spending considerable resources to complete the request.

```
[](#cb307-1)query veryDeep {
[](#cb307-2)    hero {
[](#cb307-3)        name
[](#cb307-4)        friends {
[](#cb307-5)            name
[](#cb307-6)            friends {
[](#cb307-7)                name
[](#cb307-8)                friends {
[](#cb307-9)                    name
[](#cb307-10)                    # And so on!
[](#cb307-11)                }
[](#cb307-12)            }
[](#cb307-13)        }
[](#cb307-14)    }
[](#cb307-15)}
```

For convenience, GraphQL Java includes a few [built-in instrumentations](#ch016.xhtml_built-in-instrumentations), which are listed later in this chapter. Let’s add the built-in `MaxQueryDepth` instrumentation as a bean to our Spring for GraphQL service, and set the maximum depth to an appropriate number. This instrumentation will be automatically detected and registered by the Spring Boot starter, there is no further configuration required.

```
[](#cb308-1)package myservice.service;
[](#cb308-2)
[](#cb308-3)import graphql.analysis.MaxQueryDepthInstrumentation;
[](#cb308-4)import org.springframework.context.annotation.Bean;
[](#cb308-5)import org.springframework.context.annotation.Configuration;
[](#cb308-6)
[](#cb308-7)@Configuration
[](#cb308-8)class MyGraphQLConfiguration {
[](#cb308-9)    @Bean
[](#cb308-10)    MaxQueryDepthInstrumentation maxQueryDepthInstrumentation() {
[](#cb308-11)        return new MaxQueryDepthInstrumentation(15);
[](#cb308-12)    }
[](#cb308-13)}
```

When an operation is requested with a depth of greater than the specified value, the execution is aborted early and the following error message is returned within the response.

```
[](#cb309-1){
[](#cb309-2)  "errors": [
[](#cb309-3)    {
[](#cb309-4)      "message": "maximum query depth exceeded 42 > 15",
[](#cb309-5)      "extensions": {
[](#cb309-6)        "classification": "ExecutionAborted"
[](#cb309-7)      }
[](#cb309-8)    }
[](#cb309-9)  ]
[](#cb309-10)}
```

## Writing a custom instrumentation

You can write a custom instrumentation using [instrumentation hooks](#ch016.xhtml_instrumentation-hooks) available in the `graphql.execution.Instrumentation` interface in GraphQL Java. Each hook is a separate method. A list of available hooks is presented later in this chapter.

Let’s write a custom instrumentation that measures the time taken to execute a GraphQL request. This is the time between the start of GraphQL execution until the time the request is completed.

```
[](#cb310-1)package myservice.service;
[](#cb310-2)
[](#cb310-3)import graphql.ExecutionResult;
[](#cb310-4)import graphql.execution.instrumentation.InstrumentationContext;
[](#cb310-5)import graphql.execution.instrumentation.InstrumentationState;
[](#cb310-6)import graphql.execution.instrumentation.SimpleInstrumentation;
[](#cb310-7)import graphql.execution.instrumentation.parameters
[](#cb310-8)  .InstrumentationExecutionParameters;
[](#cb310-9)import org.springframework.stereotype.Component;
[](#cb310-10)
[](#cb310-11)import java.util.concurrent.CompletableFuture;
[](#cb310-12)import java.util.concurrent.atomic.AtomicLong;
[](#cb310-13)
[](#cb310-14)@Component
[](#cb310-15)class LogTimeInstrumentation extends SimpleInstrumentation {
[](#cb310-16)  @Override
[](#cb310-17)  public InstrumentationContext<ExecutionResult> beginExecution(
[](#cb310-18)    InstrumentationExecutionParameters parameters,
[](#cb310-19)    InstrumentationState state) {
[](#cb310-20)    return new InstrumentationContext<>() {
[](#cb310-21)      AtomicLong timeStart = new AtomicLong();
[](#cb310-22)
[](#cb310-23)      @Override
[](#cb310-24)      public void onDispatched(
[](#cb310-25)        CompletableFuture<ExecutionResult> result) {
[](#cb310-26)        timeStart.set(System.currentTimeMillis());
[](#cb310-27)      }
[](#cb310-28)
[](#cb310-29)      @Override
[](#cb310-30)      public void onCompleted(ExecutionResult result, Throwable t) {
[](#cb310-31)        System.out.println("execution time: "
[](#cb310-32)          + (System.currentTimeMillis() - timeStart.get()));
[](#cb310-33)      }
[](#cb310-34)    };
[](#cb310-35)  }
[](#cb310-36)}
```

Let’s walk through this instrumentation. In the `beginExecution` hook, we return an implementation of `InstrumentationContext<ExecutionResult>` with two methods `onDispatched` and `onCompleted`. They are called when the execution starts and finishes. We save the start time and then log the difference once the execution finishes. We’ll discuss `InstrumentationContext` in more detail in the next section.

Spring for GraphQL automatically detects and registers the instrumentation. Apart from annotating this instrumentation with `@Component`, no further configuration is required.

At the time of writing, the latest Spring for GraphQL 1.1 uses GraphQL Java 19.x. In Spring for GraphQL 1.2, GraphQL Java 20.x will be used, which adds the improved `SimplePerformantInstrumentation` class. It is designed to be more performant and reduce object allocations.

If you are using pure GraphQL Java, the instrumentation must be manually passed into the `graphql.GraphQL` builder.

```
[](#cb311-1)GraphQLSchema schema = ...; 
[](#cb311-2)GraphQL graphQL = GraphQL.newGraphQL(schema)
[](#cb311-3)  .instrumentation(new LogTimeInstrumentation())
[](#cb311-4)  .build();
```

## `InstrumentationContext`

`InstrumentationContext` is the object that will be called back when a particular step ends. `InstrumentationContext` is returned by step methods in `Instrumentation` such as `beginExecution`.

In GraphQL Java, it is represented as a simple interface.

```
[](#cb312-1)public interface InstrumentationContext<T> {
[](#cb312-2)
[](#cb312-3)    /**
[](#cb312-4)     * This is invoked when the instrumentation step is initially
[](#cb312-5)     * dispatched
[](#cb312-6)     *
[](#cb312-7) * @param  result  the result of the step as a completable future
[](#cb312-8)     */
[](#cb312-9)    void onDispatched(CompletableFuture<T> result);
[](#cb312-10)
[](#cb312-11)    /**
[](#cb312-12)     * This is invoked when the instrumentation step is fully completed
[](#cb312-13)     *
[](#cb312-14) * @param  result  the result of the step (which may be null)
[](#cb312-15)     * @param  t  this exception will be non-null if an exception 
[](#cb312-16)     *               was thrown during the step
[](#cb312-17)     */
[](#cb312-18)    void onCompleted(T result, Throwable t);
[](#cb312-19)
[](#cb312-20)}
```

The use of “dispatching” and “completion” reflects the reactive way GraphQL Java is implemented internally, based on `CompleteableFuture`s. A `CompleteableFuture` is created and then it is completed later. Once the linked `CompleteableFuture` is created, the engine calls the `onDispatched` method. When the linked `CompletableFuture` is finished, the engine calls the `onCompleted` method.

`InstrumentationContext` is a generic interface, and in the previous `LogTime` example, we returned an `InstrumentationContext` for `ExecutionResult`.

## `InstrumentationState`

Let’s discuss how state is managed in instrumentation.

We usually have only one `graphql.GraphQL` instance, which is reused across all requests. Instrumentations are registered for each `graphql.GraphQL` instance. So how do we maintain different instrumentation states per request? And how do we manage the state for complex instrumentations that require coordination across multiple hooks?

State management is achieved with the `createState` method that is called once per request and returns an `InstrumentationState`. `InstrumentationState` is an empty Java interface representing any kind of state. This state is passed into every hook as argument, and the state can be tracked across multiple hooks per request.

Let’s see this in action, with a more involved instrumentation. `FieldCountInstrumentation` counts the number of fields executed for a request.

```
[](#cb313-1)package myservice.service;
[](#cb313-2)
[](#cb313-3)import graphql.ExecutionResult;
[](#cb313-4)import graphql.execution.instrumentation.InstrumentationContext;
[](#cb313-5)import graphql.execution.instrumentation.InstrumentationState;
[](#cb313-6)import graphql.execution.instrumentation.SimpleInstrumentation;
[](#cb313-7)import graphql.execution.instrumentation.parameters
[](#cb313-8)  .InstrumentationCreateStateParameters;
[](#cb313-9)import graphql.execution.instrumentation.parameters
[](#cb313-10)  .InstrumentationExecutionParameters;
[](#cb313-11)import graphql.execution.instrumentation.parameters
[](#cb313-12)  .InstrumentationFieldParameters;
[](#cb313-13)import org.springframework.stereotype.Component;
[](#cb313-14)
[](#cb313-15)import java.util.concurrent.CompletableFuture;
[](#cb313-16)import java.util.concurrent.atomic.AtomicInteger;
[](#cb313-17)
[](#cb313-18)import static graphql.execution.instrumentation
[](#cb313-19)  .SimpleInstrumentationContext.noOp;
[](#cb313-20)
[](#cb313-21)@Component
[](#cb313-22)class FieldCountInstrumentation
[](#cb313-23)  extends SimpleInstrumentation {
[](#cb313-24)
[](#cb313-25)  static class FieldCountState implements InstrumentationState {
[](#cb313-26)    AtomicInteger counter = new AtomicInteger();
[](#cb313-27)  }
[](#cb313-28)
[](#cb313-29)  @Override
[](#cb313-30)  public InstrumentationState createState(
[](#cb313-31)    InstrumentationCreateStateParameters parameters) {
[](#cb313-32)    return new FieldCountState();
[](#cb313-33)  }
[](#cb313-34)
[](#cb313-35)  @Override
[](#cb313-36)  public InstrumentationContext<ExecutionResult> beginField(
[](#cb313-37)    InstrumentationFieldParameters parameters,
[](#cb313-38)    InstrumentationState state) {
[](#cb313-39)    ((FieldCountState) state).counter.incrementAndGet();
[](#cb313-40)    return noOp();
[](#cb313-41)  }
[](#cb313-42)
[](#cb313-43)  @Override
[](#cb313-44)  public InstrumentationContext<ExecutionResult> beginExecution(
[](#cb313-45)    InstrumentationExecutionParameters parameters,
[](#cb313-46)    InstrumentationState state) {
[](#cb313-47)    return new InstrumentationContext<ExecutionResult>() {
[](#cb313-48)      @Override
[](#cb313-49)      public void onDispatched(
[](#cb313-50)        CompletableFuture<ExecutionResult> result) {
[](#cb313-51)      }
[](#cb313-52)
[](#cb313-53)      @Override
[](#cb313-54)      public void onCompleted(ExecutionResult result, Throwable t) {
[](#cb313-55)        System.out.println(
[](#cb313-56)          "finished with " +
[](#cb313-57)            ((FieldCountState) state).counter.get() +
[](#cb313-58)            " Fields called"
[](#cb313-59)        );
[](#cb313-60)      }
[](#cb313-61)    };
[](#cb313-62)  }
[](#cb313-63)}
```

We declare a new class `FieldCountState` holding the state we are interested in. The `createState` method creates a new instance per execution. In the `beginField` hook, we simply increment the counter. After the execution finishes, we log the overall field counter.

This instrumentation is automatically detected and registered by Spring for GraphQL as it is annotated with the `@Component` annotation.

## `ChainedInstrumentation`

Spring for GraphQL automatically chains all detected instrumentation beans. No further configuration is required.

If using pure GraphQL Java, the instrumentations must be manually chained together via a `ChainedInstrumentation`. The `Instrumentation` objects are called in the order they are defined in.

In GraphQL Java, multiple instrumentations are manually chained together with `ChainedInstrumentation` and then this is passed to the `graphql.GraphQL` builder.

```
[](#cb314-1)List<Instrumentation> chainedList = new ArrayList<>();
[](#cb314-2)chainedList.add(new FooInstrumentation());
[](#cb314-3)chainedList.add(new BarInstrumentation());
[](#cb314-4)
[](#cb314-5)ChainedInstrumentation chainedInstrumentation 
[](#cb314-6)        = new ChainedInstrumentation(chainedList);
[](#cb314-7)
[](#cb314-8)GraphQLSchema schema = ...; 
[](#cb314-9)GraphQL graphQL = GraphQL.newGraphQL(schema)
[](#cb314-10)  .instrumentation(chainedInstrumentation)
[](#cb314-11)  .build();
```

## Built-in instrumentations

For convenience, GraphQL Java contains built-in instrumentations.

| Name |  |
| --- | --- |
| DataLoaderDispatcher Instrumentation | For [DataLoader](#ch017.xhtml_dataloader). |
| ExecutorInstrumentation | Controls on which thread calls to DataFetchers happen on |
| FieldValidationInstrumentation | Validates fields and their arguments before query execution. If errors are returned, execution is aborted. |
| MaxQueryComplexity Instrumentation | Prevents execution of very complex operations. |
| MaxQueryDepthInstrumentation | Prevents execution of very large operations. |
| TracingInstrumentation | Implements the [Apollo Tracing](https://github.com/apollographql/apollo-tracing) format. |

## List of instrumentation hooks

You can fully customise your instrumentation to hook into steps of GraphQL execution.

| Step | Description |
| --- | --- |
| beginExecution | Called when the overall execution is started |
| beginParse | Called when parsing of the provided document string is started |
| beginValidation | Called when validation of the parsed document is started |
| beginExecuteOperation | Called when the actual operation is being executed (meaning a DataFetcher is invoked) |
| beginSubscribedFieldEvent | Called when the subscription starts (only for subscription operations) |
| beginField | Called for each field of the operation |
| beginFieldFetch | Called when the DataFetcher for a field is called |
| beginFieldComplete | Called when the result of a DataFetcher is being processed |
| instrumentExecutionInput | Allows for changing the ExecutionInput |
| instrumentDocument AndVariables | Allows for changing the parsed document and/or the variables |
| instrumentSchema | Allows for changing the GraphQLSchema |
| instrumentExecutionContext | Allows for changing the ExecutionContext class that is used by GraphQL Java internally during execution. |
| instrumentDataFetcher | Allows for changing a DataFetcher right before it is invoked |
| instrumentExecutionResult | Allows for changing the overall execution result |

In this chapter we covered instrumentation, a mechanism to hook into GraphQL execution. We covered how to create instrumentation in Spring for GraphQL that injects code to observe the execution of a query, and instrumentation that changed runtime behavior.

# DataLoader

In this chapter, we will discuss DataLoader, the library used by GraphQL Java to batch and cache requests for data. We will discuss the common n+1 problem and how to solve it with DataLoader’s batching feature. We will also discuss how DataLoader’s caching feature makes data requests more efficient.

We will demonstrate how to use DataLoader in Spring for GraphQL. Then we’ll take a closer look at how DataLoader works in GraphQL Java.

## The n+1 problem

The n+1 problem is when related entities of an object are retrieved inefficiently, which can cause significant performance problems. It is a common problem when implementing DataFetchers for a schema. Note that this is a general problem occurring in other contexts such as SQL, it is not specific to GraphQL Java nor GraphQL.

Let’s explain the n+1 problem with a simple example, people, and their best friends.

```
[](#cb315-1)type Query {
[](#cb315-2)    people: [Person]
[](#cb315-3)}
[](#cb315-4)
[](#cb315-5)type Person {
[](#cb315-6)    name: String
[](#cb315-7)    bestFriend: Person
[](#cb315-8)}
```

A query could look like:

```
[](#cb316-1)query importantPeople { 
[](#cb316-2)    people { 
[](#cb316-3)        bestFriend { 
[](#cb316-4)            name 
[](#cb316-5)        } 
[](#cb316-6)    } 
[](#cb316-7)}
```

Let’s register two DataFetchers responsible for loading `people` and then their `bestFriend` in Spring for GraphQL.

```
[](#cb317-1)package myservice.service;
[](#cb317-2)
[](#cb317-3)record Person(String name, Integer bestFriendId) {
[](#cb317-4)}
```

```
[](#cb318-1)package myservice.service;
[](#cb318-2)
[](#cb318-3)import org.springframework.graphql.data.method.annotation
[](#cb318-4)  .QueryMapping;
[](#cb318-5)import org.springframework.graphql.data.method.annotation
[](#cb318-6)  .SchemaMapping;
[](#cb318-7)import org.springframework.stereotype.Controller;
[](#cb318-8)
[](#cb318-9)import java.util.List;
[](#cb318-10)
[](#cb318-11)@Controller
[](#cb318-12)record PersonController(PersonService personService) {
[](#cb318-13)
[](#cb318-14)  @QueryMapping
[](#cb318-15)  List<Person> people() {
[](#cb318-16)    return personService.getAllPeople();
[](#cb318-17)  }
[](#cb318-18)
[](#cb318-19)  @SchemaMapping
[](#cb318-20)  Person bestFriend(Person person) {
[](#cb318-21)    return personService.getPersonById(person.bestFriendId());
[](#cb318-22)  }
[](#cb318-23)}
```

While this code works, it will not perform well with large lists. For every person in the list, we invoke the DataFetcher for the best friend. For “n” people, we now have “n+1” service calls: one for loading the initial list of people and then one for each of the n people to load their best friend. This is where the name “n+1 problem” comes from. This can cause significant performance problems as large lists will require many calls to retrieve data.

## Solving the n+1 problem

The solution is instead of making one service call for each person, we load all the best friends of all the people at once. The loading of best friends is deferred, so they can be loaded together. This would reduce the number of service calls from n+1 to two, regardless of the number of people.

The n+1 problem is so common that the solution is built into GraphQL Java, and can be accessed in Spring for GraphQL with the controller annotation `@BatchMapping`. The solution makes use of the library [java-dataloader](https://github.com/graphql-java/java-dataloader), which is maintained by the GraphQL Java team. This library is a port of the JS library [DataLoader](https://github.com/graphql/dataloader). Note that in this book, we will call the Java library “DataLoader” for short, and make it explicitly clear when we talk about the JS DataLoader.

Implementing this solution is a small change in Spring for GraphQL.

```
[](#cb319-1)package myservice.service;
[](#cb319-2)
[](#cb319-3)import org.springframework.graphql.data.method.annotation
[](#cb319-4)  .BatchMapping;
[](#cb319-5)import org.springframework.graphql.data.method.annotation
[](#cb319-6)  .QueryMapping;
[](#cb319-7)import org.springframework.stereotype.Controller;
[](#cb319-8)
[](#cb319-9)import java.util.List;
[](#cb319-10)import java.util.stream.Collectors;
[](#cb319-11)
[](#cb319-12)@Controller
[](#cb319-13)record PersonController(PersonService personService) {
[](#cb319-14)
[](#cb319-15)  @QueryMapping
[](#cb319-16)  List<Person> people() {
[](#cb319-17)    return personService.getAllPeople();
[](#cb319-18)  }
[](#cb319-19)
[](#cb319-20)  // Modified controller method
[](#cb319-21)  @BatchMapping
[](#cb319-22)  List<Person> bestFriend(List<Person> people) {
[](#cb319-23)    List<Integer> ids = people
[](#cb319-24)      .stream()
[](#cb319-25)      .map(p -> p.bestFriendId())
[](#cb319-26)      .collect(Collectors.toList());
[](#cb319-27)    return personService.getPeopleById(ids);
[](#cb319-28)  }
[](#cb319-29)}
```

Replace the `@SchemaMapping` annotation with `@BatchMapping` on the `bestFriend` method. With `@BatchMapping`, by default the field name defaults to the method name `bestFriend` and the type name defaults to the simple class name of the input `List` element type, `Person`.

Change the `bestFriend` method argument to a list of people, and add logic to collect IDs from the list of people. For the DataLoader to work, the `PersonService` must offer a bulk retrieval method `getPeopleById`.

The `@BatchMapping` annotated method takes a list of people, then loads all their best friends at once. Only two service calls are made, instead of n+1\. There is quite a bit of Spring automated magic happening here, which we will explain in greater detail in this chapter.

## DataLoader overview

DataLoader is a library used by GraphQL Java to batch and cache data requests. Batching solves the n+1 problem, and caching makes data requests more efficient. This library is also maintained by the GraphQL Java team.

There are two key implementation concepts. A `DataLoader` instance is conceptually a layer deferring the loading of entities, which identified by some key. The loading is deferred until triggered by a “dispatch”. The timing of the dispatch is managed by GraphQL Java. Then all the data is loaded as a batch, with the logic in a user-implemented `BatchLoader`. Note that the library is called “DataLoader”, and one of the key classes is also called “DataLoader”. To distinguish between the two, we refer to the class with the words “class” or “instance”.

It’s interesting to note that DataLoader is not specific to GraphQL and is not part of the GraphQL specification. The two core features, batching and caching, can be applied generally.

To better understand how DataLoader works, we will walk through multiple examples. As DataLoader is not specific to GraphQL, let’s start with a simple example without any GraphQL concepts.

```
[](#cb320-1)// Setup
[](#cb320-2)UserService userService = ...;
[](#cb320-3)// expected to return a CompletableFuture
[](#cb320-4)BatchLoader<Integer, User> userBatchLoader = userIds -> 
[](#cb320-5)  userService.loadUsersById(userIds); 
[](#cb320-6)
[](#cb320-7)DataLoader<Integer, User> userLoader = DataLoaderFactory
[](#cb320-8)  .newDataLoader(userBatchLoader);
[](#cb320-9)
[](#cb320-10)// Usage
[](#cb320-11)CompletableFuture<User> user1CF = userLoader.load(1);
[](#cb320-12)CompletableFuture<User> user2CF = userLoader.load(2);
[](#cb320-13)userLoader.dispatchAndJoin();
[](#cb320-14)
[](#cb320-15)// Retrieve loaded users
[](#cb320-16)User user1 = user1CF.get();
[](#cb320-17)User user2 = user2CF.get();
```

In this example, we want to load users by ID (represented as an `Integer` value). We want to load the users in a batch to make the data request efficient.

We first implement the `BatchLoader` Java interface by calling the `loadUsersById` method. This is how our batched data will be fetched at the dispatch point. A BatchLoader must return a `CompletableFuture`.

Then we create a new `DataLoader` instance via `DataLoaderFactory`, providing the `BatchLoader`. Our DataLoader has argument types `Integer` and `User`, indicating we have a mapping from an `Integer` value to a `User`. DataLoader is based on the idea that we have a key (in this case `Integer`) being mapped to an entity (`User`). That means we can load an entity with a given key.

This completes the setup and then we can start using `DataLoader.load`. We immediately return these two calls with a `CompletableFuture`, but note that no actual loading has happened yet.

Then we want to batch load the users. This dispatch step is triggered with `DataLoader.dispatchAndJoin()`. This is a manual way to tell the DataLoader instance that it is time to commence batch loading. Note that in later examples, the dispatch point will be managed by GraphQL Java.

`dispatchAndJoin` triggers the invocation of `userBatchLoader` with the two user IDs `1` and `2` as arguments. After `dispatchAndJoin` returns, we have loaded all users and we can access them.

By default, DataLoader uses a simple in-memory `java.util.Map` as a cache to prevent multiple entities being loaded twice. So another `userLoader.load(1)` would return a `User` from this cache.

We created a `DataLoader` instance via `DataLoaderFactory`, which allows for multiple options to be configured via `DataLoaderOptions`. For example, we can change the cache implementation or disable caching completely.

## DataLoader and GraphQL Java

Let’s walk through a DataLoader example with GraphQL concepts. We will show this example with pure GraphQL Java as a way to explain DataLoader without the Spring automated magic. You don’t need to write this code as Spring for GraphQL’s `@BatchMapping` controller annotation eliminates much of this boilerplate code.

Let’s continue with our example of people and their best friends. This is how DataLoader works with the `bestFriend` DataFetcher, in pure GraphQL Java.

```
[](#cb321-1)import graphql.ExecutionInput;
[](#cb321-2)import graphql.ExecutionResult;
[](#cb321-3)import graphql.GraphQL;
[](#cb321-4)import graphql.schema.DataFetcher;
[](#cb321-5)import graphql.schema.GraphQLSchema;
[](#cb321-6)import graphql.schema.idl.RuntimeWiring;
[](#cb321-7)import graphql.schema.idl.SchemaGenerator;
[](#cb321-8)import graphql.schema.idl.SchemaParser;
[](#cb321-9)import graphql.schema.idl.TypeDefinitionRegistry;
[](#cb321-10)import graphql.schema.idl.TypeRuntimeWiring;
[](#cb321-11)import myservice.service.Person;
[](#cb321-12)import myservice.service.PersonService;
[](#cb321-13)import org.dataloader.BatchLoader;
[](#cb321-14)import org.dataloader.DataLoader;
[](#cb321-15)import org.dataloader.DataLoaderFactory;
[](#cb321-16)import org.dataloader.DataLoaderRegistry;
[](#cb321-17)
[](#cb321-18)import java.util.List;
[](#cb321-19)import java.util.concurrent.CompletableFuture;
[](#cb321-20)
[](#cb321-21)import static graphql.ExecutionInput.newExecutionInput;
[](#cb321-22)import static graphql.schema.idl.RuntimeWiring.newRuntimeWiring;
[](#cb321-23)import static graphql.schema.idl.TypeRuntimeWiring.newTypeWiring;
[](#cb321-24)import static java.util.concurrent.CompletableFuture.completedFuture;
[](#cb321-25)
[](#cb321-26)public class PureGraphQLJava {
[](#cb321-27)
[](#cb321-28)  public static void main(String[] args) throws Exception {
[](#cb321-29)    // Set up schema
[](#cb321-30)    String sdl = """
[](#cb321-31) type Query {
[](#cb321-32) people: [Person]
[](#cb321-33) }
[](#cb321-34) 
[](#cb321-35) type Person {
[](#cb321-36) name: String
[](#cb321-37) bestFriend: Person
[](#cb321-38) }
[](#cb321-39) """;
[](#cb321-40)    TypeDefinitionRegistry parsedSdl = new SchemaParser().parse(sdl);
[](#cb321-41)
[](#cb321-42)    PersonService personService = new PersonService();
[](#cb321-43)    DataFetcher<List<Person>> people = (env) -> personService
[](#cb321-44)                                                  .getAllPeople();
[](#cb321-45)
[](#cb321-46)    // Set up Person BatchLoader
[](#cb321-47)    BatchLoader<Integer, Person> personBatchLoader = personIds ->
[](#cb321-48)      completedFuture(personService.getPeopleById(personIds));
[](#cb321-49)
[](#cb321-50)    // DataFetcher implementation: select correct DataLoader and use
[](#cb321-51)    // it to load the data
[](#cb321-52)    String PERSON_DATA_LOADER = "person";
[](#cb321-53)
[](#cb321-54)    DataFetcher<CompletableFuture<Person>> bestFriendDF = (env) -> {
[](#cb321-55)      Person person = env.getSource();
[](#cb321-56)      DataLoader<Integer, Person> dataLoader
[](#cb321-57)        = env.getDataLoader(PERSON_DATA_LOADER);
[](#cb321-58)      return dataLoader.load(person.bestFriendId());
[](#cb321-59)    };
[](#cb321-60)
[](#cb321-61)    // Make executable schema
[](#cb321-62)    TypeRuntimeWiring queryWiring = newTypeWiring("Query")
[](#cb321-63)      .dataFetcher("people", people)
[](#cb321-64)      .build();
[](#cb321-65)    TypeRuntimeWiring bestie = newTypeWiring("Person")
[](#cb321-66)      .dataFetcher("bestFriend", bestFriendDF)
[](#cb321-67)      .build();
[](#cb321-68)    RuntimeWiring runtimeWiring = newRuntimeWiring()
[](#cb321-69)      .type(queryWiring)
[](#cb321-70)      .type(bestie)
[](#cb321-71)      .build();
[](#cb321-72)    GraphQLSchema schema = new SchemaGenerator()
[](#cb321-73)      .makeExecutableSchema(parsedSdl, runtimeWiring);
[](#cb321-74)
[](#cb321-75)    // Per request:
[](#cb321-76)
[](#cb321-77)    // Creating the DataLoader
[](#cb321-78)    DataLoader<Integer, Person> personDataLoader = DataLoaderFactory
[](#cb321-79)      .newDataLoader(personBatchLoader);
[](#cb321-80)
[](#cb321-81)    // Adding DataLoader instance to a DataLoaderRegistry
[](#cb321-82)    DataLoaderRegistry registry = new DataLoaderRegistry();
[](#cb321-83)    registry.register(PERSON_DATA_LOADER, personDataLoader);
[](#cb321-84)
[](#cb321-85)    String query = """
[](#cb321-86) query everyone {
[](#cb321-87) people {
[](#cb321-88) name
[](#cb321-89) bestFriend {
[](#cb321-90) name
[](#cb321-91) }
[](#cb321-92) }
[](#cb321-93) }""";
[](#cb321-94)
[](#cb321-95)    // Providing DataLoader instance to the ExecutionInput
[](#cb321-96)    ExecutionInput executionInput = newExecutionInput()
[](#cb321-97)      .query(query)
[](#cb321-98)      .dataLoaderRegistry(registry)
[](#cb321-99)      .build();
[](#cb321-100) 
[](#cb321-101)    // Execute query
[](#cb321-102)    GraphQL graphQL = GraphQL.newGraphQL(schema).build();
[](#cb321-103)    ExecutionResult executionResult = graphQL.execute(executionInput);
[](#cb321-104)  }
[](#cb321-105)}
```

The Person DataLoader is registered with the `bestFriend` DataFetcher.

Note that a new `DataLoader` instance needs to be created per request, as it holds state about what has been dispatched and cached, and this should not be shared across requests.

As there are often multiple entities we want to use with `DataLoader`, there can be multiple different `DataLoader` instances per request. These are managed by `DataLoaderRegistry`, which identifies each `DataLoader` instance by a name. It is also possible to dispatch all registered `DataLoader` instances at once with `DataLoaderRegistry.dispatchAll`.

We then create an instance of `ExecutionInput`, which represents the incoming GraphQL request. See the [Request chapter](#ch010.xhtml_request) for more on `ExecutionInput`. The request is then executed and returns the result.

It is important to highlight that there is no “dispatch” in this pure GraphQL Java code. This is because GraphQL Java knows when to dispatch with the help of the `DataLoaderDispatcherInstrumentation`, which is automatically added to the `GraphQL` instance.

## DataLoader and Spring for GraphQL

Now that we’ve seen the pure GraphQL Java way to use DataLoader, we’ll walk through how to implement the same logic in Spring for GraphQL. We’ll begin with an example that does not use the `@BatchMapping` controller annotation to demonstrate how it works.

In Spring for GraphQL, a single, central `BatchLoaderRegistry` exposes factory methods and a builder to create and register `BatchLoader`s. The Spring Boot starter declares a `BatchLoaderRegistry` bean, which can be injected into a component such as a controller in the example below. Spring for GraphQL injects the DataLoader instance into the DataFetcher.

```
[](#cb322-1)package myservice.service;
[](#cb322-2)
[](#cb322-3)import org.dataloader.DataLoader;
[](#cb322-4)import org.springframework.graphql.data.method.annotation
[](#cb322-5)  .QueryMapping;
[](#cb322-6)import org.springframework.graphql.data.method.annotation
[](#cb322-7)  .SchemaMapping;
[](#cb322-8)import org.springframework.graphql.execution
[](#cb322-9)  .BatchLoaderRegistry;
[](#cb322-10)import org.springframework.stereotype.Controller;
[](#cb322-11)import reactor.core.publisher.Flux;
[](#cb322-12)
[](#cb322-13)import java.util.List;
[](#cb322-14)import java.util.concurrent.CompletableFuture;
[](#cb322-15)
[](#cb322-16)@Controller
[](#cb322-17)class PersonController {
[](#cb322-18)
[](#cb322-19)  PersonService personService;
[](#cb322-20) 
[](#cb322-21)  PersonController(
[](#cb322-22)    PersonService personService,
[](#cb322-23)    BatchLoaderRegistry batchLoaderRegistry) {
[](#cb322-24)    this.personService = personService;
[](#cb322-25)
[](#cb322-26)    // Registering the BatchLoader 
[](#cb322-27)    batchLoaderRegistry
[](#cb322-28)      .forTypePair(Integer.class, Person.class)
[](#cb322-29)      .registerBatchLoader(
[](#cb322-30)        (integers, batchLoaderEnvironment) -> Flux
[](#cb322-31)          .fromIterable(personService.getPeopleById(integers)
[](#cb322-32)          )
[](#cb322-33)      );
[](#cb322-34)  }
[](#cb322-35)
[](#cb322-36)  @QueryMapping
[](#cb322-37)  List<Person> people() {
[](#cb322-38)    return personService.getAllPeople();
[](#cb322-39)  }
[](#cb322-40)
[](#cb322-41)  // Manually using DataLoader instance in DataFetcher
[](#cb322-42)  @SchemaMapping
[](#cb322-43)  CompletableFuture<Person> bestFriend(
[](#cb322-44)    Person person, DataLoader<Integer, Person> dataLoader) {
[](#cb322-45)    // Using the DataLoader
[](#cb322-46)    return dataLoader.load(person.bestFriendId());
[](#cb322-47)  }
[](#cb322-48)
[](#cb322-49)}
```

`BatchLoaderRegistry` is a map of names to `BatchLoader`s. Spring for GraphQL automatically chooses the name to be the full class name of the entity we want to load. This name can be customized. Note that the `BatchLoaderRegistry` expects `BatchLoader`s to return a `Flux` and not a `CompletableFuture`.

Based on the automatically chosen `BatchLoader` name, we can declare `DataLoader<Integer, Person> dataLoader` as a method argument and Spring knows which DataLoader to inject based on the types `<Integer, Person>`.

In our example, the `bestFriend` DataFetcher only delegates directly to the DataLoader. This allows us to further reduce our code by using the `@BatchMapping` annotation, as we saw earlier in this chapter.

```
[](#cb323-1)package myservice.service;
[](#cb323-2)
[](#cb323-3)import org.springframework.graphql.data.method.annotation
[](#cb323-4)  .BatchMapping;
[](#cb323-5)import org.springframework.graphql.data.method.annotation
[](#cb323-6)  .QueryMapping;
[](#cb323-7)import org.springframework.stereotype.Controller;
[](#cb323-8)
[](#cb323-9)import java.util.List;
[](#cb323-10)import java.util.stream.Collectors;
[](#cb323-11)
[](#cb323-12)@Controller
[](#cb323-13)class PersonController {
[](#cb323-14)
[](#cb323-15)  PersonService personService;
[](#cb323-16)
[](#cb323-17)  // This constructor is written to emphasize 
[](#cb323-18)  // Spring for GraphQL automation.
[](#cb323-19)  // You can instead use a record class 
[](#cb323-20)  // and use the generated constructor.
[](#cb323-21)  PersonController(PersonService personService) {
[](#cb323-22)    this.personService = personService;
[](#cb323-23)    // No longer require BatchLoaderRegistry
[](#cb323-24)    // nor manual BatchLoader registration
[](#cb323-25)  }
[](#cb323-26)
[](#cb323-27)  @QueryMapping
[](#cb323-28)  List<Person> people() {
[](#cb323-29)    return personService.getAllPeople();
[](#cb323-30)  }
[](#cb323-31)
[](#cb323-32)  // Using @BatchMapping instead of @SchemaMapping
[](#cb323-33)  @BatchMapping
[](#cb323-34)  List<Person> bestFriend(List<Person> people) {
[](#cb323-35)    List<Integer> ids = people
[](#cb323-36)      .stream()
[](#cb323-37)      .map(p -> p.bestFriendId())
[](#cb323-38)      .collect(Collectors.toList());
[](#cb323-39)    return personService.getPeopleById(ids);
[](#cb323-40)  }
[](#cb323-41)
[](#cb323-42)}
```

The `@BatchMapping` annotation helps us remove much of the boilerplate code.

It is important to note that `Person` in this final example is the key type for the DataLoader signature rather than `Integer`. The signature is now `DataLoader<Person, Person>` rather than `DataLoader<Integer, Person>`. Therefore, it is critical that `Person` implements equals and hashcode methods in order to work as a key.

Spring for GraphQL automatically registers a `BatchLoader` with the type pair `Person, Person` in the `BatchLoaderRegistry`, so we no longer need to manually do this step. Note that `Person` is both the key and value type in this automatically registered `BatchLoader`. The `BatchLoader` logic is moved to the last line of the `bestFriend` method.

Then Spring for GraphQL creates a DataLoader instance with the full class name of `Person`. In our `bestFriend` method, a list of people is provided as an argument. We then extract the best friend IDs and delegate to the DataLoader instance, which is analogous to `dataLoader.load(person.bestFriendId)` in the previous example.

## `@BatchMapping` method signature

Batch mapping methods support the following arguments in Spring for GraphQL:

| Argument | Description |
| --- | --- |
| `List<T>` | The list of source objects |
| `java.security.Principal` | Spring Security principal |
| `@ContextValue`(name = “foo”) | A specific value from the GraphQLContext |
| `GraphQLContext` | The entire GraphQLContext |
| `BatchLoaderEnvironment` | `org.dataloader.BatchLoaderWithContext` from DataLoader itself |

The supported return types are:

| Return Type | Description |
| --- | --- |
| `Mono<Map<K, V>>` | The mapping from key to value |
| `Flux<V>` | A reactive sequence of resolved values |
| `Map<K, V>` | Non-reactive map of key to value |
| `Collection<V>` | Non-reactive collection (including list) |
| `Callable<Map<K,V>>`, `Callable<Collection<V>>` | Imperative variant to be invoked asynchronously |

In this chapter, we covered the n+1 problem when too many service calls are used to fetch data. We solved the problem with DataLoader, which is conveniently made available with `@BatchMapping` in Spring for GraphQL. We then had a closer look at how DataLoader works under the hood.

# Testing

Spring for GraphQL provides helpers for GraphQL testing in a dedicated artifact `org.springframework.graphql:spring-graphql-test`. Testing a GraphQL service can happen on multiple levels, with different scopes. In this chapter, we will discuss how Spring for GraphQL makes it easier to write tests. At the end of the chapter, we’ll conclude with our recommendations for writing good tests.

In this chapter, we will make use of standard testing libraries. We will use [JUnit 5](https://junit.org/junit5/docs/current/user-guide/), [Mockito](https://javadoc.io/static/org.mockito/mockito-core/4.5.1/org/mockito/Mockito.html), [AssertJ](https://assertj.github.io/doc/), and the standard Spring Boot testing capabilities.

## Unit testing DataFetcher

[DataFetchers](#ch007.xhtml_datafetchers-part-1) are the central concept for implementing a Spring for GraphQL service, because they are the link between your schema and the data. The main guideline for writing DataFetchers is that they should be very thin and delegate the actual work to a layer of code below it. The only purpose of a DataFetcher should be to take care of GraphQL-specific aspects. Some examples are reading and validation input, mapping return data, handling exceptions, and converting it to an error.

By purposefully designing DataFetchers to be thin, they also become easier to write unit tests for.

In the first [DataFetchers chapter](#ch018.xhtml_datafetchers-part-1%7D), we discussed that DataFetchers in Spring for GraphQL are registered via controller methods with a `@SchemaMapping` annotation, or one of the shortcut annotations such as `@QueryMapping`.

Initially, we’ll explore testing with a simple Hello World example, to illustrate the different types of testing with Spring for GraphQL. Later in this chapter, we’ll also write tests for a larger Pet schema.

Here is the simple schema for our Hello World example:

```
[](#cb324-1)type Query {
[](#cb324-2)    hello: String
[](#cb324-3)}
```

A simple query:

```
[](#cb325-1)query greeting {
[](#cb325-2)    hello
[](#cb325-3)}
```

And a simple DataFetcher registered with the `@QueryMapping` controller annotation.

```
[](#cb326-1)package myservice.service;
[](#cb326-2)
[](#cb326-3)import org.springframework.graphql.data.method.annotation
[](#cb326-4)  .QueryMapping;
[](#cb326-5)import org.springframework.stereotype.Controller;
[](#cb326-6)
[](#cb326-7)@Controller
[](#cb326-8)class GreetingController {
[](#cb326-9)
[](#cb326-10)  @QueryMapping
[](#cb326-11)  String hello() {
[](#cb326-12)    return "Hello, world!";
[](#cb326-13)  }
[](#cb326-14)}
```

The `hello` DataFetcher is a good example of a thin DataFetcher that can be easily unit tested.

```
[](#cb327-1)package myservice.service;
[](#cb327-2)
[](#cb327-3)import org.junit.jupiter.api.Test;
[](#cb327-4)import org.junit.jupiter.api.extension.ExtendWith;
[](#cb327-5)import org.mockito.junit.jupiter.MockitoExtension;
[](#cb327-6)
[](#cb327-7)import static org.assertj.core.api.Assertions.assertThat;
[](#cb327-8)
[](#cb327-9)@ExtendWith(MockitoExtension.class)
[](#cb327-10)class GreetingControllerTest {
[](#cb327-11)
[](#cb327-12)  @Test
[](#cb327-13)  void testHelloDataFetcher() {
[](#cb327-14)    GreetingController greetingController = new GreetingController();
[](#cb327-15)
[](#cb327-16)    String greeting = greetingController.hello();
[](#cb327-17)    // Verify returned object is expected one
[](#cb327-18)    assertThat(greeting).isEqualTo("Hello, world!");
[](#cb327-19)  }
[](#cb327-20)}
```

If it becomes difficult to unit test a DataFetcher, we should try to break it apart and write multiple smaller unit tests.

As we saw in the [DataFetchers chapter](#ch007.xhtml_datafetchers-graphql-java), a DataFetcher’s get method accepts an input `DataFetchingEnvironment`, which is a Java interface containing the necessary GraphQL information to fetch data, including source, schema, document, context, selection set, and much more. We also saw in the [DataFetchers chapter](#ch007.xhtml_spring-datafetcher-inputs) that Spring for GraphQL provides shortcuts to particular fields in the `DataFetchingEnvironment`, to be used as inputs into DataFetchers registered via controller annotations. When writing DataFetcher tests, we recommend mocking the `DataFetchingEnvironment` and only implement the parts needed.

## `GraphQlTester`

`GraphQlTester` is the primary class to help us test in Spring for GraphQL. `GraphQlTester` is a Java interface with a few inner interfaces, which provides a rich API to execute requests and verify responses. There are a number of implementations for different types of tests:

*   `HttpGraphQlTester` for HTTP-based testing, leveraging a `WebTestClient`
*   `WebGraphQlTester` for testing a `WebGraphQlHandler`
*   `ExecutionGraphQlServiceTester` for testing a `ExecutionGraphQlService`
*   `WebSocketGraphQlTester` for testing WebSocket requests

These different classes are normally only used to create a `GraphQlTester` instance. For use in code, we only reference `GraphQlTester`.

For example, here is a query for our Hello World example from earlier in this chapter:

```
[](#cb328-1)query greeting {
[](#cb328-2)    hello
[](#cb328-3)}
```

With `GraphQlTester`, we can write a test to verify this query is executed, and returns the expected response “Hello, world!”. This example demonstrates the `HttpGraphQlTester`.

```
[](#cb329-1)package myservice.service;
[](#cb329-2)
[](#cb329-3)import org.junit.jupiter.api.Test;
[](#cb329-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb329-5)import org.springframework.boot.test.context.SpringBootTest;
[](#cb329-6)import org.springframework.graphql.test.tester.HttpGraphQlTester;
[](#cb329-7)
[](#cb329-8)@SpringBootTest(
[](#cb329-9)  webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
[](#cb329-10)class GreetingControllerTest {
[](#cb329-11)
[](#cb329-12)  @Autowired
[](#cb329-13)  HttpGraphQlTester graphQlTester;
[](#cb329-14)
[](#cb329-15)  @Test
[](#cb329-16)  void usingTester() {
[](#cb329-17)    graphQlTester
[](#cb329-18)      .document("query greeting { hello }")
[](#cb329-19)      .execute()
[](#cb329-20)      .path("hello")
[](#cb329-21)      .entity(String.class)
[](#cb329-22)      .isEqualTo("Hello, world!");
[](#cb329-23)  }
[](#cb329-24)}
```

We’ll soon explain all the parts in this test, but let’s start by focusing on the `GraphQlTester`. We provide a document with `document`, `execute` it, select a specific part of the response to verify with `path`, and finally verify it is the string “Hello, world!”.

To make testing code more compact, note that the document in this example is provided on a single line. This is equivalent to a query with new lines, because new lines and additional whitespace are ignored in GraphQL syntax.

We’ll see how this `GraphQlTester` fits into a test class in multiple examples later in this chapter.

Let’s walk through each of these method calls in this test.

### `document` or `documentName`

A document is provided with `document`.

Alternatively, we could use `GraphQlTester.documentName` to specify a resource `.graphql` file containing a document, instead of using an inline string. By default, `GraphQlTester` expects the file to be in `src/test/resources/graphql-test`.

For example, you could save this query in a file called `greeting.graphql` in the directory `src/test/resources/graphql-test`.

```
[](#cb330-1)# Save this file as "greeting.graphql" in src/test/resources/graphql-test
[](#cb330-2)query greeting {
[](#cb330-3)    hello
[](#cb330-4)}
```

Then we could rewrite our earlier test with `documentName` to use this resource file containing the document:

```
[](#cb331-1)graphQlTester
[](#cb331-2)  .documentName("greeting")
[](#cb331-3)  .execute()
[](#cb331-4)  .path("hello")
[](#cb331-5)  .entity(String.class)
[](#cb331-6)  .isEqualTo("Hello, world!");
```

### `GraphQlTester.Request` and `execute`

`GraphQlTester.document` returns a `GraphQlTester.Request`.

`GraphQlTester.Request` specifies the details of a request (operation name, variables) and then `GraphQlTester.Request.execute` returns a `GraphQlTester.Response`.

### `GraphQlTester.Response`, `path`, `entity`, `entityList`

`GraphQlTester.Response` extends `Traversable`, which is a simple interface:

```
[](#cb332-1)interface Traversable {
[](#cb332-2)    Path path(String path);
[](#cb332-3)}
```

We can use any [JsonPath](https://github.com/json-path/JsonPath) with `path`. In our Hello World example, we used the path `"hello"`. In the more complex Pets example later in this chapter, we’ll see how to select names from a list of Pets.

You can traverse a GraphQL response by providing a path and returning a `GraphQlTester.Path`, which is again itself a `Traversable`. A `Path` has different ways of asserting or converting the current part of the GraphQL response. We can convert it to an `entity` or `entityList` and then assert further.

For example, a Pet can be converted to an `entity` and then asserted further. For example, a very basic favorite Pet schema:

```
[](#cb333-1)type Query {
[](#cb333-2)    favoritePet: Pet
[](#cb333-3)}
[](#cb333-4)
[](#cb333-5)type Pet {
[](#cb333-6)    name: String
[](#cb333-7)}
```

With a small Pet class:

```
[](#cb334-1)package myservice.service;
[](#cb334-2)
[](#cb334-3)record Pet(String name) {
[](#cb334-4)}
```

And a basic DataFetcher that queries a database:

```
[](#cb335-1)package myservice.service;
[](#cb335-2)
[](#cb335-3)import org.springframework.graphql.data.method.annotation
[](#cb335-4)  .QueryMapping;
[](#cb335-5)import org.springframework.stereotype.Controller;
[](#cb335-6)
[](#cb335-7)@Controller
[](#cb335-8)class PetsController {
[](#cb335-9)
[](#cb335-10)  @QueryMapping
[](#cb335-11)  Pet favoritePet() {
[](#cb335-12)    // return favorite pet from database
[](#cb335-13)  }
[](#cb335-14)
[](#cb335-15)}
```

To convert the current part of the GraphQL response into a Pet entity in `GraphQlTester`, use `entity(Pet.class)`, then test your assertion afterwards:

```
[](#cb336-1)Pet favoritePet = graphQlTester
[](#cb336-2)        .document("query whoIsAGoodBoyOrGirl { favoritePet { name } }")
[](#cb336-3)        .execute()
[](#cb336-4)        .path("favoritePet")
[](#cb336-5)        .entity(Pet.class)
[](#cb336-6)        .get()
[](#cb336-7)        // Your assertion here
```

See the more complicated Pets example later in this chapter for usage of `entityList` when a list of Pets is returned.

### `errors`

By default, a GraphQL error in the response will not cause the test to fail since a partial response in GraphQL is still a valid answer. See why partial responses and nullable fields are valuable in the [Schema Design chapter](#ch012.xhtml_nullable-fields).

However, in a test, you usually want to check that no errors were returned. To verify that no errors are returned in a test, add `.errors().verify()`.

```
[](#cb337-1)graphQlTester
[](#cb337-2)  .document("query greeting { hello }")
[](#cb337-3)  .execute()
[](#cb337-4)  .errors()
[](#cb337-5)  .verify() // Ensure there are no GraphQL errors
[](#cb337-6)  .path("hello")
[](#cb337-7)  .entity(String.class)
[](#cb337-8)  .isEqualTo("Hello, world!");
```

To filter out particular errors, we can use `errors().filter(error -> ...).verify()` to exclude errors from the test. To verify that an error is present, we can use `.errors().expect(error -> ...).verify()`.

## Testing different layers

As explained in the [Spring for GraphQL overview](#ch004.xhtml_spring-graphql-overview) at the beginning of the book, there are three key Spring for GraphQL classes: `GraphQlHttpHandler`, `WebGraphQlHandler`, and `ExecutionGraphQlService`. We can also test the HTTP transport layer.

To recap, a request passes through three primary classes in Spring for GraphQL, each with a distinct responsibility, as shown in the diagram “Spring for GraphQL classes”:

1.  A general purpose HTTP request invokes `GraphQlHttpHandler` converts the request into a `WebGraphQlRequest`.
2.  `WebGraphQlHandler` takes the `WebGraphQlRequest`, and calls `ExecutionGraphQlService` to execute the request.
3.  `ExecutionGraphQlService` ultimately invokes GraphQL Java.

![Spring for GraphQL classes](media/file8.png)

Spring for GraphQL classes

We can test these different layers:

*   End-to-end over HTTP: creating an entirely separate process and test via HTTP
*   Application test: test in the same process without the full HTTP layer, includes a client
*   Test on server side (without a client) starting from `WebGraphQLHandler`
*   Test on server side (without a client) starting from `ExecutionGraphQlService`

Note that the next few sections focus on HTTP where tests include transport. For WebSocket tests, see [subscriptions testing section later in this chapter](#ch018.xhtml_subscription-testing).

## End-to-end over HTTP

Spring Boot allows us to start a whole service as a separate process and test it end-to-end over HTTP by using the `SpringBootTest` annotation.

```
[](#cb338-1)@SpringBootTest(
[](#cb338-2)    webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
```

As mentioned [earlier in this chapter](#ch018.xhtml_graphql-tester), we have a `HttpGraphQlTester` to test a GraphQL API via HTTP. It builds on top of `WebTestClient`.

By combining the `@SpringBootTest` annotation and the `HttpGraphQlTester`, we can write an end-to-end test:

```
[](#cb339-1)package myservice.service;
[](#cb339-2)
[](#cb339-3)import org.junit.jupiter.api.Test;
[](#cb339-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb339-5)import org.springframework.boot.test.context.SpringBootTest;
[](#cb339-6)import org.springframework.graphql.test.tester.HttpGraphQlTester;
[](#cb339-7)
[](#cb339-8)@SpringBootTest(
[](#cb339-9)    webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
[](#cb339-10)class E2ETest {
[](#cb339-11)
[](#cb339-12)  @Autowired
[](#cb339-13)  HttpGraphQlTester graphQlTester;
[](#cb339-14)
[](#cb339-15)  @Test
[](#cb339-16)  void testHello() {
[](#cb339-17)    String document = "query greeting { hello }";
[](#cb339-18)    graphQlTester.document(document)
[](#cb339-19)      .execute()
[](#cb339-20)      .path("hello")
[](#cb339-21)      .entity(String.class)
[](#cb339-22)      .isEqualTo("Hello, world!");
[](#cb339-23)  }
[](#cb339-24)}
```

This tests a whole GraphQL service over HTTP, verifying that the request `query greeting { hello }` returns “Hello, world!”.

## Application test

To test the whole service, without the HTTP transport layer, we can start the whole application in the same Java Virtual Machine (JVM).

To automatically configure a `HttpGraphQlTester`, use the `@AutoConfigureHttpGraphQlTester` annotation.

```
[](#cb340-1)package myservice.service;
[](#cb340-2)
[](#cb340-3)import org.junit.jupiter.api.Test;
[](#cb340-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb340-5)import org.springframework.boot.test.autoconfigure.graphql.tester
[](#cb340-6)  .AutoConfigureHttpGraphQlTester;
[](#cb340-7)import org.springframework.boot.test.context.SpringBootTest;
[](#cb340-8)import org.springframework.graphql.test.tester.HttpGraphQlTester;
[](#cb340-9)
[](#cb340-10)@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.MOCK)
[](#cb340-11)@AutoConfigureHttpGraphQlTester
[](#cb340-12)class MockedTest {
[](#cb340-13)
[](#cb340-14)  @Autowired
[](#cb340-15)  HttpGraphQlTester graphQlTester;
[](#cb340-16)
[](#cb340-17)  @Test
[](#cb340-18)  void testHello() {
[](#cb340-19)    String document = "query greeting { hello }";
[](#cb340-20)    graphQlTester.document(document)
[](#cb340-21)      .execute()
[](#cb340-22)      .path("hello")
[](#cb340-23)      .entity(String.class)
[](#cb340-24)      .isEqualTo("Hello, world!");
[](#cb340-25)  }
[](#cb340-26)
[](#cb340-27)}
```

This test only verifies the request inside the application, inside the JVM. It is different to the previous end-to-end test, as the request in this test does not go through the HTTP transport layer.

## `WebGraphQlHandler` test

A `WebGraphQlHandler` test enables direct testing of `WebGraphQlHandler`. This includes `WebGraphQlInterceptor`, because the `WebGraphQlHandler` manages interceptors. Create a new tester instance by providing the relevant `WebGraphQlHandler`.

```
[](#cb341-1)package myservice.service;
[](#cb341-2)
[](#cb341-3)import org.junit.jupiter.api.Test;
[](#cb341-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb341-5)import org.springframework.boot.test.context.SpringBootTest;
[](#cb341-6)import org.springframework.graphql.server.WebGraphQlHandler;
[](#cb341-7)import org.springframework.graphql.test.tester.WebGraphQlTester;
[](#cb341-8)
[](#cb341-9)@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.MOCK)
[](#cb341-10)class WebGraphQlTest {
[](#cb341-11)
[](#cb341-12)  @Autowired
[](#cb341-13)  WebGraphQlHandler webGraphQlHandler;
[](#cb341-14)
[](#cb341-15)  @Test
[](#cb341-16)  void testHello() {
[](#cb341-17)    WebGraphQlTester webGraphQlTester 
[](#cb341-18)            = WebGraphQlTester.create(webGraphQlHandler);
[](#cb341-19)    String document = "query greeting { hello }";
[](#cb341-20)    webGraphQlTester.document(document)
[](#cb341-21)      .execute()
[](#cb341-22)      .path("hello")
[](#cb341-23)      .entity(String.class)
[](#cb341-24)      .isEqualTo("Hello, world!");
[](#cb341-25)  }
[](#cb341-26)}
```

## `ExecutionGraphQlService` test

`ExecutionGraphQlServiceTester` enables direct testing of `ExecutionGraphQlService`. Create a new tester instance by providing the relevant `ExecutionGraphQlService`.

```
[](#cb342-1)package myservice.service;
[](#cb342-2)
[](#cb342-3)import org.junit.jupiter.api.Test;
[](#cb342-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb342-5)import org.springframework.boot.test.context.SpringBootTest;
[](#cb342-6)import org.springframework.graphql.ExecutionGraphQlService;
[](#cb342-7)import org.springframework.graphql.test.tester
[](#cb342-8)  .ExecutionGraphQlServiceTester;
[](#cb342-9)
[](#cb342-10)@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.MOCK)
[](#cb342-11)class GraphQlServiceTest {
[](#cb342-12)
[](#cb342-13)  @Autowired
[](#cb342-14)  ExecutionGraphQlService graphQlService;
[](#cb342-15)
[](#cb342-16)  @Test
[](#cb342-17)  void testHello() {
[](#cb342-18)    ExecutionGraphQlServiceTester graphQlServiceTester 
[](#cb342-19)            = ExecutionGraphQlServiceTester.create(graphQlService);
[](#cb342-20)    String document = "query greeting { hello }";
[](#cb342-21)    graphQlServiceTester.document(document)
[](#cb342-22)      .execute()
[](#cb342-23)      .path("hello")
[](#cb342-24)      .entity(String.class)
[](#cb342-25)      .isEqualTo("Hello, world!");
[](#cb342-26)  }
[](#cb342-27)
[](#cb342-28)}
```

## Focused GraphQL testing with `@GraphQlTest`

For a more minimal testing setup, we can use the `@GraphQlTest` annotation instead of `@SpringBootTest`. `@GraphQlTest` configures a slice test, which will load only a subset of an application, focusing only on the GraphQL layer. It is a `ExecutionGraphQlServiceTester`, with the added feature of only automatically loading what is strictly needed to execute the request, and nothing else.

Let’s examine `@GraphQlTest` with a Pet service. This is the schema:

```
[](#cb343-1)type Query {
[](#cb343-2)    pets: [Pet]
[](#cb343-3)}
[](#cb343-4)
[](#cb343-5)type Pet {
[](#cb343-6)    name: String
[](#cb343-7)}
```

The query we want to test is:

```
[](#cb344-1)query myPets {
[](#cb344-2)    pets { 
[](#cb344-3)        name 
[](#cb344-4)    } 
[](#cb344-5)}
```

This is the Pet controller, which includes a static Pet class and the `pets` DataFetcher annotated with `@QueryMapping`:

```
[](#cb345-1)package myservice.service;
[](#cb345-2)
[](#cb345-3)import org.springframework.graphql.data.method.annotation
[](#cb345-4)  .QueryMapping;
[](#cb345-5)import org.springframework.stereotype.Controller;
[](#cb345-6)
[](#cb345-7)import java.util.List;
[](#cb345-8)
[](#cb345-9)@Controller
[](#cb345-10)record PetsController(PetService petService) {
[](#cb345-11) 
[](#cb345-12)  @QueryMapping
[](#cb345-13)  List<Pet> pets() {
[](#cb345-14)    return petService.getPets();
[](#cb345-15)  }
[](#cb345-16)
[](#cb345-17)}
```

The controller uses a Pet service, which fetches a list of Pets from a data source, which could be a database or another service, or anything else.

```
[](#cb346-1)package myservice.service;
[](#cb346-2)
[](#cb346-3)import org.springframework.stereotype.Service;
[](#cb346-4)
[](#cb346-5)@Service
[](#cb346-6)class PetService {
[](#cb346-7) 
[](#cb346-8)  List<Pet> getPets() {
[](#cb346-9)    // Fetch data from database, or elsewhere 
[](#cb346-10)  }
[](#cb346-11) 
[](#cb346-12)}
```

In this example, our `pets` DataFetcher is very thin, it only delegates to `PetService`. This is quite realistic, and usually we aim for this kind of design.

Now with `@GraphQlTest`, our test setup includes the `PetController`, but not the `PetService` because it doesn’t belong to the GraphQL layer itself.

This means we need to create a mock for the `PetService`.

```
[](#cb347-1)package myservice.service;
[](#cb347-2)
[](#cb347-3)import org.junit.jupiter.api.Test;
[](#cb347-4)import org.mockito.Mockito;
[](#cb347-5)import org.springframework.beans.factory.annotation.Autowired;
[](#cb347-6)import org.springframework.boot.test.autoconfigure.graphql
[](#cb347-7)  .GraphQlTest;
[](#cb347-8)import org.springframework.boot.test.mock.mockito.MockBean;
[](#cb347-9)import org.springframework.graphql.test.tester.GraphQlTester;
[](#cb347-10)
[](#cb347-11)import java.util.List;
[](#cb347-12)
[](#cb347-13)@GraphQlTest(PetsController.class)
[](#cb347-14)class PetsControllerTest {
[](#cb347-15)
[](#cb347-16)  @Autowired
[](#cb347-17)  GraphQlTester graphQlTester;
[](#cb347-18)
[](#cb347-19)  @MockBean
[](#cb347-20)  PetService petService;
[](#cb347-21)
[](#cb347-22)  @Test
[](#cb347-23)  void testPets() {
[](#cb347-24)    Mockito.when(petService.getPets())
[](#cb347-25)      .thenReturn(List.of(
[](#cb347-26)        new Pet("Luna"),
[](#cb347-27)        new Pet("Skipper")
[](#cb347-28)      ));
[](#cb347-29)
[](#cb347-30)    graphQlTester
[](#cb347-31)      .document("query myPets { pets { name } }")
[](#cb347-32)      .execute()
[](#cb347-33)      .path("pets[*].name")
[](#cb347-34)      .entityList(String.class)
[](#cb347-35)      .isEqualTo(List.of("Luna", "Skipper"));
[](#cb347-36)  }
[](#cb347-37) 
[](#cb347-38)}
```

This is a suitable setup, especially if we have a complicated setup below the controller. Mocking the Pet service dependency allows for a very focused and lean test.

As an alternative, you could verify there were at least two pet names by replacing the last block of the test above with:

```
[](#cb348-1)graphQlTester
[](#cb348-2)    .document("query myPets { pets { name } }")
[](#cb348-3)    .execute()
[](#cb348-4)    .path("pets[*].name")
[](#cb348-5)    .entityList(String.class)
[](#cb348-6)    .hasSizeGreaterThan(2);
```

In these examples, the `path` for Pets was more complex than our Hello World example. `"pets[*].name"` means select all names of all pets. We can use any [JsonPath](https://github.com/json-path/JsonPath) with `path`.

## Subscription testing

`GraphQlTester` offers an `executeSubscription` method that returns a `GraphQlTester.Subscription`. This can be then further converted to a `Flux` and verified. To test `Flux` more easily, add the Reactor testing library `io.projectreactor:reactor-test`.

Testing our `hello` subscription from the [Subscription chapter](#ch009.xhtml_getting-started-subscriptions) end to end looks like this.

```
[](#cb349-1)# Every schema needs a Query type
[](#cb349-2)type Query {
[](#cb349-3)    notUsed: String
[](#cb349-4)}
[](#cb349-5)
[](#cb349-6)type Subscription {
[](#cb349-7)    hello: String
[](#cb349-8)}
```

```
[](#cb350-1)package myservice.service;
[](#cb350-2)
[](#cb350-3)import org.springframework.graphql.data.method.annotation
[](#cb350-4)  .SubscriptionMapping;
[](#cb350-5)import org.springframework.stereotype.Controller;
[](#cb350-6)import reactor.core.publisher.Flux;
[](#cb350-7)
[](#cb350-8)import java.time.Duration;
[](#cb350-9)import java.util.List;
[](#cb350-10)
[](#cb350-11)@Controller
[](#cb350-12)class HelloController {
[](#cb350-13)
[](#cb350-14)  @SubscriptionMapping
[](#cb350-15)  Flux<String> hello() {
[](#cb350-16)    Flux<Integer> interval = Flux.fromIterable(List.of(0, 1, 2))
[](#cb350-17)      .delayElements(Duration.ofSeconds(1));
[](#cb350-18)    return interval.map(integer -> "Hello " + integer);
[](#cb350-19)  }
[](#cb350-20)}
```

If you haven’t already, set the WebSocket path in `application.properties`.

```
spring.graphql.websocket.path=/graphql
```

```
[](#cb352-1)package myservice.service;
[](#cb352-2)
[](#cb352-3)import org.junit.jupiter.api.BeforeEach;
[](#cb352-4)import org.junit.jupiter.api.Test;
[](#cb352-5)import org.springframework.beans.factory.annotation.Value;
[](#cb352-6)import org.springframework.boot.test.context.SpringBootTest;
[](#cb352-7)import org.springframework.graphql.test.tester.GraphQlTester;
[](#cb352-8)import org.springframework.graphql.test.tester
[](#cb352-9)  .WebSocketGraphQlTester;
[](#cb352-10)import org.springframework.web.reactive.socket.client
[](#cb352-11)  .ReactorNettyWebSocketClient;
[](#cb352-12)import reactor.core.publisher.Flux;
[](#cb352-13)import reactor.test.StepVerifier;
[](#cb352-14)
[](#cb352-15)import java.net.URI;
[](#cb352-16)
[](#cb352-17)@SpringBootTest(
[](#cb352-18)    webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
[](#cb352-19)class SubscriptionTest {
[](#cb352-20)
[](#cb352-21)  @Value("http://localhost:${local.server.port}"
[](#cb352-22)    + "${spring.graphql.websocket.path}")
[](#cb352-23)  private String baseUrl;
[](#cb352-24)
[](#cb352-25)  GraphQlTester graphQlTester;
[](#cb352-26)
[](#cb352-27)  @BeforeEach
[](#cb352-28)  void setUp() {
[](#cb352-29)    URI url = URI.create(baseUrl);
[](#cb352-30)    this.graphQlTester = WebSocketGraphQlTester.builder(
[](#cb352-31)      url, new ReactorNettyWebSocketClient()
[](#cb352-32)    ).build();
[](#cb352-33)  }
[](#cb352-34)
[](#cb352-35)  @Test
[](#cb352-36)  void helloSubscription() {
[](#cb352-37)    Flux<String> hello = graphQlTester
[](#cb352-38)      .document("subscription mySubscription {hello}")
[](#cb352-39)      .executeSubscription()
[](#cb352-40)      .toFlux("hello", String.class);
[](#cb352-41)
[](#cb352-42)    StepVerifier.create(hello)
[](#cb352-43)      .expectNext("Hello 0")
[](#cb352-44)      .expectNext("Hello 1")
[](#cb352-45)      .expectNext("Hello 2")
[](#cb352-46)      .verifyComplete();
[](#cb352-47)  }
[](#cb352-48)}
```

We create a `WebSocketGraphQlTester` by proving the URL and a WebSocket client. The default WebFlux server is Netty, meaning we use the `ReactorNettyWebSocketClient`.

In the actual test, we execute the subscription request and convert it to a `Flux<String>` by selecting the `hello` values from each response. Then we use the `StepVerifier` from the Reactor testing library to verify that we get exactly the three events we expect.

The same way we have tested subscription end to end here also allows us to test subscriptions on different layers.

## Testing recommendations

A general guide for writing good tests is to have the smallest or most focused test possible that verifies what we want to test.

Here are some examples:

*   If we want to test our DataFetcher calling the `PetService`, a unit test is the right approach.
*   If we want to make sure our GraphQL setup is correct (e.g. verify that a DataFetcher is mapped to the correct field), `@GraphQlTest` is the right approach.
*   If we want to test a `WebGraphQlInterceptor`, then a `WebGraphQlHandler` test is most often good enough.

It is good to have some basic end-to-end Spring Boot tests, ensuring that the whole service starts and receives requests as expected. However, keep in mind that these end-to-end tests are mostly focused on setup. If you want to focus on verifying behavior, it is better to use a mock environment.

Testing all layers together involves running a SpringBootTest in a mock environment with a `HttpGraphQlHandler`. This is useful to test security which we will discuss in the [next chapter on Security](#ch019.xhtml_testing-auth).

These testing guidelines fit into the [Test Pyramid model](https://martinfowler.com/bliki/TestPyramid.html). The idea is to have more of focused, smaller and faster tests, compared to the number of tests that run longer, test more aspects, and are harder to debug. This model gives us some guidance about the amount of tests per test type. It is preferable to have more unit tests than `WebGraphQlHandlerTests`, and it is preferable to have more `WebGraphQlHandlerTests` than the number of end-to-end tests.

In this chapter, we covered unit testing, application testing, and end-to-end testing with Spring for GraphQL. We also discussed testing best practices and how to think about testing your Spring for GraphQL service.

# Security

Spring for GraphQL makes securing GraphQL much simpler by integrating familiar concepts from [Spring Security](https://spring.io/projects/spring-security).

In this chapter, *auth* is short for both authentication and authorization.

Although securing GraphQL services is important, note that the GraphQL specification does not prescribe any specific auth logic, because it does not dictate where the data comes from. As a result of this, GraphQL Java does not provide auth support. Another key reason for omitting auth support in GraphQL Java was the impracticality of a generic engine attempting to support auth with is tightly coupled with transport layer concerns.

As security is not part of the GraphQL Java engine, this chapter will instead focus on using Spring for GraphQL and [Spring Security](https://spring.io/projects/spring-security) to secure your GraphQL service. Spring for GraphQL has built-in, dedicated support for Spring Security.

## Securing a Spring for GraphQL service

We’ll walk through key concepts with an example service for managing store orders. We intend for the important parts to be realistic to ensure we have a working and secured service, while we will take some shortcuts to keep this chapter short.

A web client will use our online store with a GraphQL API via HTTP, where they can query all the orders for the current user. For brevity, only admins can remove an order, and we will not cover order creation.

Here is our store orders schema.

```
[](#cb353-1)type Query {
[](#cb353-2)    # Every logged-in user can query orders
[](#cb353-3)    myOrders: [Order]
[](#cb353-4)}
[](#cb353-5)
[](#cb353-6)type Order {
[](#cb353-7)    id: ID
[](#cb353-8)    details: String
[](#cb353-9)}
[](#cb353-10)
[](#cb353-11)type Mutation {
[](#cb353-12)    # Only Admins can delete orders
[](#cb353-13)    deleteOrder(input: DeleteOrderInput!): DeleteOrderPayload
[](#cb353-14)}
[](#cb353-15)
[](#cb353-16)input DeleteOrderInput {
[](#cb353-17)    orderId: ID
[](#cb353-18)}
[](#cb353-19)
[](#cb353-20)type DeleteOrderPayload {
[](#cb353-21)    success: Boolean
[](#cb353-22)}
```

Let’s implement a very simple Java class `OrderService` that loads and changes orders, which are stored in memory.

```
[](#cb354-1)package myservice.service;
[](#cb354-2)
[](#cb354-3)record Order(String id, String details, String owner) {
[](#cb354-4)}
```

```
[](#cb355-1)package myservice.service;
[](#cb355-2)
[](#cb355-3)import org.springframework.stereotype.Service;
[](#cb355-4)
[](#cb355-5)import java.util.ArrayList;
[](#cb355-6)import java.util.List;
[](#cb355-7)import java.util.stream.Collectors;
[](#cb355-8)
[](#cb355-9)@Service
[](#cb355-10)class OrderService {
[](#cb355-11)
[](#cb355-12)  private final List<Order> orders;
[](#cb355-13)
[](#cb355-14)  OrderService() {
[](#cb355-15)    // A mutable list of orders
[](#cb355-16)    this.orders = new ArrayList<>(List.of(
[](#cb355-17)      new Order("1", "Kibbles", "Luna"),
[](#cb355-18)      new Order("2", "Chicken", "Skipper"),
[](#cb355-19)      new Order("3", "Rice", "Luna"),
[](#cb355-20)      new Order("4", "Lamb", "Skipper"),
[](#cb355-21)      new Order("5", "Bone", "Luna"),
[](#cb355-22)      new Order("6", "Toys", "Luna"),
[](#cb355-23)      new Order("7", "Toys", "Skipper")
[](#cb355-24)    ));
[](#cb355-25)  }
[](#cb355-26)
[](#cb355-27)  List<Order> getOrdersByOwner(String owner) {
[](#cb355-28)    return orders
[](#cb355-29)      .stream()
[](#cb355-30)      .filter(order -> order.owner().equals(owner))
[](#cb355-31)      .collect(Collectors.toList());
[](#cb355-32)  }
[](#cb355-33)
[](#cb355-34)  boolean deleteOrder(String orderId) {
[](#cb355-35)    return orders.removeIf(order -> order.id().equals(orderId));
[](#cb355-36)  }
[](#cb355-37) 
[](#cb355-38)}
```

This simple Java class includes the basic functional aspects we want: `getOrdersByOwner` returns the list of orders for the provided owner and `deleteOrder` deletes an order.

Our authentication will use session cookies and we require a valid session for every request. This means that before the execution of a request starts, we need to ensure that we have a valid session, otherwise we return an HTTP 401 status code.

Once we have a valid session identifying the user, we can query their orders and check if they can delete an order. This authorization part is handled during GraphQL execution on the DataFetcher-level.

To add Spring Security to our project, add the dependency

`org.springframework.boot:spring-boot-starter-security`

and then create the following `Config` class.

```
[](#cb356-1)package myservice.service;
[](#cb356-2)
[](#cb356-3)import org.springframework.context.annotation.Bean;
[](#cb356-4)import org.springframework.context.annotation.Configuration;
[](#cb356-5)import org.springframework.security.config.annotation.web
[](#cb356-6)  .reactive.EnableWebFluxSecurity;
[](#cb356-7)import org.springframework.security.config.web.server
[](#cb356-8)  .ServerHttpSecurity;
[](#cb356-9)import org.springframework.security.core.userdetails
[](#cb356-10)  .MapReactiveUserDetailsService;
[](#cb356-11)import org.springframework.security.core.userdetails.User;
[](#cb356-12)import org.springframework.security.core.userdetails
[](#cb356-13)  .UserDetails;
[](#cb356-14)import org.springframework.security.web.server
[](#cb356-15)  .SecurityWebFilterChain;
[](#cb356-16)import org.springframework.security.web.server.authentication
[](#cb356-17)  .RedirectServerAuthenticationSuccessHandler;
[](#cb356-18)
[](#cb356-19)@Configuration
[](#cb356-20)@EnableWebFluxSecurity
[](#cb356-21)class Config {
[](#cb356-22)
[](#cb356-23)  @Bean
[](#cb356-24)  SecurityWebFilterChain springWebFilterChain(ServerHttpSecurity http) 
[](#cb356-25)      throws Exception {
[](#cb356-26)    http.formLogin().authenticationSuccessHandler(
[](#cb356-27)      new RedirectServerAuthenticationSuccessHandler("/graphiql")
[](#cb356-28)    );
[](#cb356-29)
[](#cb356-30)    return http
[](#cb356-31)      .csrf(ServerHttpSecurity.CsrfSpec::disable)
[](#cb356-32)      .authorizeExchange(exchanges -> {
[](#cb356-33)        exchanges.anyExchange().authenticated();
[](#cb356-34)      })
[](#cb356-35)      .build();
[](#cb356-36)  }
[](#cb356-37)
[](#cb356-38)  @Bean
[](#cb356-39)  @SuppressWarnings("deprecation")
[](#cb356-40)  MapReactiveUserDetailsService userDetailsService() {
[](#cb356-41)    User.UserBuilder userBuilder = User.withDefaultPasswordEncoder();
[](#cb356-42)    UserDetails luna = userBuilder
[](#cb356-43)      .username("Luna").password("password").roles("USER")
[](#cb356-44)      .build();
[](#cb356-45)    UserDetails andi = userBuilder
[](#cb356-46)      .username("Andi").password("password").roles("USER", "ADMIN")
[](#cb356-47)      .build();
[](#cb356-48)    return new MapReactiveUserDetailsService(luna, andi);
[](#cb356-49)  }
[](#cb356-50)}
```

Let’s step through this security configuration:

*   It activates Spring Security for reactive WebFlux applications with the annotation `@EnableWebFluxSecurity`.
*   It configures a simple form-based login, which should redirect to `/graphiql` if successful. [GraphiQL](https://github.com/graphql/graphiql) is an interactive playground which is included in Spring for GraphQL.
*   It disables [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) protection to allow us to use GraphiQL for easy testing. We do not recommend disabling CSRF for a real service.
*   It requires that every request is authenticated.
*   It configures the list of users, simply by declaring them and including their password directly in our configuration. Of course, hard coded users is only acceptable for demo code.

The simple form-based login allows us to login by visiting `/login` in a browser and to logout via `/logout`. If not logged in, we are get redirected to `/login`. This is a very convenient way for us to switch users easily and verify the expected behavior manually.

Let’s create the last required class, the `OrderController` that implements our DataFetcher.

To implement the `myOrders` method, we need to know the current logged-in user. Spring for GraphQL provides access to the current `java.security.Principal` by simply declaring it as a Java argument. Spring for GraphQL made this possible by integrating with Spring Security.

```
[](#cb357-1)package myservice.service;
[](#cb357-2)
[](#cb357-3)import org.springframework.graphql.data.method.annotation
[](#cb357-4)  .QueryMapping;
[](#cb357-5)import org.springframework.stereotype.Controller;
[](#cb357-6)
[](#cb357-7)import java.security.Principal;
[](#cb357-8)import java.util.List;
[](#cb357-9)
[](#cb357-10)@Controller
[](#cb357-11)record OrderController(OrderService orderService) {
[](#cb357-12)
[](#cb357-13)  @QueryMapping
[](#cb357-14)  List<Order> myOrders(Principal principal) {
[](#cb357-15)    return orderService.getOrdersByOwner(principal.getName());
[](#cb357-16)  }
[](#cb357-17)
[](#cb357-18)}
```

This is the first part of implementing authorization. We use the current user to filter the list of orders returned. We only return the orders belonging to the right user.

The second DataFetcher is concerned with deleting an order. While we already made sure that we have valid authentication, we must also check authorization. Only admins can delete orders. Therefore, we need to verify the role of the current user before we delete any orders.

```
[](#cb358-1)package myservice.service;
[](#cb358-2)
[](#cb358-3)record DeleteOrderInput(String orderId) {
[](#cb358-4)}
```

```
[](#cb359-1)package myservice.service;
[](#cb359-2)
[](#cb359-3)record DeleteOrderPayload(boolean success) {
[](#cb359-4)}
```

```
[](#cb360-1)package myservice.service;
[](#cb360-2)
[](#cb360-3)import org.springframework.graphql.data.method.annotation
[](#cb360-4)  .Argument;
[](#cb360-5)import org.springframework.graphql.data.method.annotation
[](#cb360-6)  .MutationMapping;
[](#cb360-7)import org.springframework.graphql.data.method.annotation
[](#cb360-8)  .QueryMapping;
[](#cb360-9)import org.springframework.security.access
[](#cb360-10)  .AccessDeniedException;
[](#cb360-11)import org.springframework.security.authentication
[](#cb360-12)  .UsernamePasswordAuthenticationToken;
[](#cb360-13)import org.springframework.security.core.authority
[](#cb360-14)  .SimpleGrantedAuthority;
[](#cb360-15)import org.springframework.stereotype.Controller;
[](#cb360-16)
[](#cb360-17)import java.security.Principal;
[](#cb360-18)import java.util.List;
[](#cb360-19)
[](#cb360-20)@Controller
[](#cb360-21)record OrderController(OrderService orderService) {
[](#cb360-22)
[](#cb360-23)  @QueryMapping
[](#cb360-24)  List<Order> myOrders(Principal principal) {
[](#cb360-25)    return orderService.getOrdersByOwner(principal.getName());
[](#cb360-26)  }
[](#cb360-27)
[](#cb360-28)  @MutationMapping
[](#cb360-29)  DeleteOrderPayload deleteOrder(@Argument DeleteOrderInput input,
[](#cb360-30)                                        Principal principal) {
[](#cb360-31)    UsernamePasswordAuthenticationToken user
[](#cb360-32)      = (UsernamePasswordAuthenticationToken) principal;
[](#cb360-33)    if (!user.getAuthorities()
[](#cb360-34)      .contains(new SimpleGrantedAuthority("ROLE_ADMIN"))) {
[](#cb360-35)      throw new AccessDeniedException("Only admins can delete orders");
[](#cb360-36)    }
[](#cb360-37)    return new DeleteOrderPayload(orderService
[](#cb360-38)      .deleteOrder(input.orderId()));
[](#cb360-39)  }
[](#cb360-40)}
```

We use the injected `Principal` again, but this time we use it to verify that the current user has the correct role, rather than filtering orders. If the user is unauthorized, we throw an `AccessDeniedException`.

We can test this service manually by logging in as “Luna” at `/login` with the password “password” and querying all orders via the GraphiQL playground, as shown in the screenshot “Luna’s orders”.

```
[](#cb361-1)query lunaOrders {
[](#cb361-2)    myOrders {
[](#cb361-3)        id
[](#cb361-4)    }
[](#cb361-5)}
```

![Luna’s orders](media/file17.png)

Luna’s orders

If we try to delete an order as Luna, we will get a GraphQL error telling us we are unauthorized, as shown in the screenshot “Luna is unauthorized to delete orders”.

```
[](#cb362-1)mutation lunaUnauthorized {
[](#cb362-2)    deleteOrder(input: {orderId: 1}) {
[](#cb362-3)        success
[](#cb362-4)    }
[](#cb362-5)}
```

![Luna is unauthorized to delete orders](media/file18.png)

Luna is unauthorized to delete orders

After we log out via `/logout` and login as “Andi” (with password “password”), we can delete an order.

It’s important to note that an unauthorized attempt to delete an order with a logged-in user, will **not** cause an HTTP error. The status code of the HTTP response is `200` containing a GraphQL error.

## Spring for GraphQL support for security

In the store orders example, we saw one feature of Spring for GraphQL supporting Spring Security: we can declare a `java.security.Principal` as input for annotated methods (this includes `@BatchMapping`).

Spring for GraphQL also automatically registers a `ReactiveSecurityDataFetcherExceptionResolver` (or `SecurityDataFetcherExceptionResolver` for WebMVC) handling `AuthenticationException` and `AccessDeniedException`. `AuthenticationException` and `AccessDeniedException` result in a GraphQL error with error type `UNAUTHORIZED` and `FORBIDDEN` respectively.

## Method security

One problem with our store order example above is the location where we perform the authorization checks. They happen directly inside each DataFetcher. This is not great. The better and recommended way is to secure the `OrderService` itself, so that it is secure, regardless which DataFetcher uses it.

Spring Security offers method-level annotations to perform authorization in a declarative way. As Spring for GraphQL integrates Spring Security, we can use these annotations to refactor `OrderService`.

```
[](#cb363-1)@PreAuthorize("hasRole('ADMIN')")
[](#cb363-2)Mono<Boolean> deleteOrder(String orderId) {
[](#cb363-3)  return Mono.just(orders.removeIf(order -> order.id().equals(orderId)));
[](#cb363-4)}
```

In order for `PreAuthorize` to work in a WebFlux service, the annotated method must return `Mono` or `Flux`. Therefore, we need to wrap our return value in a `Mono`.

We also refactor `getOrdersByOwner` into `getOrdersForCurrentUser` and we are using `ReactiveSecurityContextHolder` to get the current logged-in user.

```
[](#cb364-1)Mono<List<Order>> getOrdersForCurrentUser() {
[](#cb364-2)  return ReactiveSecurityContextHolder.getContext()
[](#cb364-3)    .map(securityContext -> {
[](#cb364-4)      Principal principal = securityContext.getAuthentication();
[](#cb364-5)      return orders
[](#cb364-6)        .stream()
[](#cb364-7)        .filter(order -> order.owner().equals(principal.getName()))
[](#cb364-8)        .collect(Collectors.toList());
[](#cb364-9)  });
[](#cb364-10)}
```

We need to change the return type to `Mono` because `ReactiveSecurityContextHolder` itself is reactive. Finally, we need to add `@EnableReactiveMethodSecurity` to the `Config` class to enable these annotations.

Putting it all together, here is the full source code for `Config`, `Controller`, and `OrderService`.

```
[](#cb365-1)package myservice.service;
[](#cb365-2)
[](#cb365-3)import org.springframework.context.annotation.Bean;
[](#cb365-4)import org.springframework.context.annotation.Configuration;
[](#cb365-5)import org.springframework.security.config.annotation.method
[](#cb365-6)  .configuration.EnableReactiveMethodSecurity;
[](#cb365-7)import org.springframework.security.config.annotation.web
[](#cb365-8)  .reactive.EnableWebFluxSecurity;
[](#cb365-9)import org.springframework.security.config.web.server
[](#cb365-10)  .ServerHttpSecurity;
[](#cb365-11)import org.springframework.security.core.userdetails
[](#cb365-12)  .MapReactiveUserDetailsService;
[](#cb365-13)import org.springframework.security.core.userdetails.User;
[](#cb365-14)import org.springframework.security.core.userdetails
[](#cb365-15)  .UserDetails;
[](#cb365-16)import org.springframework.security.web.server
[](#cb365-17)  .SecurityWebFilterChain;
[](#cb365-18)import org.springframework.security.web.server.authentication
[](#cb365-19)  .RedirectServerAuthenticationSuccessHandler;
[](#cb365-20)
[](#cb365-21)@Configuration
[](#cb365-22)@EnableWebFluxSecurity
[](#cb365-23)@EnableReactiveMethodSecurity
[](#cb365-24)class Config {
[](#cb365-25)
[](#cb365-26)  @Bean
[](#cb365-27)  SecurityWebFilterChain springWebFilterChain(
[](#cb365-28)    ServerHttpSecurity http
[](#cb365-29)  ) throws Exception {
[](#cb365-30)    http
[](#cb365-31)      .formLogin()
[](#cb365-32)      .authenticationSuccessHandler(
[](#cb365-33)        new RedirectServerAuthenticationSuccessHandler("/graphiql")
[](#cb365-34)      );
[](#cb365-35)
[](#cb365-36)    return http
[](#cb365-37)      .csrf(ServerHttpSecurity.CsrfSpec::disable)
[](#cb365-38)      .authorizeExchange(exchanges -> {
[](#cb365-39)        exchanges.anyExchange().authenticated();
[](#cb365-40)      })
[](#cb365-41)      .build();
[](#cb365-42)  }
[](#cb365-43)
[](#cb365-44)  @Bean
[](#cb365-45)  @SuppressWarnings("deprecation")
[](#cb365-46)  MapReactiveUserDetailsService userDetailsService() {
[](#cb365-47)    User.UserBuilder userBuilder = User.withDefaultPasswordEncoder();
[](#cb365-48)    UserDetails luna = userBuilder
[](#cb365-49)      .username("Luna").password("password")
[](#cb365-50)      .roles("USER").build();
[](#cb365-51)    UserDetails andi = userBuilder
[](#cb365-52)      .username("Andi").password("password")
[](#cb365-53)      .roles("USER", "ADMIN").build();
[](#cb365-54)    return new MapReactiveUserDetailsService(luna, andi);
[](#cb365-55)  }
[](#cb365-56)}
```

```
[](#cb366-1)package myservice.service;
[](#cb366-2)
[](#cb366-3)import org.springframework.graphql.data.method.annotation
[](#cb366-4)  .Argument;
[](#cb366-5)import org.springframework.graphql.data.method.annotation
[](#cb366-6)  .MutationMapping;
[](#cb366-7)import org.springframework.graphql.data.method.annotation
[](#cb366-8)  .QueryMapping;
[](#cb366-9)import org.springframework.stereotype.Controller;
[](#cb366-10)import reactor.core.publisher.Mono;
[](#cb366-11)
[](#cb366-12)import java.util.List;
[](#cb366-13)
[](#cb366-14)@Controller
[](#cb366-15)record OrderController(OrderService orderService) {
[](#cb366-16)
[](#cb366-17)  @QueryMapping
[](#cb366-18)  Mono<List<Order>> myOrders() {
[](#cb366-19)    return orderService.getOrdersForCurrentUser();
[](#cb366-20)  }
[](#cb366-21)
[](#cb366-22)  @MutationMapping
[](#cb366-23)  Mono<DeleteOrderPayload> deleteOrder(
[](#cb366-24)    @Argument DeleteOrderInput input) {
[](#cb366-25)    Mono<Boolean> booleanMono = orderService
[](#cb366-26)      .deleteOrder(input.orderId());
[](#cb366-27)    return booleanMono.map(DeleteOrderPayload::new);
[](#cb366-28)  }
[](#cb366-29)
[](#cb366-30)}
```

```
[](#cb367-1)package myservice.service;
[](#cb367-2)
[](#cb367-3)import org.springframework.security.access.prepost.PreAuthorize;
[](#cb367-4)import org.springframework.security.core.context
[](#cb367-5)  .ReactiveSecurityContextHolder;
[](#cb367-6)import org.springframework.stereotype.Service;
[](#cb367-7)import reactor.core.publisher.Mono;
[](#cb367-8)
[](#cb367-9)import java.security.Principal;
[](#cb367-10)import java.util.ArrayList;
[](#cb367-11)import java.util.List;
[](#cb367-12)import java.util.stream.Collectors;
[](#cb367-13)
[](#cb367-14)@Service
[](#cb367-15)class OrderService {
[](#cb367-16)
[](#cb367-17)  private final List<Order> orders;
[](#cb367-18)
[](#cb367-19)  OrderService() {
[](#cb367-20)    // A mutable list of orders
[](#cb367-21)    this.orders = new ArrayList<>(List.of(
[](#cb367-22)      new Order("1", "Kibbles", "Luna"),
[](#cb367-23)      new Order("2", "Chicken", "Skipper"),
[](#cb367-24)      new Order("3", "Rice", "Luna"),
[](#cb367-25)      new Order("4", "Lamb", "Skipper"),
[](#cb367-26)      new Order("5", "Bone", "Luna"),
[](#cb367-27)      new Order("6", "Toys", "Luna"),
[](#cb367-28)      new Order("7", "Toys", "Skipper")
[](#cb367-29)    ));
[](#cb367-30)  }
[](#cb367-31) 
[](#cb367-32)  Mono<List<Order>> getOrdersForCurrentUser() {
[](#cb367-33)    return ReactiveSecurityContextHolder.getContext()
[](#cb367-34)      .map(securityContext -> {
[](#cb367-35)        Principal principal = securityContext.getAuthentication();
[](#cb367-36)        return orders
[](#cb367-37)          .stream()
[](#cb367-38)          .filter(order -> order.owner().equals(principal.getName()))
[](#cb367-39)          .collect(Collectors.toList());
[](#cb367-40)      });
[](#cb367-41)  }
[](#cb367-42)
[](#cb367-43)  @PreAuthorize("hasRole('ADMIN')")
[](#cb367-44)  Mono<Boolean> deleteOrder(String orderId) {
[](#cb367-45)    return Mono.just(orders
[](#cb367-46)      .removeIf(order -> order.id().equals(orderId)));
[](#cb367-47)  }
[](#cb367-48)
[](#cb367-49)}
```

Note that all authorization logic is now contained in the `OrderService`.

In addition to `@PreAuthorize`, Spring Security also offers `@PostAuthorize`, `@PreFilter`, and `@PostFilter` to perform authorization and filtering before and after method invocation.

## Testing auth

For an introduction to testing, please see the [previous chapter on Testing](#ch018.xhtml_testing).

Let’s write end-to-end auth tests. To start with the simplest test and establish a good baseline, let’s verify that we reject unauthenticated requests.

```
[](#cb368-1)package myservice.service;
[](#cb368-2)
[](#cb368-3)import org.junit.jupiter.api.Test;
[](#cb368-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb368-5)import org.springframework.boot.test.autoconfigure.web.reactive
[](#cb368-6)  .AutoConfigureWebTestClient;
[](#cb368-7)import org.springframework.boot.test.context.SpringBootTest;
[](#cb368-8)import org.springframework.http.HttpStatus;
[](#cb368-9)import org.springframework.http.MediaType;
[](#cb368-10)import org.springframework.test.web.reactive.server
[](#cb368-11)  .WebTestClient;
[](#cb368-12)
[](#cb368-13)import java.util.Map;
[](#cb368-14)
[](#cb368-15)@SpringBootTest(
[](#cb368-16)    webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
[](#cb368-17)@AutoConfigureWebTestClient
[](#cb368-18)class AuthE2ETest {
[](#cb368-19)
[](#cb368-20)  @Autowired
[](#cb368-21)  WebTestClient webTestClient;
[](#cb368-22)
[](#cb368-23)  @Test
[](#cb368-24)  void shouldRejectUnauthenticated() {
[](#cb368-25)    String document = "query orders { myOrders { id } }";
[](#cb368-26)    Map<String, String> body = Map.of("query", document);
[](#cb368-27)    webTestClient
[](#cb368-28)      .mutateWith(
[](#cb368-29)        (builder, httpHandlerBuilder, connector) 
[](#cb368-30)                -> builder.baseUrl("/graphql"))
[](#cb368-31)      .post()
[](#cb368-32)      .contentType(MediaType.APPLICATION_JSON)
[](#cb368-33)      .accept(MediaType.APPLICATION_JSON)
[](#cb368-34)      .bodyValue(body)
[](#cb368-35)      .exchange()
[](#cb368-36)      .expectStatus().isEqualTo(HttpStatus.FOUND);
[](#cb368-37)  }
[](#cb368-38)}
```

In this end-to-end test, we reject a GraphQL request with a `302 Found` result, and redirect to another page (the login page). Depending on the service, we could assert another HTTP status code such as `401 Unauthorized`.

If you prefer to test only the GraphQL layer, rather than the whole service end-to-end, you can use `WebGraphQlTester`.

Let’s test that we return the correct orders for the authenticated user.

```
[](#cb369-1)package myservice.service;
[](#cb369-2)
[](#cb369-3)import org.junit.jupiter.api.Test;
[](#cb369-4)import org.springframework.beans.factory.annotation.Autowired;
[](#cb369-5)import org.springframework.boot.test.context.SpringBootTest;
[](#cb369-6)import org.springframework.context.annotation.Import;
[](#cb369-7)import org.springframework.graphql.server.WebGraphQlHandler;
[](#cb369-8)import org.springframework.graphql.server.WebGraphQlInterceptor;
[](#cb369-9)import org.springframework.graphql.server.WebGraphQlRequest;
[](#cb369-10)import org.springframework.graphql.server.WebGraphQlResponse;
[](#cb369-11)import org.springframework.graphql.test.tester.WebGraphQlTester;
[](#cb369-12)import org.springframework.security.authentication
[](#cb369-13)  .UsernamePasswordAuthenticationToken;
[](#cb369-14)import org.springframework.security.core.authority
[](#cb369-15)  .SimpleGrantedAuthority;
[](#cb369-16)import org.springframework.security.core.context
[](#cb369-17)  .ReactiveSecurityContextHolder;
[](#cb369-18)import org.springframework.security.core.context.SecurityContext;
[](#cb369-19)import org.springframework.security.core.context
[](#cb369-20)  .SecurityContextHolder;
[](#cb369-21)import org.springframework.stereotype.Component;
[](#cb369-22)import reactor.core.publisher.Mono;
[](#cb369-23)
[](#cb369-24)import java.util.List;
[](#cb369-25)
[](#cb369-26)@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.MOCK)
[](#cb369-27)@Import(WebGraphQlTest.WebInterceptor.class)
[](#cb369-28)class WebGraphQlTest {
[](#cb369-29)
[](#cb369-30)  @Autowired
[](#cb369-31)  WebGraphQlHandler webGraphQlHandler;
[](#cb369-32)
[](#cb369-33)  @Component
[](#cb369-34)  static class WebInterceptor implements WebGraphQlInterceptor {
[](#cb369-35)
[](#cb369-36)    @Override
[](#cb369-37)    public Mono<WebGraphQlResponse> intercept(WebGraphQlRequest request,
[](#cb369-38)                                              Chain chain) {
[](#cb369-39)      UsernamePasswordAuthenticationToken authenticated = 
[](#cb369-40)        UsernamePasswordAuthenticationToken.authenticated(
[](#cb369-41)        "Luna", "password",
[](#cb369-42)        List.of(new SimpleGrantedAuthority("ROLE_USER")));
[](#cb369-43)
[](#cb369-44)      SecurityContext context = SecurityContextHolder.getContext();
[](#cb369-45)      context.setAuthentication(authenticated);
[](#cb369-46)      return chain
[](#cb369-47)        .next(request)
[](#cb369-48)        .contextWrite(
[](#cb369-49)          ReactiveSecurityContextHolder
[](#cb369-50)            .withSecurityContext(Mono.just(context)
[](#cb369-51)            ));
[](#cb369-52)    }
[](#cb369-53)  }
[](#cb369-54)
[](#cb369-55)  @Test
[](#cb369-56)  void testCorrectOrdersAreReturned() {
[](#cb369-57)    WebGraphQlTester webGraphQlTester
[](#cb369-58)      = WebGraphQlTester.create(webGraphQlHandler);
[](#cb369-59)    String document = "query orders { myOrders { id } }";
[](#cb369-60)    webGraphQlTester.document(document)
[](#cb369-61)      .execute()
[](#cb369-62)      .errors()
[](#cb369-63)      .verify()
[](#cb369-64)      .path("myOrders[*].id")
[](#cb369-65)      .entityList(String.class)
[](#cb369-66)      .isEqualTo(List.of("1", "3", "5", "6"));
[](#cb369-67)    // Luna's orders previously defined in the OrderService
[](#cb369-68)  }
[](#cb369-69)}
```

We register a new `WebInterceptor` and create the authenticated user because Spring Security relies on the `SecurityContext`, which itself is being stored in the Reactor context. In the test itself, we verify that we return no error and then check the order IDs in the response. These order IDs were previously defined in the `OrderService` constructor.

Within the same class, we can also test that an unauthorized user cannot delete orders.

```
[](#cb370-1)  @Test
[](#cb370-2)  void testMutationForbidden() {
[](#cb370-3)    WebGraphQlTester webGraphQlTester
[](#cb370-4)      = WebGraphQlTester.create(webGraphQlHandler);
[](#cb370-5)    String document = """
[](#cb370-6) mutation delete($id:ID){
[](#cb370-7) deleteOrder(input:{orderId:$id}){success}}""";
[](#cb370-8)    webGraphQlTester.document(document)
[](#cb370-9)      .variable("id", "1")
[](#cb370-10)      .execute()
[](#cb370-11)      .errors()
[](#cb370-12)      .expect(responseError ->
[](#cb370-13)        responseError.getMessage().equals("Forbidden") &&
[](#cb370-14)          responseError.getPath().equals("deleteOrder")).verify();
[](#cb370-15)  }
```

Note how this test verifies a GraphQL error, not an HTTP status code, because the overall HTTP response is a `200`. We verify that the message and the path match our expectation.

In this chapter, we covered how to secure GraphQL services with Spring for GraphQL’s useful Spring Security integrations.

# Java client

Spring for GraphQL comes with a client, `GraphQlClient`, for making GraphQL requests over HTTP or WebSocket.

The `HttpGraphQlClient` is for queries and mutations, to execute GraphQL requests over HTTP. The `WebSocketGraphQlClient` is for subscriptions, and executes GraphQL requests over a shared WebSocket connection.

We interact with the base Java interface `GraphQlClient`. We use `HttpGraphQlClient` and `WebSocketGraphQlClient` to create specific instances implementing the `GraphQlClient` interface. The design is similar to `GraphQlTester`, which we [discussed previously in the Testing chapter](#ch018.xhtml_graphql-tester).

## HTTP client

The HTTP GraphQL client is basically a wrapper around a `WebClient`, so we need to provide a `WebClient` when creating a `HttpGraphQlClient`.

```
[](#cb371-1)package myservice.service;
[](#cb371-2)
[](#cb371-3)import org.springframework.graphql.client.HttpGraphQlClient;
[](#cb371-4)import org.springframework.web.reactive.function.client
[](#cb371-5)  .WebClient;
[](#cb371-6)
[](#cb371-7)WebClient webClient = ... ;
[](#cb371-8)HttpGraphQlClient graphQlClient = HttpGraphQlClient.create(webClient);
```

Using builder methods, we can provide specific HTTP settings, such as headers at build time.

```
[](#cb372-1)HttpGraphQlClient graphQlClient = HttpGraphQlClient
[](#cb372-2)  .builder(webClient)
[](#cb372-3)  .header("Special-Header", "true")
[](#cb372-4)  .build();
```

or

```
[](#cb373-1)HttpGraphQlClient graphQlClient = HttpGraphQlClient
[](#cb373-2)  .builder(webClient)
[](#cb373-3)  .headers(httpHeaders -> httpHeaders.setBearerAuth("token"))
[](#cb373-4)  .build();
```

We can also provide other settings such as `url`.

```
[](#cb374-1)HttpGraphQlClient graphQlClient = HttpGraphQlClient
[](#cb374-2)  .builder(webClient)
[](#cb374-3)  .url("/public/graphql")
[](#cb374-4)  .build();
```

Once created, we can’t change any of these client settings. For different settings, we need to mutate the client and use the builder methods again.

```
[](#cb375-1)HttpGraphQlClient newClient = graphQlClient
[](#cb375-2)  .mutate()
[](#cb375-3)  .header("Another-Header", "false")
[](#cb375-4)  .build();
```

## WebSocket client

The `WebSocketGraphQlClient` uses a `WebSocketClient` under the hood. We have to provide a `WebSocketClient` when creating a new `WebSocketGraphQlClient`. Note that `WebSocketClient` is an abstraction with implementations for Reactor Netty, Tomcat [and others](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html#webflux-websocket-client).

Here is an example using a Netty-based implementation.

```
[](#cb376-1)import org.springframework.graphql.client.WebSocketGraphQlClient;
[](#cb376-2)import org.springframework.web.reactive.socket.client
[](#cb376-3)  .ReactorNettyWebSocketClient;
[](#cb376-4)import org.springframework.web.reactive.socket.client
[](#cb376-5)  .WebSocketClient;
[](#cb376-6)
[](#cb376-7)String url = "http://localhost:8080/graphql";
[](#cb376-8)WebSocketClient client = new ReactorNettyWebSocketClient();
[](#cb376-9)WebSocketGraphQlClient graphQlClient = WebSocketGraphQlClient
[](#cb376-10)  .builder(url, client)
[](#cb376-11)  .build();
```

Note that in the WebSocket client we provide the URL via the builder `builder(url, client)`, whereas in the HTTP client it is set via the builder `url`.

Once created, we can’t change any WebSocket client settings. For different settings, we need to mutate the client and use the builder methods again.

```
[](#cb377-1)WebSocketGraphQlClient newClient = graphQlClient
[](#cb377-2)  .mutate()
[](#cb377-3)  .url("https://my-new-url")
[](#cb377-4)  .build();
```

## `GraphQlClient`

We can only use `GraphQlClient` after creating an instance of an HTTP or WebSocket client. In the following examples, `graphQlClient` could be either an HTTP or WebSocket client.

Use `document` or `documentName` to define the request operation and then we can `retrieve` specific parts of the response. Note that this is similar in design to `GraphQlTester`.

```
[](#cb378-1)Mono<List<Pet>> pets = graphQlClient
[](#cb378-2)  .document("query petNames {pets{name}}")
[](#cb378-3)  .retrieve("pets")
[](#cb378-4)  .toEntityList(Pet.class);
```

If we have a subscription request, we use `retrieveSubscription` to get `Flux` instead of a `Mono`.

```
[](#cb379-1)Flux<Pet> pets = graphQlClient
[](#cb379-2)  .document("subscription newPetNames {newPet{name}}")
[](#cb379-3)  .retrieveSubscription("newPet")
[](#cb379-4)  .toEntity(Pet.class);
```

As an alternative to `retrieve`, we can use `execute` and `executeSubscription` to return a `Mono<ClientGraphQlResponse>` or `Flux<ClientGraphQlResponse>` respectively. A `ClientGraphQlResponse` allows access to the full GraphQL response, including GraphQL errors.

```
[](#cb380-1)Mono<List<Pet>> pets = graphQlClient
[](#cb380-2)  .document("query {pets{name}}")
[](#cb380-3)  .execute()
[](#cb380-4)  .map(response -> {
[](#cb380-5)    List<ResponseError> errors = response.getErrors();
[](#cb380-6)    // Your additional code here
[](#cb380-7)  });
```

In this chapter, we covered Spring for GraphQL’s built-in `GraphQlClient`, for making GraphQL requests over HTTP or WebSocket.