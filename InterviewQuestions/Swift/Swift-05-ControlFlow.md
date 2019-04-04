# Control Flow

1. Print out the speed of all cars in a separate line, like "The Astra can go with 205km/h".
    ```swift
    let speedOfCars = ["Astra": 205, "Golf": 200, "Corolla": 190]
    ```
1. Print out how much faster can go each car than a bicycle. like "The astra can go 5,125 times faster than a bicycle."
    ```swift
    let speedOfBicycle = 40
    ```

1. What is the 'sum'?
    ```swift
    var sum = 0
    for i in 2...5 {
        for j in 2..<3 {
            if i > j {
                sum += i*j
            }
        }
    }
    print(sum)
    ```
1. Create a human readable sentence from 'array' using a while loop
    ```swift
    let array = ["this", "is", "a", "quite", "long", "sentence"]
    ```
1. What will be the 4 printed value?
    ```swift
    func while1(count: Int) -> Int {
        var num = 1
        sum = 0
        repeat {
            sum += num
            num += 1
        } while num < count
        return sum
    }

    func while2(count: Int) -> Int {
        var num = 1
        sum = 0
        while num < count {
            sum += num
            num += 1
        }
        return sum
    }

    print(while1(count: 5))
    print(while2(count: 5))
    print(while1(count: 1))
    print(while2(count: 1))
    ```
1. Create a small program, which simulates 50 dice throws and prints out the thrown values. (use the 'random' variable)
    ```swift
    let random = Int.random(in: 1...6)
    ```
1. Improve your previous program to collect which number was thrown how many times.













1. Write a short code to check the number of dices equals 50: print out the sum of the dices for all cases
1. Order the dice values by frequency (decreasing list). (This is a harder task on paper, you can use Xcode and solve it later if you want.)


1. Create a function, which prints out the how many times the specific dice values were thrown. Use switch and the following format: "One was thrown '10' times."











1. Create a funtion, which categorizes the dice values. Use switch and the following print calls.
    ```swift
    func categorizeValue(_ value: Int) {


        print("Less than four is not enough")


        print("Still not too good")


        print("Six is perfect")


        print("Value should be between 1 and 6")

    }
    ```

1. Handle all of the possible values of 'result' in a switch.
    ```swift
    func loadNextMovieTitle() -> (String?, Error?) {
        //whatever
    }

    let result = loadNextMovieTitle()
    ```











1. You can find an immaginary expected distribution in the expectedDistribution dictionary. Fill in the cases, to compare your actual distribution with the expected, and print out the defined messages.
    ```swift
    let expectedDistribution = [1: 5, 2: 5, 3: 5, 4: 10, 5: 10, 6: 15]

    func compareDistribution(actualDict: [Int: Int]) {
        for i in 1...6 {
            guard let expected = expectedDistribution[i], let actual = actualDict[i] else {
                fatalError("We are not handling in this example")
            }
            switch (expected, actual) {
            case 

                print("/(i) was thrown less times than we expected.")
            case 

                print("/(i) was thrown more times than we expected.")
            case 

                print("/(i) was thrown exactly as many times as we expected.")
            default:
                continue
            }
        }
    }
    ```

1. What will be the output?
    ```swift
    func myFunc(limit: Int) {
        for i in 0...limit {
            switch i {
            case let i where i % 2 == 0:
                continue
            case let i where i % 2 == 1:
                fallthrough
            case let i where i == 7:
                break
            case let i where i == 9:
                return
            default:
                continue
            }
            if i == 9 {
                print(11)
                return
            }
            print(i)
        }
    }
    myFunc(limit: 10)
    ```

1. Create a 'greetings' function, which reverses the name of the person and says hello to him except for "John". The function can simly return for "John". For example in case of "Mike" it prints out "Hello ekiM".
    ```swift
    func greetings(_ name: String?) {
    ```
