
# Basic operators
[reference](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)

1. Given the following code:
    ```swift
    let three = 3
    var value1 = -three
    ```
    - What is the value and the type of `value1`
    - What is the value of `value1` after the following:
        ```swift
        value1 -= three
        ```
    - What is the value of `value1` after the code:
        ```swift
        value1 -= -value1
        ```
1. What's the output:
    ```swift
    if (3, "apple") < (3, "bird") {
        print("big bird")
    } else {
        print("small bird")
    }
    ```

1. What's the type and value of `winner`:
    ```swift
    let a = (1, "zebra")
    let b = (2, "apple")
    let winner = a < b ? b : a
    ```

1. What is the value and the type of `value2`?
    ```swift
    let value1 = -6
    let three = 3
    let value2 = 5 < 4 ? 5 : (three > 6 ? 8 : (value1 == -6) ? 7 : 8)
    ```

1. Given the following code:
    ```swift
    let someValue: Int?
    let num: Int
    if someValue == nil {
        num = 1
    }
    else {
        num = someValue!
    }
    ```
    - How can you change it for a shorter/swiftish form?
    - What is the shortest expression

1. What's the value and type of `num`
    ```swift
    let some: Int?
    let num = some ?? 1
    ```

1. What's the output?
    ```swift
    var numberOfStudents: Int?
    var numberOfTeachers: Int?
    numberOfTeachers = numberOfStudents == nil ? 1 : numberOfStudents
    numberOfStudents = (numberOfTeachers != nil ? (numberOfTeachers ?? 0) : 0) * 20
    print("\(numberOfTeachers! + numberOfStudents!)")
    ```

1.  What is the output?
    ```swift
    var sum = 0
    for index in 0...49 {
        sum += 1
    }
    print(sum)
    ```

1. What is output?
    ```swift
    var sum = 10
    var numberOfRuns = 0
    for i in 0..<sum {
        sum -= 1
        numberOfRuns += 1
    }
    print(numberOfRuns)
    print(sum)
    ```

1. What is the value of sum and numberOfRuns?
    ```swift
    var sum = 10
    var numberOfRuns = 0
    while numberOfRuns < sum {
        sum -= 1
        numberOfRuns += 1
    }
    print(numberOfRuns)
    print(sum)
    ```

1. What is printed out?
    ```swift
    let hasTee = true
    let hasEggs = true
    let canCook = false
    let hasBread = false
    if canCook && hasEggs && hasBread {
        print("Breakfast")
    } else if hasTee && hasBread || canCook {
        print("Drink a tee")
    } else if hasBread && !canCook || hasEggs {
        print("Go to a restaurant")
    } else {
        print("None of these")
    }
    ```

-----
