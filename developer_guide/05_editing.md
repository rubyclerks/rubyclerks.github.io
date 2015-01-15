---
layout: developer
author: Torsten
---

## Editing

The most **normal** rails way uses resources with edit/show pages and a sleuth of actions for them. OfficeClerk
follows this scheme for most models, but there are exceptions, especially three:

When creating a **Basket** , the object will actually be created immediately and saved. This comes from the thinking
that baskets are disposable, or don't count. It's the Orders and Purchases that matter.

Also when creating an **Order** or **Purchase** the object is created immediately, inclusive of basket. The logic here is
that this is the admin interface, you should know what you are doing. And off course you may delete orders and 
purchases when they are not shiped or received respectively. You can even delete baskets that are not locked (unused).

Orders and Purchases are also the two only classes that don't have a seperate edit screen. They let you edit the basket,
and the order also the shipping info, on a seperate page. But the main *state* changes, that come from changing variables
are implemented by seperate controller actions.

Basket does have a *normal* update action that accepts attributes for the items. But it also implements many edit actions
that implement the discounts and adding/removing products, to make the pos work faster.

Other classes folow the normal rails pattern and are not discussed further.

Some *show* pages implement **in place editing** , specifically the order info-type fields and simple product attributes.
This is so one can make quick edits for simple changes. The gem best_in_place is used for this and demands a certain
json response from the update action. It also uses it's own helper to create the form and is all in all quite a minimal
impact solution.

For javascript use, some *show* pages make the object in question available to the client. This is done by use of the
*gon* gem, which allows setting variables on the *gon* object in ruby. The gem serialises it's object as json into the 
page and so the gon object is available in javascript on the browser. Currently this is done for order,basket and product
show pages, but a more systematic use is planned (see also next chapter).

[**<- Prev** Searches](04_searches.html)    [**Next ->** Extensions](06_extensions.html)


