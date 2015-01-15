---
layout: developer
author: Torsten
---

## Developer Guide

This is the **developer** guide for the rubyclerks sytsem. It explains **how** the system is built, not 
as much *what* it does. To get aquainted with what the system does, please read the [User Guide](/user_guide/01_index.html) 

As all clerks are built on [ruby on rails](http://rubyonrails.org/) it is assumed that you are familiar with at least the 
basics of ror. [Engines](http://guides.rubyonrails.org/v4.1.8/engines.html) are relatively new and it may help to read the
guide to understand better, but when in doubt one may thing of an engine as a packaged application.

### Tool choices

As Rails is a framework, it leaves the developer with many many choices how to do things. Many smaller ones will be explained in later chapters, but here is a short summary of the main choices that were made:

#### AR and Database independence

We use the rails standard ActiveRecord for database access and the model layer. And while AR allows to write sql, we 
specifically don't do that to leave you the choice of database. Ie rubyclerks should work with any AR supported database.

#### Haml

To create views rails standard uses erb. While erb is easy for people coming from html, it is unneccessarily cluttered.
We use [haml](http://haml.info/) for all views. Engine views may be overriden in an app, and this may be done with any 
template format, ie an erb template may override a haml one.
Haml's style friend is **sass**, and as a basis **bootstrap** is used.

#### Good testing

There is an overview of [Testing](/06_testing.html), and it is done with rspec. But the main point about testing is not
the framework (or if you like it) but to **do it**. We currently have close to 400 tests and no bug gets fixed
or feature added with more testing, and off course all old ones passing.

## Contents

You can see from the menu on the right how this is going to go. First a brief overview of the **architecture** of the
system, ie how different clerks work together. Then a quick look at the **models** involved and their relationships.
Next two chapters on the main topics of **index** and **edit** pages, and then an introduction on how to build your 
own clerk, an **extension**.

The chapter on **testing** will cover extension testing too, and last but not least an **installation** guide.


   [**Next ->** Architecture](02_architecture.html)


