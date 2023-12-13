---
layout: post
title: What is SOLID principles?
subtitle: There's lots to learn!
gh-badge: [ star, fork, follow ]
tags: [ solid ]
comments: true
author: NoRoom2013
---

This post have reference
from [SOLID Principles](https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898)

## Table of Contents

[What is SOLID principles?](#what-is-solid-principles)

- [Single Responsibility Principle](#single-responsibility-principle)
- [Open/Closed Principle](#openclosed-principle)
- [Liskov Substitution Principle](#liskov-substitution-principle)
- [Interface Segregation Principle](#interface-segregation-principle)
- [Dependency Inversion Principle](#dependency-inversion-principle)
- [Understanding Low Coupling và High Cohesion](#understanding-low-coupling-và-high-cohesion)

## What is SOLID principles?

> SOLID is an acronym for the first five object-oriented design(OOD) principles by Robert C. Martin, popularly known as
> Uncle Bob.
>
> These principles, when combined together, make it easy for a programmer to develop software that are easy to maintain
> and extend.
>
> They also make it easy for developers to avoid code smells, easily refactor code, and are also a part of the agile or
> adaptive software development.

So, what is SOLID principles?

- [**S**ingle Responsibility Principle](#single-responsibility-principle)
- [**O**pen/Closed Principle](#openclosed-principle)
- [**L**iskov Substitution Principle](#liskov-substitution-principle)
- [**I**nterface Segregation Principle](#interface-segregation-principle)
- [**D**ependency Inversion Principle](#dependency-inversion-principle)

## Single Responsibility Principle

> A class should have one and only one reason to change, meaning that a class should have only one job.
![Single Responsibility Principle](../assets/img/2023-12-12-solid-principles/single-responsibility-principle.webp)

## Open/Closed Principle

> Objects or entities should be open for extension but closed for modification.

![Open/Closed Principle](../assets/img/2023-12-12-solid-principles/open-closed-principle.webp)

## Liskov Substitution Principle

> Every subclass/derived class should be substitutable for their base/parent class.

![Liskov Substitution Principle](../assets/img/2023-12-12-solid-principles/liskov-substitution-principle.webp)

- This principle is very rigid in theory, but in practice it cannot be applied 100%.
- Even in the Android source code there are many examples that violate this principle.

## Interface Segregation Principle

> A client should never be forced to implement an interface that it doesn’t use, or clients shouldn’t be forced to
> depend on methods they do not use.

![Interface Segregation Principle](../assets/img/2023-12-12-solid-principles/interface-segregation-principle.webp)

## Dependency Inversion Principle

> Entities must depend on abstractions not on concretions. It states that the high-level module must not depend on the
> low-level module, but they should depend on abstractions.

![Dependency Inversion Principle](../assets/img/2023-12-12-solid-principles/dependency-inversion-principle.webp)

## Understanding Low Coupling và High Cohesion
> doing...