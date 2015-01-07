---
layout: developer
author: Torsten
---

## Searches

As you see from the [User Guide](/user_guide/02_baskets.html) the layout is quite "resourceful" and apart from Items
quite similar for every [Model](03_models.html). The index / search pages always list most important attributes,
lets you search for attributes and lets you sort the result.

All this is achieved in quite a compact form by using several tools. The actual search is performed by
[**ransack**](https://github.com/activerecord-hackery/ransack) which transforms form field names to ActiveRecord 
queries. For example a name_cont field will query the object's atrribute name if it contains the given string.
All basics are covered and ransack goes much further by searching in associations and even in combinations (and/or)
of those. 

This is very usefull, eg when searching Orders for certain products (ie Order->basket->items->products.name), or 
even "just" for products. As the Products name may be a combination of Product Item and Product Line name, or just
a normal name, the actual search is :name_or_product_name_cont.

Apart running the search, Ransack also provides two very nice helpers. One is for creating the actual form, here we
use *search_form_for* and in the form various helpers to crete input fields. 
The other helper creates links to make the sorting possible.

All searches are implemented as gets to make bookmarking possible. Ransack lets you build the search of the params and
returns a lazily evaluated object. As searches may return very many items, the result is limited and **paginated**.
That means by default 20 items are shown and links to flip throught the pages are shown.  

An external gem **will_paginate-bootstrap** styles the page links acording to bootstrap,  and **will paginate** 
will make the search return only the one page needed, making the search much much faster. 
The original search scope is available on the page anyway, and usually a total is displayed
 (resulting in one more query)

As we use bootstrap for styling, form-groups are used for controls and labels, labels use form-control and the whole
search is usually a form-horizontal. Some of the radio button add-ons may use input-controls, as per 
[bootstrap documentation](http://getbootstrap.com/components/#input-groups-checkboxes-radios).

[**<- Prev** Models](03_models.html)    [**Next ->** Editing](05_editing.html)


