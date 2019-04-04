# Strings

[reference](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)

1. Create a new string 'hello there' using the two constants (how many solutions do you know?):
    ```swift
    let string1 = "hello"
    let string2 = " there"
    ```

1. Create a variable `finalString` which contains `You can try 10 times` using the `number` variable - how many options do you have:
    ```swift
    let number = 10
    ```

1. Give a one-liner solution: create a string using the constants '3 * 2.5 is 7.5':
    ```swift
    let multiplier = 3
    let number = 2.5
    ```

1. Given the following: `let greeting = "Hello World!"``
    1. put the first character to a variable 'first'
    2. put the character before the last character to a variable 'last'
    3. put the 4th character to a variable 'fourth'

1. write a short code which prints all the characters one by one to the console of the string 'Hello World!'

1. Given the following function snippet, print out 'starts with "text content"' if it starts with text; print 'ends with "text content"' if it ends with 'text'
    ```swift
    func check(text: String) {
        ...
    }
    ```

1. Given the following string: "Hello World!"
    1. put the first 5 characters to a new variable (how many options do you know?)
    1. put the five character before the last one into a variable (how many options do you know?)
    1. put the last 6 characters to a variable (how many options do you know?)

1. What is printed out?
    ```swift
    let value1 = "hello";
    for i in 0..<value1.count {
        if value1[i] == "l" {
            print("\(i)")
        }
    }
    ```

1. print out "found" if a string variable has the 'in' text inside

1. replace the spaces to '+'' in a string. How many options do you know?

1. print out a string where all the words are in reversed order. For example: 'hello in swift world' -> 'world swift in hello'

1. Create a siring with the content "I 💖 Swift"! The unicode value of 💖 is U+1F496

1. Write a short function which has a string parameter and returns with a 'nothing' if the string doesn't have content otherwise it should return with the original string

1. Write a short function which takes an optional string as parameter and returns with the string extended by ' extended'. If the parameter is nil it should return with 'silent'

1. What is printed out?
    ```swift
    var welcome = "h e l l o "
    welcome.insert("!", at: welcome.endIndex)
    var value1 = welcome.components(separatedBy: " ")
    value1.reverse()
    print(value1[1])
    ```
