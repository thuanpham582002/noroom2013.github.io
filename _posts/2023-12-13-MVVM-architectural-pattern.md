---
layout: post
title: MVVM architectural pattern
bigimg: /img/image-header/california.jpg
tags: [ Architecture Pattern ]
---

In this article, we will find something out about MVVM pattern, it is inherited from MVC pattern. But definitely, it has
some changes when compared to MVC pattern. So, we will understand how to use it, how to differentiate between MVC
pattern and MVVM pattern.

Let's get started.

<br>

## Table of contents

- [Analysis Problem](#analysis-problem)
- [Definition of MVVM Pattern](#definition-of-mvvm-pattern)
- [When to use](#when-to-use)
- [Benefits & Drawback](#benefits-&-drawback)
- [Wrapping up](#wrapping-up)

<br>

## Analysis Problem

The caution that was born MVVM pattern is as same as
with [MVC pattern](http://ducmanhphan.github.io/2019-07-27-MVC-architecture-pattern). But MVVM is used to prevent some
drawbacks of MVC pattern such as:

- In MVC pattern, View and Model can be interact each other. So, we usually validate data from Model or use data logic
  in View. So, it makes automated unit testing difficult.
- It is relevant to the security.

<br>

## Definition of MVVM Pattern

According to [wikipedia.com](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel), we have the definition
of MVVM pattern:

```
MVVM pattern is a derivation of the Model-View-Controller (MVC) architectural pattern, and is used mostly for building user interfaces.

In MVVM, the presenter assumes the functionality of the middle-man.

In MVVM, all presetation logic is pushed to the presenter.
```

And MVVM pattern originated in the early 1990s at Taligent, a joint venture of Apple, IBM, and Hewlett-Packard.

Below is the content of each part in MVVM pattern.

- The Model has entities and services.

  Entities is used to contain data that is mapping with table in database for utilizing some other reasons.

  Services, can be used DAO pattern, or Repository pattern, are thin layer between Application layer and Data Access
  Layer. They normally manage CRUD opertions with database in local or remote.

- The View has responsibilities that interact with users.

  It does not contain any logic. It will route user inputs and commands (events) to the Presenter.

  The View usually has a reference to its Presenter.

- The Presenter is the intermediate part between View and Model. It will play same role as Controller in MVC pattern.

  All business logic, data logic, validate input, receives events from Views, converts data from View to Model or from
  Model to View is implemented in Presenter.

  When compared to the View and Controller in the MVC pattern, the View and Presenter present in the MVVM pattern are
  fully decoupled from each other and they communicate by means of an interface. (The Presenter interact with the Views
  via View interface, it means that the Presenter can perform all presentation and navigation tasks without any
  dependency on the actual UI technology being used)

  ![](../img/Architecture-pattern/MVVM-pattern/MVVM-pattern.jpg)

  And we have sequence diagram of MVVM pattern:

  ![](../img/Architecture-pattern/MVVM-pattern/Sequence-diagram-MVVM-pattern.png)

<br>

## When to use

- Our screen has ```bi-directional-flow```, it means that user interactions need to request something from our Model,
  and the result of this request will affect the View.

- The View affected by the updates from Model are very limited.

- MVVM pattern is not used in a case when the UI is updated without user interactions, like updating UI when an event
  happens in the Model, this approach is closer to MVVM more than MVVM.

<br>

## Benefits & Drawback

1. Benefits
    - The View does not interact directly with the Model. This isolates the View implementation bettern than in MVC and
      allows easier automated unit testing of the Presenter and Model.

    - The ability to change the UI from Web to Window or Mobile is very easy.

    - Low maintaince cost


2. Drawbacks
    - The Presenter tends to expand to a huge all-knowing class if we are not careful enough and do not break our code
      according to Single Responsibility Principle.

    - Increased complexity.

    - Extra learning curve.

<br>

## Some patterns that are relevant to MVVM pattern

- ```Observer pattern```

<br>

## Wrapping up

- The end user interacts only with the View.

- One View is mapped only to one Presenter.

- View references Presenter but it has no reference to Model. And the Presenter is also aware of the View that
  associated with it.

- The pattern facilities two way communication between the View and the Presenter.

- There are two other implementations of MVVM pattern such as Passive View and Supervising Controller.

    - The Passive View is completely controlled by Presenter. By implementing MVVM Passive View, it's much easier to
      handle concurrency and multithreading.

    - In Supervising Presenter, the View interacts directly with the Model to perform any simple data binding that can
      be declaratively defined, without the Presenter. The Presenter updates the Model. It only changes the state of the
      View when complex UI logic that cannot be declaratively specified is required.

      ![](../img/Architecture-pattern/MVVM-pattern/supervising-presenter-mvvm.png)

    - Compare to other variations of MVVM, such as Passive View, the Supervising Presenter pattern makes simpler code a
      higher priority than complete testability. The Supervising Presenter pattern requires less code than other MVVM
      patterns because it uses data binding. The code is easier to maintain because simple UI changes do not require
      code changes in the Presenter to update the View.
      <br>

Refer:
`todo`
https://ahmed-shaaban-elhdah.medium.com/mvvm-not-always-better-than-mvp-f50efb69a054