# SOLID Principles

SOLID is a set of object oriented programming principles aimed at making software more understandable, more tested, and make it user to maintained.

- S: Single Responsibility - Each class should have on role, a single purpose
	- Ex a class that is a book might not also want to print or order more books
- O: (Open/Close Principle) - Class, modules, function should be open to extension but closed to modification
	- Ex create base class and allowing other class to extend it to modify content
- L: Liskov's Substituation Principle
	- Any derived or child class must be substituted for their base or parent class
	 - Any new behavior in the child must not affect its parent
 - I: Interface Segregation Principle
	 - Do not force any client implementation which is irrelevant to them
	 - Prefer many small interfaces to one big one
 - D: Dependency Inversion Principles
	 - High-level module should not depend on low level modules. Both should depend on abstractions
	 - Should not have to know how it implemented.  Just how to use it