# Structures, Classes, Properties, Methods, Subscripts

[reference](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)
[reference](https://docs.swift.org/swift-book/LanguageGuide/Properties.html)
[reference](https://docs.swift.org/swift-book/LanguageGuide/Methods.html)
[reference](https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html)

1. What's the purpose to create a class or structure
1. What's the difference between class and structure
1. Given the following code. What will be printed out?
    ```swift
       class C {
           var x: Int = 0
       }

       struct S {
           var x: Int = 0
       }

       func modClass(_ c: C) {
           var c2 = c
           c2.x += 1
       }

       func modStruct(_ s: S) {
           var s2 = s
           s2.x += 1
       }

       var c = C()
       var s = S()

       modClass(c)
       modStruct(s)

       print("C = \(c.x)")
       print("S = \(s.x)")
    ```
1. Given the following class which is `Equatable` so you can check equatibility by `==`.
    ```swift
    class Item: Equatable {
        var x: Int = 0

        static func == (lhs: Small, rhs: Small) -> Bool { return lhs.x == rhs.x }
        static func != (lhs: Small, rhs: Small) -> Bool { return lhs.x != rhs.x }
    }    
    ```

    1. Write a small class (`Tester`) which test `Item` instances. `Tester` should not use default values and don't need an `init`. The rules:
        * create a `set` method with one parameter of `Item` save the passed item
        * create a `test` method with one `Item` parameter. When I call the `test` method it should compare the parameter with the saved item.
        * If the instance is equal with another instance it should return +1.
        * If the items are not equal it should return with -1
        * If the item is the same instance it should return with 0

    1. Extend Tester with properties/functions
        * `itemInc` should return the stored item's x property +1
        * `x` should return the stored item's x property and also should be able to set it - without reallocating the stored item!
        * `item` should store the assigned item. When it changes it should print out "item change! old value: ... new value: ..." where `...` must contain the real old/new values
        * `Tester` also have to calculate how many times its `set` method was called **on any instance of `Tester`**. So when I have two Tester instances, and I called three times set on the first, and two times set on the second the result is 5!
        * When I call the `setCalled` it should return with a string 'Set was called ... times' where ... is the real value
1. Create a struct Distance. It has two properties: low and high. Both are double.
    1. define `distance` which returns the distance between low and high
    1. make functions which modifies the low and high values
    1. when one sets the distance it should modify the high value accordingly
    1. I want to check the Distance the following way: myDistance[10, 3]. This is a range starts at 10 and 3 long (Int types). It should give back an enum value:
        * `lower` when `low` is below the first value
        * `higher` when `high` is above the second value
        * `inside` when the low is higher than first value but `high` is below second value
        * otherwise it should return `somewhere`
    1. I want to call Distance with the previous enum as subscript. It should return with a new Distance according to the behavior described above. For example `lower` should return with a new Distance which `low` value is lower (-1) etc
