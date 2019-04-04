
# Basics

[reference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)


1. What are the values and the types of value1 and value2 variables?
    ```swift
    let num1 = 3
    let num2 = 0.14
    let value1 = num1 + Int(num2)
    let value2 = Double(num1) + num2
    ```

1. What is the value and the type of value3?
    ```swift
    typealias MyType = Int
    let value3 = MyType(3.14)
    ```

1. Given the following declaration:
    ```swift
        let cars = ("VW", "Golf")
    ```
    - How can you print out *Golf*?
    - How can you change the declaration to access the *Golf* value with a name?

1. Write down how you can call the processError function with the errorCode:
    ```swift
    func someFunc(_ errorCode: Int?) {
        // TODO: call process error
    }
    func processError(_ code: Int) {
        print("Error happened: \(code)")
    }
    ```

1. write a code, which calls myFunction and prints out "Sorry" if somethingBadHappened
    ```swift
    func someFunc() throws -> Bool {
        // can throw any error
    }

    enum MyError: Error {
        case somethingBadHappened
    }

    func myFunction() throws {
        let result = try someFunc()
        if !result {
            throw MyError.somethingBadHappened
        }
    }
    ```
-----
