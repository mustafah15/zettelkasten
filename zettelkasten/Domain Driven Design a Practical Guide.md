---
tags:
  - software-design
type:
  - permanent
related: "[[domain driven design]]"
---

## Introduction

Domain Driven Design (DDD) originates from a book called Domain Driven Design by Eric Evans. One of the key goals of the book is to try to create a software implementation that is based on an evolving model that is understood by domain experts. It's about creating a communication channel between the domain experts and the software developers. As far as goals go for domain-driven design one of the key goals within it is to take a large system, or a large domain, and to break it down into smaller pieces. the problem is that we larger domain you have the harder you can deal with it and the harder to model a large coherent model. DDD as a design approach gives us a set of guidelines and a set of techniques that we can use to determine the boundaries, essentially between those smaller pieces within the larger domain. 

In this ^book^ we will go through using DDD with practical examples to decompose problems into domains, how to determine the bounded context for each smaller domain, and how to build anti-corruption layers to make sure that there's no information leakage between the domains also will use domain activities, domain object and all DDD fancy terms across that journey, Last but not least we will build an actual NodeJS with Typescript Implementation for our architecture.

## Why Domain-Driven Design
In simple terms, as DDD Focuses on the essential parts of the problem domain and simplifies it removes most of the necessary complexity, DDD gives the ability to express business logic in the clearest way possible is a trait that makes DDD so appealing at enterprise-level applications. it's hard to estimate how important that is, as the most difficult task in modern business line software is to manage complexity and keep it under control.

## What is A Domain?

A domain in the context of the software usually refers to the business or the idea that we are modeling into software. As it contains the business’s problems, operations, logic, and rules. Understanding the domain is crucial, as the software’s purpose is to address and solve real-world problems within this domain.
Domain experts are the people who understand the business and not necessarily the software.

The key goal of DDD is to build a domain model that the domain experts understand, and the model should represent our understanding of the domain and the software should be an implementation of this model. This model is usually written in *Ubiquitous Language* which we will define later.
## DDD Common Terms

In order to navigate this book easily let's explain some DDD common terms first

### Ubiquitous Language 
Ubiquitous Language is A common language structured around the domain model and shared by developers and domain experts, It’s used to describe all aspects of the domain, ensuring that all communication is precise and meaningful. you might have noticed in many projects domain experts and developers use different sets of terms when they talk about the domain which leads to misunderstanding and slows the process down, the Ubiquitous Language helps to eliminate this issue by explicitly pointing those differences out and adjusting the terminology to have one unified language. 
let's say for example that you have 

### Bounded Context
### Core Domain

## Decomposing The Domain

## Domain Objects

## Hexagonal Architecture 

## Implementation 


