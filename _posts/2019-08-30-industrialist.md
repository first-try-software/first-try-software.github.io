---
layout: post
title: The Factory Pattern
subtitle: Factories build things. Industrialist builds factories.
slug: industrialist
date: 2019-09-02 16:23:00
tags: [oop, factory, design, patterns, design-patterns, gem, industrialist]
---
In object oriented design, a factory is a method or class whose only responsibility is to build objects of a particular type. So, an AutomobileFactory would be responsible for building Automobile objects.

Factories are often implemented as switch statements. But doing so requires you to hard code the keys in the factory, either in the switch statement, or as a hash. So, whenever you need to add a class to the factory, you have to modify the factory. This is a violation of the Open/Closed Principle which states that classes should be open for extension, but closed for modification.

One way to resolve this problem in Ruby is to use metaprogramming. In this approach, you define a convention for converting a key into a class name (e.g. :sedan maps to Sedan). Unfotunately, if your keys and class names don't lend themselves to a convention (e.g. :convertible maps to Cabriolet), then you won't be able to use this technique. Furthermore, if your convention ever changes, you'll have to modify the factory, which again is a violation of the Open/Closed Principle.

Industrialist is a gem that solves this problem. It allows classes to register themselves as "manufacturable" by a specific factory when Ruby loads the file. Industrialist can manage any number of factories. It supports defaults, so if a factory is passed a key it does not recognize, it can still build an appropriate object. A single class can be registered under multiple keys. And, keys can be any Ruby object, including hashes, making Industrialist factories super flexible.

For more on extension without modification, check out [Extenstion without Modification](https://engineering.entelo.com/extension-without-modification-cb0f9cfb64a3).

And, then go see Industrialst on [GitHub](https://github.com/entelo/industrialist).
