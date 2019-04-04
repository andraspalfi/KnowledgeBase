# Collection Types

[reference](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html)

1. What basic containers are supported by Swift?
1. Define an empty array of `int`
1. Define an array with the items "one", "two", "three" in it
1. Given an array with items '1,2,3' and an another one with values '1,3,5'
Create a third array containing all values of the two arrays
1. Declare an array with the values 1,2,3
    1. Then add a new item to it 4 (how many options you have to solve that?)
    1. Then add two more items: 5 and 6
    1. Change the second item to 7
1. Given an array of items "one", "two", "three". Create a new string with the number of items and the second item like "3: 'two'"
1. Create a short one liner method taking an array as parameter: print out the number of items or 'no items' in case there are no items in the array
1. Given the following array: let items = [5,4,3,2,1]
    1. Create a new array with the second, third and fourth item
    1. then add two new items to the new array: 7,8
    1. then replace the fourth and fifth element to 9,10
    1. place a new item to the second position: 11 (do not overwrite existing items)
    1. remove the third item
    1. remoce the last two items
    1. what's the result? (you can use playground)
1. given the array: ["a", "b", "c", "d"]
    Print out the indices with the content (0="a", 1="b" ...)
1. Given the following code and output:
code:
    ```swift
        print("count:  \(collection.count)")
        print("first:  \(collection[1]!)")
        print("second: \(collection[2]!)")
        print("third:  \(collection[3]!)")
    ```
    output:
    ```swift
    count:  3
    first:  1
    second: two
    third:  ["three", 2.05]
    ```
    
    Declare `collection`!
1. Define an empty dictionary where key is `int` and value is `string`
1. Define an dictionary with the items key 1,2,3 and the values "one", "two", "three" respectively
1. Given a dictionary of items 1:"one", 2:"two", 3:"three". Create a new string with the number of items and the value of key '2', like: "3: 'two'"
1. Declare a  dictionary with the items 1 value "one", 2 value "two", 3 value "three"
    1. Then add a new item to it 4:"four" (how many options you have to solve that?)
    1. Then add two more items: 5:"five" and 6:"six"
    1. Change the item 2 to "seven"
1. Create a short one liner method taking a dictionary [String:String] as parameter: print out the number of items or 'no items' in case there are no items in the dictionary
1. write code: check whether the dictionary contains an item with the key "one"
1. print our all keys of the dictionary
1. print out the key-value pair of a dictionary
1. write tiny method which updates a dictionary (can be global variable): when the key was in the dictionary already print out "existing" if this is a new key print out "new"
1. Given a dictionary with items 1 value "one", 2 value "two", 3 value "three" and an another one with items 1 value "one", 3 value "three", 5 value "five"'
Create a third dictionary containing all keys and values of the two dictionaries. If a key is in the first and the second dictionary keep the value from the first dictionary
1. Define an empty set of type String
1. Define a set of Ints with values 1,2,3 (how many options do you have?)
1. Insert a new value 4 to a Set of Ints 1,2,3
1. Remove the item 3
1. Print out "exists" if the value 1 is in the Set
1. Create a short one liner method taking a Set of Int as parameter: print out the number of items or 'no items' in case there are no items in the Set
1. Create a new string with the number of items and the second value of a Set of Ints 1,2,3 , like: "3: 2"
1. Given two Sets of Ints: 1,2,3 and 3,4,5. Create a new set...
    1. which contains all items which are in both Sets
    2. which contains only the unique values (only in the first or in the second exists)
    3. which contains all the items
    4. which are only in the first Set
1. Print out if set B is part of set A (all items in set B are in set A)
1. Print out if set A contains set B
1. Print out if set A and set B has common values
1. Print out if set A and set B doesn't have common values
