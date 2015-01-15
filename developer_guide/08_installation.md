---
layout: developer
author: Torsten
---

## Installation

Before explaining how to create a rubyclerks installation, I would like to say, from many years of e-commerce development,
that **shops are different**. Just like with real shops, online shops want to be different from the next, provide not 
only unique products, but also a unique experience and in their own style. There is currently no "one click" installer
because of this.

That doesn't mean you can't get up to speed very very quickly, it just means we expect you to modify your shop **greatly**

This considereation has affected the architecture design, and specifically the fact that **SalesClerk** , the online shop
part, is an application. In broad strokes installation involves copying (or cloning) an existing one. Especially to a 
seasoned rails (engine) user this may sound strange at first, but before long you will see why. You will have changed
just about evey part of the system, some more some less, and trying to stay compatible with a possibly evolving gem
would just create more headache without extra benefit.

#### Clone or fork sales_clerk

You choice really. If you fork, rename your repository, clone it and start.

If you're just testing/evaluating you may just clone to your harddrive. Later you can change the origin and the name. 
Or completely remove the .git folder and run git init and start fresh.

Both ways are designed to **transfer ownership to you**

####  Get ready

Off course once you have the rep, you'll need to **bundle** and **rake db:migrations**

Then you'll need an admin, which you can create in the console or by running **rake db:create_admin** , which creates
admin@example.com with "password".

And you're ready to go, ie **rails s**

But don't get your hopes too high, it's like walking into an empty shop. In fact our empty shop.

#### Add data

Go to the admin side (localhost:3000/categories) and create a few categories and then a few products. 
If you add pictures you'll start to get a feel.

If you come from spree, check out the migrate_spree repository, it's a start. If you have other existing data you're on
your own. If you have no data, start clicking (create locally, use rake db:fixtures:dump to 
export and db:fixtures:load to load in production)

#### Change the style

Ok, you don't need me to tell you that, you probably have a customer or your own ideas. Hack away at the css and 
haml templates. Change the behaviour in the (shop) controller and helpers.

Remove all reference to Auringosta while your at it, but please leave a link to rubyclerks and possibly rubydesign.

#### Add extensions

As mentioned, this is quite intentionally a minimal system. Off course you can change your code, but you can also add
extensions.

And if you are developing new code that may be off use to others, consider writing it as an extension and sharing it.
If it's good maybe even in the rubyclerks orginisation, but at least it should be mentioned on the wiki.

## Existing app

To integrate SalesClerk into an existing app, you basically have to copy all relavant parts over to your app. Clone the
sales_clerk repository and just move the routes, and basically everything in the app directory. You can generate new
migrations with rake, so you get current timestamps.

## Beyond

If you like it, like us on facebook (just joking, i'm over 40).

I mean join the mailing list, ask questions, add issues and send pull requests. 

Pull requests preferably on a topic branch, and if it's bigger talk first.

Other than that, enjoy :-)

[**<- Prev** Testing](07_testing.html)


