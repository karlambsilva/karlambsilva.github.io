---
layout: post
title: Software Testing Heuristics
description: Overview of heuristics in general, and discuss the most popular ones related to software testing.
date: 2020-06-13 18:05:55 +0300
image: '/images/23.jpg'
tags: [heuristics, software testing, exploratory testing]
---

In this post, I will give an overview of heuristics in general, and discuss the most popular ones related to software testing. Let's start?

Introduction
============

Psychologists [Amos Tversky](https://en.wikipedia.org/wiki/Amos_Tversky) and [Daniel Kahneman](https://en.wikipedia.org/wiki/Daniel_Kahneman) were pioneers in studies related to heuristics and cognitive biases. In a study from 1974, they define heuristics as:

> Principles which **reduce** the complex tasks of assessing probabilities and predicting values to **simpler judgmental operations**.

In other words, we can define them as cognitive shortcuts. They're also known as 'rule of thumb' where a procedure can be applied based on practical experience. However, it does not have to be strictly accurate, and it might not work for every situation.

Probably, you already have used heuristics in your daily routine without knowing the concept. Imagine that there is someone in your kitchen struggling to open a stuck jar lid. Which tips do you will give to them?

![](https://miro.medium.com/v2/resize:fit:700/1*aU2iJvJFTYtcmq0AOGxbkg.png)

Photo by [Ella Olsson](https://unsplash.com/@ellaolsson?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

Usually, people say things like: 'tap the lid', 'run the lid under hot water', 'wrap the lid in a dish towel', and so on. Have you heard any of those? They can be considered as 'opening jar heuristics'.

For psychologists, the use and development of heuristics are innate for humans, and they helped our ancestors to survive. Nowadays, heuristics are essential and are applied in multiple areas (besides psychology). For example, when I am testing a new software application, I know some things that are interesting to try, so those are my test heuristics.

It's also important to realize that heuristics are fallible and they can lead to systematic errors because of biases related to our previous experiences. Even if with those limitations, we can say that heuristics are very useful to find 'good enough' solutions.

Well-known Software Testing Heuristics
======================================

The following list represents a small set of well-known software testing heuristics that can be easily applied to our daily testing. All of those testing heuristics are discussed in more detail on the Explore it! [book](https://pragprog.com/titles/ehxta/) by Elisabeth Hendrickson. The book has several chapters covering the discussed topic, and an appendix containing all the test design heuristics presented throughout the volume. It's **TOTALLY** worth reading.

Goldilocks
----------

The name of this heuristic comes from the British fairy tale called 'Goldilocks and the Three Bears'. The story is about a girl named Goldilocks which found three bowls of porridge (one for each bear): the first one is too hot, the second one is too cold, and the third is just right.

Applying to test, we can convert this into *too big*, *too small*, or *just right, *so it can apply for ranges of dates, numerical values, length of strings, etc. When applying this heuristic is important to pay attention to unhelpful error messages and data truncated without notice.

Count
-----

For Elisabeth, all systems have things that you can count, and you can use heuristics to vary that count. For example:

-   *Zero*, *one*, and *many*: do search that returns 0, 1, and more than 1 element. Sometimes, you will find messages like '0 items returned', '2 record found', and so on.
-   *Too many* and *too few*: explore situations where you have more or fewer things than the system can handle. As an illustration, once, I found a bug, while testing a feature that lists the orders by users, that was reproducible only if the user did not have a relationship with the 'order' entity.

Sequences
---------

This heuristic suggests looking for ideas related to shaking up sequences and interactions. To explain, Elisabeth says that sometimes users' operations result in non-logical actions that might involve pressing random keys or arbitrary deleting some stuff. For this reason, it's important to explore variations in the order of operations. For example, try to do things in reverse order, undo everything, etc.

Sorting
-------

When dealing with applications in which items can be sorted, Elisabeth suggests looking for alphabetically versus numeric sorting. Sometimes, developers do not take into consideration the type of data used in the column. For example, when sorting a list with the following numeric values: 8, 12, and 20, the 12 value should come after 8. However, if the list is alphabetically sorted, 12 will come before 8.

Additionally, make sure that the sorting criteria are consistent across multiple pages.

Input Method
------------

It's also important to vary the way that you enter data or how do you navigate on the application. Sometimes, validation rules are not applied to all input methods. Particularly, explore actions like typing, copy/paste, import, and drag/drop. For example, try to navigate in a form using only the keyboard and check that navigation is correct and all the validations occur normally.

Bookmark It
-----------

Usually, users bookmark all kinds of pages, including pages that are not designed for that. For example, pages that are in the middle of a sequence. When applying this heuristic, look for links that redirect users to pages with partial data, 404 pages, and duplicate transactions.

Mnemonics
=========

Mnemonics are used to help us remember something. For example, you can use HOMES to memorize the names of the five Great Lakes: **H**uron, **O**ntario, **M**ichigan, **E**rie, and **S**uperior. Definitely, they are cognitive shortcuts that help our memory during the process of retrieving information. Because of that, we can also say that they're heuristics.

In this post, I will explain two mnemonics that I use very often on my routine. However, in reality, there are lots of mnemonics related to software testing. In a future post, I will talk about some of them in more detail.

RCRCRC
------

This mnemonic was presented by Karen Johnson, and its main objective is to help with regression tests. In this case, each letter represents a word that is relevant to this kind of test. For example:

-   **R** stands for **Recent**: what new features or new areas of code have been added?
-   **C** stands for **Core**: what essential or critical functions or features must continue to work?
-   **R** stands for **Risky**: what features or areas of code are inherently riskier?
-   **C** stands for **Configuration Sensitive**: what code is dependent on environment settings?
-   **R** stands for **Repaired**: what code has been changed to address defects and therefore may have created issues?
-   **C** stands for **Chronic**: which code may seem to be chronically breaking or having issues?

I SLICED UP FUN
---------------

The I SLICED UP FUN mnemonic was proposed in an [article](http://www.kohl.ca/articles/ISLICEDUPFUN.pdf) by Jonathan Kohl which purpose is to guide your thinking while testing mobile applications. Jonathan suggests using the app under test focusing on each of these areas, one at a time. A brief explanation of each area:

-   **I** stands for **Inputs into the device**: ways that you can interact with the device. For example, built-in keyboard/keypad, touch screen gestures, and typing, etc;
-   **S** stands for **Store**: try to find out information about the application requirements for store submissions;
-   **L** stands for **Location**: your current location might have an impact on your tests. Look for geolocation errors, movement, and stopping suddenly;
-   **I** stands for **Interactions/Interruptions**: try to run other applications at the same time while testing your app;
-   **C** stands for **Communication**: test how your app interacts with features related to communication. For example, texting, emails, calls, voicemail, etc;
-   **E** stands for **Ergonomics**: after some time using your app, do you have signs of physical stress? Look for small screens, sore back, sore fingers, etc;
-   **D** stands for **Data**: look for the data that is processed by the app. For instance, types of input, media, updates, and so on;
-   **U** stands for **Usability**: while testing your app, look for any actions that are awkward, confusing, or slow;
-   **P** stands for **Platform**: it's important to look at some details related to the device that the application needs to run. For example, make sure that you know the technical details about the device and the operating system version you are using.
-   **F** stands for **Function**: check that items are placed on the application, and they behave as expected. For instance, have you clicked all the buttons on the app? or fill in every form?
-   **U** stands for **User Scenarios**: imagine what some real users would do in your application. Try to create scenarios of real people and how they react using the software.
-   **N** stands for **Network**: explore scenarios related to poor network connection, moving from one network to another, network without data, etc.

Other Mnemonics
---------------

If you are interested in knowing other mnemonics, you can check the [mind map](https://findingdeefex.com/2015/05/04/testing-mnemonics-desktop-download/) created by Del Dewar where he compiles the mnemonics from [Karen Johnson's card deck](http://karennicolejohnson.com/2012/07/testing-mnemonics-as-a-card-deck/), [Lynn McKee's mnemonics page](http://www.qualityperspectives.ca/resources_mnemonics.html), and posts from the [Moolya blog](https://moolya.com/blog/).

![](https://miro.medium.com/v2/resize:fit:700/1*0WkoVlgUa6inFSGrf8c_2A.png)

Testing Mnemonics mind map by Del Dewar.

Personal Heuristics
===================

As practitioners, probably, we already have our heuristics. At first, it can be hard to identify. However, you can start reflecting on it by answering the following questions:

-   What things do you consider when starting to test a new application?
-   What are your actions during and after each testing session?

Additionally, you can also use and modify those common heuristics to create your list.

References
==========

The content of this post is based on the following resources:

[

Software Testing Heuristics: Mind The Gap!
------------------------------------------

### By Richard Bradshaw and Sarah Deery As with all testing methods and techniques, a deep understanding of what they are...

www.ministryoftesting.com

](https://www.ministryoftesting.com/dojo/lessons/software-testing-heuristics-mind-the-gap?source=post_page-----97783f7317da--------------------------------)

[

Explore It!
-----------

### Uncover surprises, risks, and potentially serious bugs with exploratory testing. Rather than designing all tests in...

pragprog.com

](https://pragprog.com/titles/ehxta/explore-it/?source=post_page-----97783f7317da--------------------------------)

[

What are Test Oracles and Test Heuristics?
------------------------------------------

### Within the world of testing and quality assurance, we often hear the words Test Oracles and Test Heuristics, but what...

devqa.io

](https://devqa.io/test-oracles-test-heuristics/?source=post_page-----97783f7317da--------------------------------)

[

Testing Mnemonics - Desktop Download
------------------------------------

### Good news, I have a present for you all. :-) Testing mnemonics are not exactly new, but are still fantastic ways of...

findingdeefex.com

](https://findingdeefex.com/2015/05/04/testing-mnemonics-desktop-download/?source=post_page-----97783f7317da--------------------------------)

-   *Judgment under Uncertainty: Heuristics and Biases* [article](https://science.sciencemag.org/content/185/4157/1124) by Amos Tversky and Daniel Kahneman;
-   *Testing Without a Map* [article](https://www.developsense.com/articles/2005-01-TestingWithoutAMap.pdf) by Michael Bolton;
-   *Test Heuristics* [cheat sheet](http://testobsessed.com/wp-content/uploads/2011/04/testheuristicscheatsheetv1.pdf) by Elisabeth Hendrickson, James Lyndsay, and Dale Emery;
-   *Test Mobile Applications with I SLICED UP FUN* [article](http://www.kohl.ca/articles/ISLICEDUPFUN.pdf) by Jonathan Kohl;

In conclusion, software testing heuristics can help us to make decisions, solve problems, and give insights when we don't have ideas on how to start testing. On the other hand, keep in mind that they are fallible and might lead to errors because of biases.

As has been noted, it's important to study heuristics, understand when they can be used, apply them to your context, and reflect on their efficacy. On your daily routine, which testing heuristics do you already use? Which ones are you planning to use?

Looking forward to the next posts!