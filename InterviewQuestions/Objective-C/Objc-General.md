# General Objective-C 

<details> <summary>What tools/environemnt do you need to be able to develop for iOS</summary>  

 MAC OS X, XCode, Developer Profile ...

</details>

<details>
<summary>Define basic OOP concepts and the keywords in ObjC used with classes</summary>  

@interface, @implementation, @property, @protocol, 

</details>

<details>
<summary>Application lifecycle; What kind of states an application can have? Which general methods are called </summary>  

States: 
* not running
* inactive
* active
* background
* suspended
  
Transitions can be handled using method on AppDelegate or notifications:
* `application:willFinishLaunchingWithOptions:`
* `application:didFinishLaunchingWithOptions>:`
* `applicationDidBecomeActive:`
* `applicationWillResignActive:`
* `applicationDidEnterBackground:`
* `applicationWillEnterForeground:`
* `applicationWillTerminate:`
* `applicationDidFinishLaunching:`
</details>

<details><summary>What is an iVar?</summary>  

Instance variable, data memeber of a class instance

</details>

<details><summary>method visibility</summary>  

 private/public - no protected. anyone can call a private
 
 </details>

 <details><summary>what are + and - methods?</summary>  
   
class vs instance methods
 
 </details>

 <details><summary>What about multiple class inheritance</summary>  
   
   not supported, only single inheritance

 </details>

<details><summary>What is a property? How can you declare one? What is the benefits to use properties?</summary>  

 `@property (atomic|nonatomic, assign|strong|weak|copy, readonly|readwrite, getter=,setter=) type name;`  
 
  getter/setter method, also sends KVO notifications. Hides the iVars (safety and flexibility)

</details>

<details><summary>What property attributes do you know?</summary>

* nonatomic/atomic
* assign (unsafe_unretained)/string (retain)/weak/copy/
* readonly/readwrite
* getter=, setter=

</details>

<details><summary>What's de difference between strong, weak, assign?</summary>

* strong: retains
* weak: doesn't retain, become nil if the original object released so treated as safe
* assign: doesn't retain, become **invalid** pointer if the original object released: can lead to crash! use for scalar types only

</details>

<details><summary>How can you implement a property</summary>  

* In general you don't need for classes as peroperties are autosythesized 
* `@synthesize name < = iVar name` can be used to bind the property to an iVar  
* `@synthesize` **must be** used if the property declared in a **protocol**  
* implement getter/setter methods:
  
    ```
    - (void) set<Propertyname>:(type)paramName { _iVarName = paramName }
    - (type) propertyName { return _ivarName; } 
    ```
</details>

<details><summary>What is a protocol? How can you declare one?</summary>

```
@protocol ProtocolName
// list of methods and properties
@end
```
</details>

<details><summary>Is it mandatory to implement all the methods/properties from a protocol? (what about optional and required?)</summary>

Declaring a section in a protocol @optional the methods/properties below are not mandatory to implement
By default everything is @required so they must be implemented

</details>

<details><summary>How to check an optional protocol method existence on an object?</summary>  
  
`[instance respondsToSelector:@selector(method/propertyname)]`

</details>

<details><summary>How to add a method to a class (extend) without the source of the class and without recompiling the class</summary>

With _categories_; allows to extend any class with methods, properties, but stored properties  and synthesize wont work. Can be implemented with getter/setters though

</details>

<details><summary>Difference between extensions () and (named) categories</summary>

* named categories are the normal categories, can be implemented anywhere
* extension category allows to declare private properties and adds compile time method existance checks. can be implemented only in the same implementation file as the original class

</details>

<details><summary>Can you re-declare a property in subclass or extension?</summary>   
  
YES. If you declare a property in one class as readonly, you can redeclare it as readwrite in a class extension, in a protocol, or in a subclass.

</details>

<details><summary>Limitations of- and problems with categories?</summary>

Cannot override an existing method and call it in the extension method.
Cannot introduce new stored properties, iVars
</details>

<details><summary>What are formal and informal protocols
</summary>

Formal are the real protocols, informal are categories on NSObject (with optional methods)

</details>

<details><summary>How to declare protected-like methods (accessible only for some dedicated classes)?</summary>

 Separate header file with (named) category, and include it in other class 

</details>

<details><summary>What is a designated and convenience initializer? What is the calling rule related to that</summary>

Designated initializer is the mandatory initializer which must be called when creating an instance. 
There must be always at least one designated initializer but there can be more.
Convenience initializers are initializers with less/other parameters to ease the creation of an instance. 
Convenience initializer must call a designated initializer on the same class level.
Designed initializer must call the super class's designated initializer.

</details>

<details><summary>What is the code pattern for the implementation of initializers and why?</summary>
 
 super init must be called to make sure everything is initialized properly. Additionally super init can fail which mus tbe handled properly.
 An init can reuturn with nil if fails for some reason

 ```objc 
 - (id) init {
        if ((self = [super init]) != nil) { 
         ... 
        }
    }
 ```
</details>

<details><summary>What technics do you know to implement when one object informas another one (or more) that something happened or information needed. What are the differences?</summary>

- delegate: keep a reference to an object with a known API (class, protocol) better if there is a need to call more methods
- target-action: save a reference to the object (_target_), the _action_ is _selector_ which also saved. frequently used by UI controls; can be used only with one object and one method (but method name is not restricted)
- block: reference a block and call that. can be any object and method, can be just a block inside another method.
- notification: can call more _listeners_. Use when binding between object is not possible for some reason

</details>

<details><summary>What is a delegate and what is the ownership rule around that and why? Do you know any exception?</summary>

Delegate is a protocl implementation used to inform an object about something and/or get information from an object. Use when more methods needed (otherwise use block)  
  

Ownership rule: never _retain_ to avoid circular reference problem where one object keeps reference to another and the other keeps reference to the same object. They keep themselves alive while there is no outer reference to them - memory leak!

Exception: NSULRSession references its delegate (the same with NSURLConnection)
</details>

<details><summary>What is a block?</summary>
TBD
</details>

<details><summary>What problems can come along using blocks?</summary>   

Capturing: on caller side it is easy to accidentally capture object, like self which can lead to cilcular reference problem.
Only one ‘method’ can be called – delegate can have more methods. 
Recursive calls implementation is also problematic. Fopr example on fail restart the method which expects the same block. 
Solution to recursive calls: put the closure to a __block local variable, so it can call/reference itself  
</details>

<details><summary>What is a selector? How to call a selector reference?</summary>
TBD
</details>

<details><summary>What is the difference between the dot notation and using the square brackets</summary>

No difference at low-level as dot notation compiled to getted/setter method calls. But keep dot notation to properties.

</details>

