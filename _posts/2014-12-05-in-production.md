---
layout: news
author: Torsten
---

Yes, it done. We're ready to receive [Orders](http://auringostaitaan.fi)

## Online

The whole team has worked hard to get this done, so now we have 2 installations online.

Just a reminder, the first has been used as a backend for 10 months already. 
I'm still careful with the versioning, though i think that a 1.0 would be deserved.

### Shop done

One of the major steps was the actual store, we called it sales_clerk. 
A lot of design work there and technically the checkout.
Definately a time to see the basket design choice pay off.

The second site is not actually a shop, but a reseller presence. Still a buisness needs to sell and so all the 
order fullfilment (with product management etc) is handled by the "invisible" backend, office_clerk.

### Some details

To name but a few of the new features:

- product and categories now contain summaries for toal control in list views. 
- one page checkout is done. Payment is (optionally) collected after.
- start to see some nice js use in fade effects and the like (mostly shop)
- better search/view for what is online and only showing products with stock online.
- completely extenalized independent xx_cerks, for printing/accounting cane be plugged. Also gives extension developers a start on how to
- off course lots and lots of "little" things, one of which just comes to mind: ssl config option

I did go over the spree migration again for the second shop, but the payment is still open (we use bank transfer)

All in all, we're all very **happy** and just in time to get on with x-mas.

Up next: stripe payment and (gitbook) documentation.