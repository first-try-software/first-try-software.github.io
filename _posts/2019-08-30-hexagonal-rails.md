---
layout: post
title: Hexagonal Rails
subtitle: Architecturally sound. Rapid application development.
slug: hexagonal-rails
date: 2019-08-30 16:11:00
tags: [oop, architecture, design, patterns]
---
Ruby on Rails is famous for rapid application development. It is super quick and easy to setup a Rails application with some basic functionality. So much so, that Rails was the darling of startups for years.

But, Rails is also famous for applications that grow unweildy over time and become inflexible to change. This rigidity is caused by Rails' numerous violations of basic object oriented design principles.

When classes have more than one responsibility, they become harder to test. This makes it more difficult to reason about the class. As a result, the classes will have lower test coverage, higher churn, and more bugs.

When classes are written in such a way so that extending them requires them to be modified directly, you introduce higher churn and more bugs.

When classes take references to concrete objects rather than relying on interfaces (or duck types in Ruby), they will be much harder to test, leading to lower coverage and more bugs.

_A typical Rails controller violates all of these principles._

Fortunately, there are architectural patterns that can resolve these issues. The Ports &amp; Adapters pattern (also known as hexagonal architecture) is one such pattern. It makes heavy use of the Single Responsibility Principle, the Open/Closed Principle, and the Dependency Inversion Principle, making it a more resilient choice than traditional Rails architecture.

For more on hexagonal architecture and some example Rails code, read [Making Sense of Your Rails Monolith](https://engineering.entelo.com/making-sense-of-your-rails-monolith-ea54692241c3).