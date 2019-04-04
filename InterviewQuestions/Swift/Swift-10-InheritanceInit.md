1. Define a 'Person' base class, which has two properties: name and age. It should have a 'greet()' function also, which returns: "Hi". 'Person' should have an init, which fills all properties based on the input parameters.
1. Define an 'Employee' class, which should be a 'Person'. The 'Employee' should be at least 18 years old. Please ensure this in the initializer.
1. Create a 'Boss' class, which should be an 'Employee'. Boss should have an 'employees' array and an 'employ' function, which adds the Employee what it got as input param to the employees array.
1. Enhance the 'Employee' with a boss property, where it stores it's direct Boss. This property should be set at the moment of emloyment.
1. Create objects, which are representing a company structure of three levels: CEO, Line Managers, Employees and assigne them properly to each other.
1. Modify the 'greet()' function on the Employee to extend Person's greet with " Colleague!". 'Employee' should disable the possibility to modify its greet method to its subclasses.
1. Enhance the 'Boss' to be able to reach its employees using the follwing syntax: `boss[0]`.
1. Add an 'isLiar' property to the Employee. If 'isLiar' is set to true, the 'age' should be decreased with 3 years.
1. Add an 'isAdult' property to the 'Person', which should be set to true if age is higher than 18.
1. Add an 'isWorking' variable to the 'Person', which should return with false, but in case of 'Employee' should return with true.
1. Create an initializer for 'Boss' with an additional optional parameter: 'employees'. It should fail if the 'employees' array is empty.
1. Also create an convenience initializer for the same, but with different parameter names.
1. Enhance the 'Employee' to print out that he left the company if no one employs him (this practically means, that no one has reference to him). For example: "Jim left the company"
1. Create an enumeration, called 'ABC', which can have 3 possible values: 'A', 'B' and 'C'. 'ABC' should have an initializer which accepts A, B and C characters to initialize itself with the proper value, otherwise it should fail.
  
1. Fill out the missing spaces.
     ```swift
     class Animal {
         var voice: _____________________
     
         required init(speak: ______________________) {
             self.voice = speak
         }
     
         func speak() {
             self.voice()
         }
     }
     
     class Dog: Animal {
         static func bark() {
             print("vauuu")
         }
     
     }
     
     let barking = Dog.bark
     let dog = Dog(speak: barking)
     dog.speak()
     ```
1. Create a minimal designated initalizer for the 'Movie'.
      ```swift
      class Movie {
          let title: String
          let year: Int?
          let description = "Empty"
      
      }
      ```
1. Create a convenience initializer for the 'Movie', which initializes all properties. This initializer should be able to create an object with the same values as the previous one.
1. Create the only the necessary initializers for 'A' and 'B'.
     ```swift
     class A {
         var a: Int
     
     }
     struct B {
         var b: Int
     
     }
     ```
1. What is printed out?
    ```swift
    class Person {
        var name: String
        init(name: String) {
            self.name = name
        }
    }

    class Employee: Person {
        var boss: NewBoss?
    }

    class NewBoss: Employee {
        var employees = [Employee]()

        override init(name: String) {
            super.init(name: "Mr " + name)
        }

        init(name1: String) {
            super.init(name: name1)
        }

        convenience init(name2: String) {
            self.init(name: name2)
        }
    }

    print(NewBoss(name1: "John").name)
    print(NewBoss(name2: "Jim").name)
    ```