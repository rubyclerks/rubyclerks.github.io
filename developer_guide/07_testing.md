---
layout: developer
author: Torsten
---

## Testing

Testing is the only reliable way to know that a software does what it should. When developing anything larger-ish
one can even turn that around and say: What is tested defines what an application should do. It also the only way
to make updates to running online application and sleep well.

I look at testing as diagonals in building: you can put a structure up without quite fine, but before you put any weight
on it (like  a roof) you'll need to put diagonals for stability. Testing is in the same way not really needed or even 
helpful right at the beginning. It may even be in the way while still going up. Rather it is what gives the software
stability, it's second dimension.

OfficeClerk is tested with **rspec** and mostly though the user interface (see previous paragraph). Controller and model
tests do exist, but are usually created as a simpler way to test the user experience. Ie as an extraction from the feature
tests.

Since OfficeClerk is an extension we need an application to actually run it. This is the **test_app** folder, but the 
specs including helpers and the usual directory structure is still in **spec/**. Spec files are named according to what 
they test. When they grow over 10ish tests, a directory with the previous filename (minus _spec) is created and the 
new files are named according to the aspect they test (folder name not repeated)

There is also a **Guardfile**, start with bundle exec guard. If you install the **spring** gem and the rspec command for it
it will be used. Together they give a turnaround time of
seconds, so that often when a test is edited and saved, it has already run by the time the terminal is active.

#### Bugs

Since OfficeClerk is in daily use without problems and has 300+ test it is quite stable. But with new users, new uses
come new bugs. It is essential to **write a failing test first** , before commencing to debug. The test should off
course turn when the bug is fixed. It is **good practise** to improve other tests while at.


#### Features

Off course any maintained software gets changed or added to. This **must** be accompanied by **more tests**. 

#### Extensions

Extensions are also engines, so their testing involves much the same principles. They also need a test_app (easy to copy
an existing) to test their interface. For parts that are being added normal practices apply. 

If parts of OfficeClerk are being overriden, new tests will have to be added for exising functionality, redefining what 
it should do. To that effect the OfficeClerk helpers may be used. Even the factories are exported in the engine, so they 
are available in extensions too.


[**<- Prev** Extensions](06_extensions.html)    [**Next ->** Installation](08_installation.html)


