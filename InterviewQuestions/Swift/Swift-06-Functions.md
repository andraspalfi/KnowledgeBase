1. Create a 'greet' function, which has two input params: 'greeting' and 'name'. The function should print out the two strings concatenated. If you call the 'greet' without param, it should use the default values and print out: 'Hi John'



1. Improve the 'greet' function to return with a tuple, which contains the concatenated string and the number of the characters in the string.



1. How would you print out the return value of function with the following signature? Write an example call.

    ```swift
    func anotherGreet(name: String, with greeting: String) -> String
    ```

1. How would you change the 'greet' function to be called without named parameters.



1. Create a 'massGreet' function, which can greet any number of persons with "Hello ****!". Each greeting should be printed out in one line comma separated. Implement it at least using two different ways.



1. Create a function which reverses the input string. The function should not have a return value.

1. Create a variable, which is a function type. The function should have an Int input param and a String return value.

1. What will the following code print out?
    ```swift
    func func1(_ num: Int) -> Int {
        return num - 1
    }

    func func2(_ num: Int) -> Int {
        return num + 1
    }

    func func3(_ num: Int) -> Int {
        return num * 2
    }

    print("First: \(func1(func2(2)))")
    print("Second: \(func1(func3(func2(2))))")

    let myVar = func3
    let myVar2 = func1

    print("Third: \(func2(myVar(2)))")
    print("Fourth: \(myVar(myVar2(2)))")
    ```


1. What is the type of 'myVar'?

1. Create a 'callAll' function which has two input params: an array of integers and a function type. 'callAll' should call the input function with all elements of the input array.

1. Create a function, which has an integer input parameter, and the function should just print the number out. Call the 'callAll' function with this function and an array of integers.

1. Create a 'sumOfCalls' function, which has an integer input parameter. The function should print out the sum of the input parameters, with the function were called during the program run. 

    so sumOfCalls(2) should print out 2
    
    and sumOfCalls(1) should print out 3, as the func were called with 2 previously and 2+1=3
    
    Call the 'callAll' function with 'sumOfCalls' function and an array of integers.
    
1. Create an 'increase' function, which has an integer input parameter. If you call it with 'num' as the  parameter (```var num = 0```), 'increase' should increase the value by one during the call.

1. Create a 'counter' function and call it with the 'func2' and an integer as input parameters. The 'counter' should return with the value, what it gets if it calls the input function with the input integer.



1. Create an example for a nested function.
