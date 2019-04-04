# Design Patterns and Principles

- [Design Patterns and Principles](#design-patterns-and-principles)
- [Basic Definitions](#basic-definitions)
- [GoF Design patterns](#gof-design-patterns)
  - [Creational patterns](#creational-patterns)
  - [Structural Patterns](#structural-patterns)
  - [Behavioral Patterns](#behavioral-patterns)
- [Other design patterns](#other-design-patterns)
  
   

  
This article is a cheat sheet of the most used design patterns and principles. This was not made to teach you. This was made to make you remember what you already understood.
Other sources to learn and understand more:  
- THE GoF book: _Design Patterns - elements of reusable object-oriented software_  
- [design patterns at sourcemaking.com](https://sourcemaking.com/design_patterns)
- [wikipedia](https://en.wikipedia.org/wiki/Software_design_pattern)
  
> Note: It is very important not to try to use a given pattern as it is. Perhaps you just want to use the wrong pattern. Always adapt them to the requirements to solve a given task. It is very frequent that more patterns are used together to achieve the goal.  

> There are patterns which are similar to other patterns. The intention why to choose one, how to use one, what to solve with one makes the difference.

# Basic Definitions
Several design patterns based on the following key concepts:

<details><summary>Interface: a structure of a type</summary>
  
 (usually a class) without a specific implementation. It is a **contract** between two objects. Interfaces usually are declared by objects to 'delegate' some functionality (see `Inversion of control` for more detail). Specifies what methods an object can have - but does not specify the behaviour. Different classes implements the interface providing different behaviours.
</details>

<details><summary>Wrapper: holds reference to an other object.</summary>
 Sometimes it means the owner manages the lifetime of that object as well, sometimes just a simple reference to use it. To make it flexible this reference should be kept using an `interface` instead. 
</details>

<details><summary>Delegation: move/use functionality of another class.</summary>
    
The purpose can be to ask for some data or to perform an action (transport the data). Apply it using the `wrapper`.
</details>

<details><summary>Factory: a method/class which creates objects</summary>

Factory is a method (or a class with more methods) which has the only task to manage the creation of other classes. Factory usually provides objects through interface.
See `Factory method` and/or `Abstract factory` for more details.

</details>

---

# GoF Design patterns
GoF is the abbreviation of _**Gang of Four**_ - after the four authors of one of the most fundamental design patterns book.
There are three different kinds of pattern based on their tasks:
* Creational patterns: how objects can be created/accessed
* Structural patterns: how objects can be bind together
* Behavioral patterns: how objects works, works together to achieve specific tasks

## Creational patterns

<details><summary>Abstract Factory: creates and returns with related classes</summary>  

_"Provide an interface for creating families of related or dependent objects without specifying their concrete classes."_  

_Client_ uses a _factory_ (referencing Abstract Factory, through interface or abstract class) to create instances of different classes belonging together.    


Define an interface/class which declares the methods used by the _client_ and add different implementation of it by overriding the creational methods. This way the client can build products with the same structure using the factory by calling the appropriate method (_Delegation_)  

Abstract Factory is often implemented using _Template Methods_ or _Prototype_.  

For example: HouseFactory: createWall, createDoor, createWindow ...   Different implementations of HouseFactory create different parts of a house, but one instance creates the same "style" of house.  

</details>


<details><summary>Builder: creates a _product_ in several steps; _director_ directs _builder_, what part to add to the product and when. Finally _director_ asks _buidler_ to create the final _product_.
</summary>  

"Separate the construction of a complex object from its representation so that the same construction process can create different representations."
`Director` class sets up a complex object by calling elementary methods defined in the `Builder` interface/class. Each builder subclass implements the operations in its own way so Director won't know what parts makes up the object and how are they assembled.
Finally `Director` asks `builder` to create a 'product'.  


Similar to `Abstract factory`, but the purpose is different. While the `client` in abstract factory gets a new object for each call, the `Builder` doesn't give out the object. The `Director` (client) directs the Builder what to do.  


Can be used with abstract factory - inside the builder.
For example: HouseBuilder: addWall, addWindow, addDoor, create/get House
</details>

<details><summary>Factory method: create an instance of some class conforming to a given interface or base class; subclasses can return with different instances</summary>  

_"Define an interface for creating an object, but let subclasses decide which class to instantiate"_  
  
Put a dedicated method to a class (_Creator_) which creates the Product. Creator also can contain other methods which is used with Product. The subclass of Creator will implement the method and create the specific Product instance.
</details>

<details><summary>Prototype: create new instances by copying an existing one</summary>  

Create new instances of a class using an existing one by cloning/copying it. Very useful, when the creation of new instances needs in runtime while the classes are referenced by an interface/base-class.
</details>

<details><summary>Singleton: allow only one instance from a class</summary>  

_"Ensure a class only has one instance, and provide a global point of access to it"_  

Instance of a class can be accessed through only one dedicated 'static/class' method. Keep the only instance inside the class scope privately. The allocation/creation of the class instance have to be prohibited to other classes.  

    > Note: Be careful and do not overuse this pattern. Very easily can became an anti-pattern. I would say in 99% of the cases you don't need it. For more information why, see [here](http://andras.palfi.hu/singleton-the-anti-pattern).  

</details>

## Structural Patterns

<details><summary>Adapter: make classes compatible with another class, interface</summary>  

Implement an interface for a class to make it compatible with another class which wants to use the first class.  
  
Two kinds:  
- **Class adapter**: use multiple inheritance/interface implementation to implement the new interface while subclassing the original class.  
- **Object adapter**: create a new class implementing the desired interface and encapsulate (`wrapper`) the original class holding reference to it in a member. In the interface-methods call the methods of the encapsulated class (see: `proxy`).

</details>    

<details><summary>Bridge: implement complex things for multiple platform delegating base operations</summary>  

_"Decouple an abstraction from its implementation so that the two can vary independently"_  

Useful when the same functionality for problems has to be implemented to more platforms. For the two platforms two implementation needed but the real differences are only at low level.  
For example build houses, where the structure always the same, but perhaps you use different bricks. So you have a house builder which has an internal wall builder which puts together the bricks. If everything hard coded you implement two house builders but the majority of the code is duplications. To get rid of code duplications the easiest way is to replace only the bricks which are used to build the house.  
The same is drawing shapes on different systems. It is enough to define some basic operations (draw line, draw curve) and then implement the draw shape methods (rect, triangle, circle, more complex stuff) using these basic operations.

In short: delegate the basic operations, then implement what you need using abstract references to that basic operations. 
</details>

<details><summary>Composite: build a hierarchy</summary>  

Compose objects to hierarchies by using a base class/interface which contains the very basic mandatory operations to manage the hierarchy and perform basic operations.
  
Declare node classes and leaf classes. Calling a basic operation on a node will forward the same call to all its children. Hierarchy management operations will work only on node items.
</details>

<details><summary>Decorator: attach additional functionality/feature to an existing component on the same API by wrapping it into a new compatible class</summary>

It helps to add functionality dymaically and you can vary the features independently!

For compatibility reason the classes need a base class/interface.  
*Decorator* keeps a reference to the 
All operations called on the decorator will be forwarded to the wrapped class but performing additional operations before and/or after the forwarded call.

</details>

<details><summary>Facade: publish a simpler API above a system to hide underneath API</summary>

To hide, simplify or control a complex class hierarchy create and publish a new interface/class. Delegate all operation to the appropriate subsystem classes.
Users of the facade don’t know about the classes in the subsystem and subsystem classes don’t know about the facade or the user classes.  
It is also easier to change the underlying classes.

</details>

<details><summary>Flyweight: share expensive objects among class instances</summary>  
  
Share the expensive objects (*flyweights*) among instances if there are numerous elements in a system which use the same components.  
Do not store object specific states in the *flyweights* but pass the actual state to them on use.

- *Client* can store the states and pass them to *flyweights* when needed.  
- An other aspect that the *client* only references light flwyweight objects which stores the state and calls the real flyweights (expensive objects stored by *flyweight pool*) and the real flywights are invisible for *client*. 
  
Can be very useful for example to image caches. It is possible to remove unnecessary images from memory and load them on demand even if the 'image flyweight' object is referenced by the system since that only references a container (*flyweight pool*) which stores the real image.

</details>

<details><summary>Proxy: a compatible wrapper to control the access to the original object</summary>

Wrap the original object into the proxy and forward every call to it. Proxy has the same API as the original object, so it is 'invisible'.

Subcases:  
- **remote proxy**: provides a local representation of a remote object in a different address space like network, database etc.
- **virtual proxy**: create the wrapped object on demand – lazy binding. 
- **protection proxy**: filter the access to an object
- **smart proxy**: the proxy performs some additional functionality; useful for reference counting and lifetime management (smart pointer); thread locking etc

</details>

## Behavioral Patterns

<details><summary>Chain of Responsibility: Chain the receiving objects and pass the request along the chain until one handles it</summary>  
  
Base on the original pattern description the objects are composed to a chain. When an item is called it handles the message or it calls the base class implementation, which by default calls the next item in the chain. For that all items in the chain must be a subclass of a specific base class. 

Can be implemented however otherwise where the object in teh chain just returns whether the message was handled or not and the caller (parent object) knows who to call next. Can be used with iterator.

</details>

<details><summary>Command: encapsulate _requests_ as objects instead of method call on an object with specific parameters</summary> 
  
Encapsulate a request as an object: the _command_ should encapsulate the _receiver_ and the _parameters_. _Client_ just calls the _execute_ method. It is possible to queue or log requests, command can encapsulate its _reverse_ operation to support _undo_.

Another variation when only the parameters are stored in a _command_ object and using _chain of responsibility_ we let someone to handle it. Operating systems' user interfaces work this way.
</details>

<details><summary>Interpreter: define a language with its interpreter (processor)</summary>  

Define a language representation for its grammar along with an interpreter that uses the representation to interpret sentences in the language.  
The _language_ can be letters, numbers or even color codes. 

Interpreter always pass the state to the next interpreter. Usually implemented with _Composite_.

</details>

<details><summary>Iterator: provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation </summary>  
   
Given aggregate objects (_array, dictionary, lists, trees etc_) and walk though each item one by one without knowing the internal structure. It is also possible to walk through items from one to the last or reversed order or using any specific rule (items conforming to a rule).

Define an interface with _next()_ method.   
Let's create a new _iterator_ classes for each storage (and rule) which knows the internal structure of the collection and has access to its items. 

_Clients_ can instantiate the proper _iterator_ and call _next()_ accessign all the elements (conforming to a rule, accessing them in the proper order) until the end of the items (_next()_ returns null, or dedicated _finished()_ returns true)
 
</details>

<details>
<summary>Mediator: define a supervisor object which knows who to call and when</summary>

Define an object that encapsulates how a set of objects interact. Mediator promotes loose coupling by keeping objects from referring to each other explicitly, and it lets you vary their interactions independently. The underlying objects don’t hold reference to each other but a reference to the mediator object (through an interface or abstract class). The mediator has reference to the more important underlying objects.  
Even if underlying objects call each other or a client makes a call mediator direct the call to the proper underlying object.
Similar to _Facade_ but the intention is different as it simplifies the API and facade handles only requests from clients.

</details>

<details><summary>Memento: serialization, capture an object state, store and restore te object later</summary>

_Caretaker_ an object knowing when to use (save/restore) _originator_. It can be a client directly. Calls a dedicated method on _originator_ to create a memento (persisted state object) and another method to set the back the stateof the object to the data captured in memento

</details>

<details>
<summary>Observer: pusblish-subscribe; more objects listen on changes of a subject object</summary>

Define a one-to-many dependency between objects. The observers listen to the changes of subject (observed object) so that when the subject changes its state, all its observers are notified.
Usually the subject sends out specific messages which the observers catch/handle.

</details>

<details><summary>State: instead of conditions everywhere in the code use separated objects with the same API but different behavior according to state.
</summary>  
  
Use, when the state of an object changes at runtime and it is hard to use conditions everywhere in the code.  
The _client_ holds reference to the _context_ class which is technically a proxy providing the same API as all the _state_ objects used internally in _context_. The context class holds reference to a specific state object and forward every call to it. If the state should change the context class will reference another _state_ class. 

</details>

<details>
<summary>Strategy: replace functionality referenced by an interface/base class</summary>

Use when it is necessary to be able to easily replace some functionality.
Client can be configured with any concrete 'strategy' implementations as it references a strategy with an interface.
_Delegation_: client delegates the functionality to a strategy

</details>


<details><summary>Template method: define abstract/virtual methods what subclasses must implement</summary>

Different subclasses can implement the _template method_ differently. 

Prefer _strategy_ and delegation instead.

</details>

<details><summary>Visitor: perform tasks for instances of different types of classes in a composite structure without type casting using method overload</summary>  
  
Given a _composite_ strcture containing different, related types of classes. Without extending the classes let to perform different tasks.
- The original classes declares a special method - _accept_(_visitor_) where _visitor_ is an interface/base class with methods: _visit_(_type_) where the _visit_ method overloaded with **all** the types in the composite. 
- _accept_ only calls the appropriate _visit_() method selected by the compiler based on type
- create different visitors performing different tasks with the items
- apply/perform a given visitor instance passing it to composite. It calls all the items' _accept_ method which just calls the appropriate _visit_ method on it.

</details>

---  


# Other design patterns

<details><summary>Object Pool: limit the number of objects</summary>

There are situations when the number of objects must be limited. Use a dedicated object which controls the instances available of (another) object. Can be a separate object store but can be implemented on the class itself as static method.  
`YourClass.getFreeObject()` can return null or can block the call waiting for the next available instance.   
The user of an object must _release_ the instance when finished.

Object pool can also behave in a way that always creates a new instance but it is also possible to push an unused object into it so next time it returns with the existing object instead of creates a new one.

Independent object store can store different types of objects. Passing the type (or using generics) the proper type of instance can be retrieved.

As en example think of _thread pools_ or _network request pools_
</details>

<details><summary>Multitone: more instance of a type referenced by key</summary>

Similar to _singleton_, multitone however supports more instances. The access of the objects are bound to a _key_.   
Different instances of course have different states. Based on implementation it can have different behavior etc.

</details>

<details><summary>Private class data, pImpl (pointer to implementation: hide data/code in a membber, the type of member is hidden/unkown - only private implementation sees</summary>

This design patterns used mostly in languages where the structure of private members are visible (c++, Objective-C etc)  
In this languages a "forward declaration", an empy name declaration is enough to represent the storage of a data or functional object in a member. It can be a non-typed representation as well (void*);

The implementation internally can use the _pImpl_ instance or even just forward the calls to it. 

</details>

<details><summary>Null object: provide a simplistic, empty, default implementation for an interface/abstract class</summary>

When an object must reference something but it can be "empty" instead of using Null/Nil as referene and alwasy check the existance, provide a very primitive, empty implementation as a placeholder.

</details>