# Enumerations:

1. Create a `MovieFetcherError`, which has two values: network and parsing.
1. Declare a `fetch` function, which expects an URL as input parameter and calls back with an optional MovieFetcherError asynchronously.
1. Call the `fetch` function and process all possible outputs properly and print out meaningful messages about what happened.
1. Enhance MovieFetcherError to contain an HTTP error code in case of network issue and the content in case of parsing issue. Align the `fetch` function and the messages in the caller as well.
1. Write an if statement which prints out "Not Found" if the result of the fetch is that.
1. Create an enumeration called `Numbers`, which contains the numbers from `one` to `five` and has a raw value of Int. Define this as compact as possible.
1. Enhance the `Numbers` enum with a `stringValue` function, which returns with the number in english text (one, two...). Test it.
1. Create an `ApplicationError` enumeration, which contains two values: `fetchingFailed` and `uiLoadingFailed`. `fetchingFailed` should have a parameter, which is a `MovieFetcherError`.
1. Create a function, which processes an `ApplicationError` and prints out meaningful, detialed messages for the different situations. Avoid code duplication.
1. Define the `LinkedListItem`, on which you can run the following code:
   ```swift
   let third = LinkedListItem.endPoint(value: "Third")
   let second = LinkedListItem.linkNode(value: "Second", next: third)
   let first = LinkedListItem.linkNode(value: "First", next: second)

   var currentNode: LinkedListItem? = first

   while currentNode != nil {
       switch currentNode! {
       case .endPoint(let value):
           print(value)
           currentNode = nil
       case .linkNode(let value, let next):
           print(value)
           currentNode = next
       }
   }
   ```

1. Create equatibility check for the `MovieFetcherError`.
   ```swift
   extension MovieFetcherError: Equatable {
        public static func == (lhs: MovieFetcherError, rhs: MovieFetcherError) -> Bool {
            // implement this
        }
    }
   ```
