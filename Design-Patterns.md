# best-practices
## Singleton
####Pros:
To be added later
####Cons:
1. They are generally used as a global instance, why is that so bad? Because you hide the 
dependencies of your application in your code, instead of exposing them through the interfaces. 
Making something global to avoid passing it around is a code smell.

2. They violate the single responsibility principle (SRP): by virtue of the fact that they control 
their own creation and lifecycle.

3. They inherently cause code to be tightly coupled. It makes faking them out under test rather 
difficult in many cases.

4. They carry state around for the lifetime of the application. Another hit to testing since you 
can end up with a situation where tests need to be ordered which is a big no no for unit tests. 
Why? Because each unit test should be independent of the other.

#### Do's
To be added later
#### Don't's
1. If your Singleton carries a significant global state, don’t use Singleton. This includes 
persistent storage such as Databases, Files etc. Note that log files are an exception to that. 
In most cases their state isn’t significant for the behaviour of the Application. Good examples 
for the usage of Singletons are PrintSpoolers (fire and forget)

2. There aren't many examples. A log file is the big one. You don't want to just abandon a single 
log file. You want to flush, sync and close it properly. This is an example of a single shared 
resource that has to be managed.
It's rare that you need a singleton. The reason they're bad is that they feel like a global, and 
they're a fully paid up member of the GoF Design Patterns book.
When you think you need a global, you're probably making a terrible design mistake.
   
