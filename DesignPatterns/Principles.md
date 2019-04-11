# Frequently cited software development principles - a quick overview

<details><summary>S.O.L.I.D</summary>  
  
Solid was declared by Uncle Bob (Robert C. Martin) among other principles. See the original [article](http://butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod). It is an acronym of the following principles:  

- **SRP - Single Responsibility Principle**: "A class should have only one reason to change". It should perform only one declared task. "Gather together the things that change for the same reasons. Separate those things that change for different reasons". This is the same as _separation of concerns_ from another perspective. See the original [article](https://blog.cleancoder.com/uncle-bob/2014/05/08/SingleReponsibilityPrinciple.html)
- **OCP - Open Closed Principle**: classes should be opened for extension but closed for modification. "The behaviors of all the modules in your system could be extended, without modifying them, then you could add new features to that system without modifying any old code". Comsider the _Plugin_ architecture, _delegation_, _loose coupling_ and in the last case _subclassing_ (_composition over inheritance_). See the original [article](https://blog.cleancoder.com/uncle-bob/2014/05/12/TheOpenClosedPrinciple.html)  
- **LSP - Liskov Substitution Principle**: derived classes must be substitutable for their base classes.  
- **ISP - Interface Segregation Principle**: make fine grained interfaces that are client specific. Many client/functionality specific interfaces are better than one general purpose interface. Kind of _separation of concerns_
- **DIP - Dependency Inversion Principle**: in classical systems and object would reference another object to perform some tasks. This is _tight coupling_. It is better that the object declares its own requirements (in an interface). Then other classes can implement this interface or _adapter design pattern_ can be used to attach any custom class.
   
</details>

<details><summary>STUPID code: avoid it :-)</summary>  
This acronym defines some common mistaktes using in your code.

- **S**ingleton
- **T**ight coupling
- **U**ntestability
- **P**remature Optimization
- **I**ndescriptive Naming
- **D**uplication
  
</details>
 
 <details><summary>SoC - Separation of Concerns</summary>
 
 
 </details>

</details>
  
<details><summary>IoC - Inversion of Control</summary>  


</details>

<details><summary>Service locator</summary>  
  
  
</details>

<details><summary>DI - Dependency Injection</summary>


</details>

<details><summary>KISS - Keep It Simple, Stupid / Keep It Stupid Simple</summary>

</details>

<details><summary>DRY - Don't Repeat Yourself</summary>  
  
  
</details>

<details><summary>YAGNI - You Ain't Gonna Need It</summary>  
  
</details>

<details><summary>Closure/Block/Lambda expression</summary>

Encapsulate sets of operations together with their context (used variables). Usually in the background the compiler generates a tiny class for you which members are the _captured_ variables.   
Consider the _closure_/_lambda_ as a tiny class with some members and only one method.

</details>

<details><summary>Lazy load/Late binding</summary>  
  
  
</details>

<details><summary>RAII</summary>  
  
  
</details>

<details><summary>Introspection</summary>  
  
The ability of a program to check/get information of a type in runtime so the client can make decisions and perform different operations depending on the information of the referenced class.
  
</details>

<details><summary>Reflection<summary>  

Type introspection + the ability to modify the structure and behavior of classes in runtime: create instances of types, calling methods, modifying members or even add new methods or replace method.
  
</details>

<details><summary>Composition over inheritance</summary>  
  
  
</details>