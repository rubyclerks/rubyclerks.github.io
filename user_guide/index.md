---
layout: user
author: Torsten
---

## User Documentation

This is the *User* guide for OfficeClerk.

A User of office clerk is the admin of the system. He uses the OfficeClerk back-end software and this is what 
is descibed in this guide.

The guide is also a good starting point for developers to see *what* the system does, before delving into *how* it does it.
The developers guide is [here](/developer_guide/index.html)

### Introduction

A good one page introduction of the system is the [Features](/features.html) page. This guide will go through those same
topics in more detail, also providing screenshots.

![Header](images/header.png)

This shows the standard header and the document will go through those menu items one by one (as the index on the right shows)

Almost all items provide a list/search view and from there let you create new items or edit existing.

Only the first and last are quite different: Shop is really just a quick link to your root, ie whatever application you have running. As you see by the name, we assume this is a shop. and the last, the manage link, provies a quick overview
over the system configuration. But it will be up to the developer to edit this.

#### Products

As this is (albeit small) ecommerce platform, it is all about selling. What you sell is called a Product (even it may be a service product), so we will start with that. 

Products have a cost and a price and other attributes.
We assume you have one Supplier per product and each product is in exactly one Category.
So Suppliers and Categories are handled next.

#### Selling and Buying

An Order captures the transaction of selling products. They may be in different states and include payment and shipment 
information additionally to the obvious items sold.

The system keeps track of your inventory (assumed to be in one place) and when an order is shipped, inventory is deducted.

The only way to get inventory into the stusyem is by purchacing, ie buying from one of your suppliers. 
This will be handled next.

#### Other clerks

Technically the system is split into sevral clerks. These are not neccessary for the functioning of the OfficeClerk, 
but very useful for a usual buisness. We shall descibe the three standard ones:

- SalesClerk  (online shop)
- AccountantClerk  (reporting)
- PrintClerk and Postclerk for invoicing and shipment
