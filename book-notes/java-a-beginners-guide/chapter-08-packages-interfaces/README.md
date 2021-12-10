# Chapter 8. Packages & Interfaces

Packages are groups of related classes and using them help to organize code and provide another layer of encapsulation.

Interfaces define a set of methods that must be implemented by a class that implements it. In this way an interface specifies 
what a class will do (the contract), but not how it should do it. 

## Packages
Packages serve two purposes:
1. organization
2. access control

Packages utilise Java's access control features so classes defined within a package can be made private to that package 
only and cannot be accessed outside, to do this do not apply an access modifier to the class member. This applies the default 
access which is public within the package but private outside.

Another access modifier that is used within packages is ***protected***. Using this, allows a member to be public within the 
package, private outside but also accessible to subclasses of it that are outside the package.

