# Closures

[reference](https://docs.swift.org/swift-book/LanguageGuide/Closures.html)

1. What is a closure?
1. What's the difference between a nested function and a closure declared in a function and saved in the same function to a local variable?
1. What's the difference among: function, method, closure and how and when the 'instance' is handled?
1. What's the difference between @escaping and non-escaping closures?
1. What is 'capturing' and how can you use it?
1. How capturing works? What is the consequences of that?
1. When do you have to use `self.` in a closure when you refer to an instance property
1. Show a sample snippet for a trailing closure syntax
1. Given an array of strings. Sort it using the `sorted` function of the array passing by setting up the order based on the last character of the string. Write the three different form of closure implementation, from longer to the shortest version
1. (Task A) You can use Xcode: declare local optional variables (the initial value of the variables must be nil) for a closure type which can take an Int and a String parameter...
    1. ... and returns ***synchronously*** with a String.
    1. ... and calls back ***asynchronously*** with a String. The method must provide the result ***asynchronously***. To make sure it is asynchronously calls back use the 'DispatchQueue.global().asyncAfter(deadline: DispatchTime.now() + 1' with the trailing closure syntax inside the method
1. Based on the previous declaration assign an implementation for both properties. The implementation should generate a String from the two parameters by concatenating so the result looks like: 'original string: value of int'
1. (Task B) Based on the previous implementations create two new closure variables which takes a parameter String, Int and the type of closure of the previous declarations. The implementation should call the closure in the parameter, with the String and Int and returns with a String: the result of the methods. So it looks like: 'The result of the closure was: <write the result here>'.
    1. print out the result of calling the new closure with the ***synchronous*** closure implementation (use the variable) and the String 'synchronous' and Int 1
    1. print out the result of calling the new closure with the ***asynchronous*** closure implementation (use the variable) and the String 'asynch' and Int 2. Your implementation should call the other closure ***asynchronous*** (Dispatch) and must provide the result ***asynchronously***
1. Call the methods in 'Task B' with trailing closure (instead of passing the closures implemented in 'Task A'). Use named parameters. So implement what you have in the closures in 'Task A' directly with trailing closure
1. The same as the previous task, but now use the shortest one-liner form of implementation (you can ignore the dispatch call for the asynchronous method)
1. Create a method which returns with helper 'functions': based on the Int parameter (A) it returns with a closure. The closure is asynchronous, takes an Int as a parameter and results in
    1. incremented value of the input if A was positive
    1. decremented value of the input if A was negative
    1. negates value of input if A was 0
The returned closures must be one liners and cannot contain conditional calls!
1. Create a function which can be called the following way `cap(ar: [10,11,12,13]) { print($0) }` and produces the result: 10, 11, 12, 13
1. Modify the ***call*** so it calculates the *sum* of the values
1. Create a small class. It has two methods:
    1. `subscribe` which takes a closure as a parameter. The closure is asynchronous, has an Int parameter, and a completion handler (Void).
    1. `send(Int)` calls all the *subscribers* with the parameter. Note: subscribers are ***asynchronous***!
1. modify the previous class. The subscribe must take an "id: String" parameter and the closure must be optional. When that id is already subscribed the existing one should be replaced with the new one. If the closure is nil the subscription must be removed. Otherwise everything should be work the same way: all subscription must be called ***asynchronously***
1. Given the following code. Implement the method `positive` where the `numberOfPositives` results in 1
    ```swift
        var numberOfPositives = 0
        [10,0,-1].forEach { positive($0, numberOfPositives += 1) }
    ```
1. Declare local optional variables for a closure type which can take an URL as parameter...
   1. ... and returns ***synchronously*** either with a String or an Error.
   2. ... and calls back ***asynchronously*** either with a String or an Error. The method must provide the result ***asynchronously***. To make sure it is asynchronously calls back use the 'DispatchQueue.global().asyncAfter(deadline: DispatchTime.now() + 1' with the trailing closure syntax inside the method
1. Create a function which can be called the following way `process(names: ["milk", "butter", "bread"]) { print($0) }` and produces the result: 
   ```swift 
   Shopping list:
   - milk
   - butter
   - bread
   ```

1. Given the following code. Implement the method `isCapital` where the `numberOfCapitals` counts the strings, which starts with uppercase.

   ```
    var numberOfCapitals = 0
    ["butter", "John", "milk", "Jim"].forEach { isCapital($0, { numberOfCapitals += 1 }) }
   ```
