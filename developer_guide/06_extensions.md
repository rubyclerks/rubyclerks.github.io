---
layout: developer
author: Torsten
---

## Extensions

As OfficeClerk is planned as a minimal system, extensions are neccessary for what may seem like even basic functionality.
But shops, merchandise, countries, taxes, shipping and payment systems all differ, sometimes even a lot, for it to 
be impractical to add every functionality. And since we we need extensions anyway, it is most flexible to use them 
whereever possible.

Extension naming follows the convention of short_name_clerk, and some of the currently available extensions are post,
accountant and print.

To develop your own, the best way is to start from a copy of an existing. Extensions may vary greatly in what they try
to achieve, so they too are rails engines. This gives them the possibility to add models,controlers, code, views,
and overide views. In detail:

To **add** a model, controller, helper or view the extension uses normal rails conventions.

To **change exising code** the extension may use ruby's class_eval method. To load such code one may place it into the
normal location in file called class_decorator.rb  and then load all decorators in the engines init like for example 
[here](https://github.com/rubyclerks/print_clerk/blob/master/lib/print_clerk.rb).

To **change a template** the extension may just define a same name and path template to redefine it. If there is a need
to change the load order of the extension for this to have effect, that may be done by defining 
[config.railties_order](https://github.com/rubyclerks/office_clerk/blob/master/lib/office_clerk/engine.rb).

Another technique may be to use javascript to **manipulate the dom**. To do that one must get the javascript onto the page
and have defined dom elements to work with. Also the gon-data as descibed in the previous chapter may be useful.
To get the javascript loaded the extension may advertise it's need to add javascript or stylesheets by having 
a [office_assets function](https://github.com/rubyclerks/print_clerk/blob/master/lib/print_clerk.rb) on it's 
engine that returns the assets name that shall be included. 
OfficeClerk will add **both** javascript include and stylesheets tags for that name to the head section.

To find the actual elements to target you must look at the respecive template. If there is not enough unique
identifiers please get in touch. It should be noted that this techique allows for adding, removing and editing
of content. To generate html in js one may off course do string manipulation, or use any of the many js template
solutions. A futher possibility is to use
[**ajax**](https://github.com/rubyclerks/print_clerk/blob/master/app/assets/javascripts/print_office.js.coffee) 
and generate the html on [the server](https://github.com/rubyclerks/print_clerk/blob/master/app/controllers/orders_decorator.rb#L4).

To **edit styles** one may use the above technique to add style to admin pages.

[**<- Prev** Editing](05_editing.html)    [**Next ->** Testing](07_testing.html)


