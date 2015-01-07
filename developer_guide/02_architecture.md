---
layout: developer
author: Torsten
---

## Architecture

The overall goal of the project was to create a **simple** and **extensible** system for small buisnesses.
By simple i mean that it is ok that many people will think there are missing features. The system is implemented 
with rails engines, in ruby, it could not be easier to add functionality.

![System](http://yuml.me/bf8c0f49)

So the **rails application** in our sytem is the SalesClerk. You are free to use the OfficeClerk gem in your own 
app and create a different user experience or copy/clone the SalesClerk and start modifying it.

SalesClerk contains all shop views and the ShopController, not much else. The admin backend is in OfficeClerk. Rails's
modular engines let you create and use as many other Engines as you like and they all use defined ways to modify
and extend your app. Especially in the [entension chapter] we'll go into how this happens.

The rest of the document is concerned mainly with OfficeClerk, and if not familiar with Engines one may think of it as
a rails app, packaged as a gem.


[**<- Prev** Introduction](01_index.html)    [**Next ->** Models](03_models.html)


