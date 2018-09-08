---
layout: single
title:  "A Mental Model of Microservices"
categories: Cloud
comments: true
---
When you start designing a software, you either think of it as one big thing or as small connected things.
System architects call the first approach as Monolithic, which is the traditional way to structure software. Microservices in the other hand decomposes the system as a group of services that are able to communicate with each other via APIs. Many companies nowadays consider transforming to Microservices, which might not be the best solution for all, but separating complex systems into smaller parts could resolve many problems.

## Problems in Monolith Pattern:

Monolithic software becomes larger by the time either from adding more functionalities or serving a huge number of users. This makes the Monolithic difficult to handle by developers. Despite its simple implementation and deployment, scaling Monolithic requires to replicate the entire software into multiple machines, which is a waste of resources. In addition, a fail in one function may affect the whole system.
 

## Monolith vs. Microservices 

|Monolithic | Microservices|
|-----------|---------------|
|big code   | small codebase|
|coupling services| independent services within containers|
|difficult to debug| easy debugging|
|hard to scale| easy scaling|
|one long deployment| multiple independent deployments|
|no fault tolerace| fault telorance|
|strict tech stack| flexible tech stack|
|one database| multiple independent databases for each service|
|no commuincation overhead| communication overhead between services|



## Microservices Defination

Here are two definitions from microservices' pioneers:

"A microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API" ~ Martin Fowler

"Small autonomous services that work together, modeled around a business domain" ~ Sam Newman


## Principles of Microservices

[Conway's law](https://en.wikipedia.org/wiki/Conway%27s_law)  states that "organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations.". Microservices are selected to serve the business domain and the organization assigns dev teams for each microservice. Each team is independent of another and they can select the suitable platforms to run the microservice painlessly while meeting consumer needs.
Microservice should be independent, deployed automatically using CI/CD, and each manages its data storage and resources.

| ![](https://i.imgur.com/LgVKiBD.png)| 
|:--:| 
| *Microservices Principles taken from [Sam's Newman book](http://shop.oreilly.com/product/0636920033158.do)* |



## Transition from Monolithic to Microservice

The diagram below shows when and how a company considers the transition to Microservices.


| ![](https://i.imgur.com/1Bl14tz.png)| 
|:--:| 
| *Transition from Monolithic to Microservices* |


## Monolithic pattern vs Microservices using Taxi-hailing app example 


| ![](https://cdn-1.wp.nginx.com/wp-content/uploads/2016/04/Richardson-microservices-part1-1_monolithic-architecture.png)| 
|:--:| 
| *Monolithic Architecture taken from [NGINX](https://www.nginx.com/blog/microservices-from-design-to-deployment-ebook-nginx/)* |


| ![](https://cdn-1.wp.nginx.com/wp-content/uploads/2016/04/Richardson-microservices-part1-2_microservices-architecture.png)| 
|:--:| 
| *Microservices Architecture taken from [NGINX](https://www.nginx.com/blog/microservices-from-design-to-deployment-ebook-nginx/)* |


**Resources**
- [Building Microservices](http://shop.oreilly.com/product/0636920033158.do) 
- [Martin Fowler blog](https://martinfowler.com/articles/microservices.html)
- [Microservices: From Design to Deployment, NGINX](https://www.nginx.com/blog/microservices-from-design-to-deployment-ebook-nginx/)




