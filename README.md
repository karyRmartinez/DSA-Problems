# DSA-Problems

**Greatest Number**
```
func greatestNumber(_ arr: [Int]) -> Int {
  var result = 0

  for num in arr {
    if num > result {
      result = num 
    }
  }
  return result
}

print(greatestNumber([4, 2, 7, 1, 3]))

//O(n)

// 1st loop - num = 4, result = 0
// 2nd loop - num = 2, result = 4
// 3rd loop - num = 7, result = 4
// 4th loop - num = 1, result = 7
// 5th loop - num = 3, result = 7

```



```
**get intersection**

let inputA = [1,2,3,4,5];
let inputB = [0, 2, 4, 6, 8];

func getIntersection(from array1: [Int], and array2: [Int]) {
  var intersection = [Int]()
  var dictionary = [Int:Int]()

  for element in array1 {
    if let count = dictionary[element] {
      dictionary[element] = count + 1
    }
    else {
      dictionary[element] = 1
    }
  }

  for element in array2 {
    if let count = dictionary[element] {
      dictionary[element] = count + 1
      intersection.append(element)
    } else {
      dictionary[element] = 1
    }
  }

  print(intersection, dictionary)
}

getIntersection(from: inputA, and: inputB)


```
```
/* 
**Given a string str, a duplicate removal consists of choosing two adjacent and equal letters, and removing them.**

We repeatedly make duplicate removals on S until we no longer can.

Return the final string after all such duplicate removals have been made. It is guaranteed the answer is unique.

let input = "bookkeeper"
=> "bper"

let input = "abbaca"
=> "ca"
-> "abbaca" -> "aaca" -> "ca"

*/

// loop through the string 
// look duplictes
// remove all duplicate until I find no duplicates
// "abbaca"
// ['c']

func removeDuplicates(str: String) -> String {
  var stack = [Characters]()

  for letter in str == 0 {
    letter.remove
    if (stack.last == letter) {
      stack.removeLast()
    }
    if stack.isEmpty {
      stack.append(letter)
    }
    if stack.last =! letter {
      stack.append(letter)
    }
  }

  return 
}
```




```

/*
**1. Write a function that returns the intersection of two array. The intersection is a third array that contains all values contained within the first two arrays.**
ex. - The intersection of [1,2,3,4,5] and [0, 2, 4, 6, 8] is [2, 4].

(If your programming language as a built-in way of doing this, don't use it. The idea is to build the algorithm yourself.)

The function should have a complexity of 0(N).
*/

// look at each index 

// O ( N * M ) <- Bad! 

func getIntersection(_ nums1: [Int],_ nums2: [Int]) -> [Int] {

  var intersection = [Int]()
  var dict = [Int: Bool]()
  
  // for value in nums1 {
  //   dict[value] = true
  // }

  for key in 0..<nums1.count {
        dict[nums1[key]] = true
    }

  for key in 0..<nums2.count {
    if dict[nums2[key]] != nil {
      intersection.append(nums2[key])
    }
  }

  print(dict)
  return intersection

}

print(getIntersection([1,2,3,4,5],[0, 2, 4, 6, 8]))

//external paramaters
//internal paramaters
//func getIntersection(from array1: [Int],and array2: [Int]) -> [Int]
//getIntersection(from: [], and: [])
// adding a dictionary to store my key of type Int and my value of also type Int
//looping through my array looking through to my intersection
// once i have looped through my array i will add to my intersection

/*
```

```
**3. Write a function that accepts a string that contains all the letters of the alphabet except one and returns the missing letter.**

ex. - The string "the quick brown ox jumps over a lazy dog" contains all the letters in the alphabet except the letter "f".

The function should have a time complexity of O(N).
*/

func getMissingLetter(in string: String) -> String {
  var dict = [Character: Bool]()
  var missingLetter = String()

  for key in string {
    dict[key] = true 
  }
   print(dict)
  return missingLetter
 
}
print(getMissingLetter(in: "the quick brown ox jumps over a lazy dog"))
```


```
//I want to use a dictionary that will keep track of both the number AND the index where the number is found.
//var numbersSeenDict: [Int: Int] = [2: 0, 8: 1, 11: 2, 15: 3]

// func twoSumVersion2(nums: [Int], target: Int) -> [Int] {
//   var numberSeen = Set<Int>()

//   for currentNumber in nums {
//     if numberSeen.contains(target - currentNumber) {
//       // print(currentNumber, target - currentNumber)
//     } else {
//       numberSeen.insert(currentNumber)
//     }
//   }
//   return [Int]()
// }
// func twoSumVersion1(nums: [Int], target: Int) -> [Int] {
  
//   //Big O Notation = O(n^2) -> Quadratic runtime
//   for numberPointerOne in nums {
//     for numberPointerTwo in nums {
//       if numberPointerOne + numberPointerTwo == target {
//         return [numberPointerOne, numberPointerTwo]
//       }
//     }
//   }
//   return [Int]()
// }


//     func lengthOfLongestSubstring(_ s: String) -> Int {
//         var charDic = [Character:Int]()
//         var chars = Array(s)
//         var i = 0 , ans = 0
//         for  j in  0..<s.count {
//             if let index = charDic[chars[j]]{
//                 i = max(index, i)
//             }
//             ans = max(ans, j-i+1)
//             charDic[chars[j]] = j+1
//         }
//         return  ans
//     }

```

```
// Implement an algorithm to determine if a string has all unique characters. What if you cannot use additional data structures?

// input - string ,lowercase
// output - boolean true - all unique characters false- no unique characters
//example: bcd
// output : true

//example: aaabcca
// output: false


// edge cases - 

// constraints - 

var inputFalse = "d"

//["d" : true, "u" : true, "z" : true]
//keys have to be unique 
// == -> one of the comparion operators -> equal to
// = -> assignment operator

func isUniqueCharacters(_ string :String) -> Bool {
var dict = [Character: Int]()

//check the length of the string, return if less than 2
    //if string.count < 1 { return true }
    guard string.count > 1 else { return true }

// 1. loop through my string of characters
for char in string {
  if let _ = dict[char] {
    return false
  }
  else {
    dict[char] = 1
  }
}

// all characters are unique
return true
}

print(isUniqueCharacters(inputFalse))

//function to generate sample input strings
func randomString(length: Int) -> String {
  let letters = "abcdefghijklmnopqrstuvwxyz"
  return String((0..<length).map{ _ in letters.randomElement()! })
}
var input = randomString(length: 10)



print(input)
```

**Bubble Sort**
```
func bubbleSort(_ array: inout [Int]) -> [Int] {
   var sorted = false
   var swaps = 0

   while !sorted {
     sorted = true
     for currentIndex in 1..<array.count {
       if array[currentIndex - 1] > array[currentIndex] {
         let temp = array[currentIndex - 1]
         array[currentIndex - 1 ] = array[currentIndex]
         array[currentIndex] = temp
         sorted = false
         swaps += 1
       }
     }
   }
//Array is sorted in \(numSwaps) swaps., where  is the number of swaps that took place.
print("Array is sorted in \(swaps) swaps.")
//First Element: firstElement, where  is the first element in the sorted array.
print("First Element: \(array.first!)")
//Last Element: lastElement, where  is the last element in the sorted array.
print("Last Element: \(array.last!)")
return array

}

var input = [6, 4, 1]
print(bubbleSort(&input))
```

```

**Given an integer array arr that is guaranteed to be a mountain, return any i such that arr[0] < arr[1] < ... arr[i - 1] < arr[i] > arr[i + 1] > ... > arr[arr.length - 1].**

    func peakIndexInMountainArray(_ arr: [Int]) -> Int {
            guard arr.count >= 3 else{
            return -1
        }

        var startIndex = 0
        var endIndex = arr.count - 1

        while startIndex <= endIndex{
            let midIndex = startIndex + (endIndex - startIndex) / 2

            if arr[midIndex] < arr[midIndex + 1]{
                startIndex += 1
            } else{
                endIndex -= 1
            }
        }

        return startIndex
    }
```

```

**Given a string, return the first recurring character in that string If there's no recurring character, return a "_"
//Input 1: ABCA -> A
//Input 2: BCABA -> B
//Input 3: ABCDE -> _**

func findRecurringCharacterVersion2(str: String) -> Character {
  var charsSeen = Set<Character>()

  for currentChar in str {
    if charsSeen.contains(currentChar) {
      return currentChar
    } else {
      charsSeen.insert(currentChar)
    }
  }
  return "_"
}

print("Linear Approach: \(findRecurringCharacterVersion2(str: inputString))")

```
```
Lemonade stand
**// each lemonade cost $5
// each customer pays with 5,10,20
// return bool

//example: 5, 10, 20 -> true
 // if two customers give 10 one after another no change
 // bank starts at 0**
 
 
 func(arr: [Int])-> Bool {
  var bankFive = 0
  var bankTen = 0
  var bankTwenty = 0
  for bill in arr { //
    if bill == 5 {
      bankFive += 1
    } else if bill == 10 {
      bankTen += 1
      bankFive -= 1 
    }else if bill == 20 {
      bankTwenty += 1
      if bankTen > 0 {
        bankTen -= 1
        bankFive -= 1
      } else {
         bankFive -= 3
      }

    }else{
      return false
    }
  }
  if bankFive > 0 {
    return true
  }else {
    return false
  }
 }
```




1. Factorial - the product of all positive integers less than or equal to a given positive integer and denoted by that integer and an exclamation point.

Given an integer, n, write a function that produces it's factorial value.

Example 1:
  Input: n = 3
  Output: 6
  Explanation: 3 * 2 * 1 = 6
  
Example 2:
  Input: n = 4
  Output: 24
  Explanation: 4 * 3 * 2 * 1 = 24

Example 3: 
  Input: n = 5
  Output: 120
  Explanation: 5 * 4 * 3 * 2 * 1 = 120

Approach
  - BC: if n === 1 || n === 0 return 1
  - Init sum set to 0
  - sum = Call factorial recursively (n - 1)
  - sum (6) += 3 * n - 1 = 2
*/
function factorial(n) {
  if(n <= 1) return 1
  return n * factorial(n - 1)
}
let n1 = 3;
// console.log(factorial(n1));
/* Time Complexity: O(n)
   Space Complexity: O(n)

The time complexity of the factorial algorithm implemented using recursion is O(n), where n is the input number for which we are calculating the factorial.

This is because, in the worst case, the function needs to make n-1 recursive calls before it reaches the base case of n = 0 or n = 1. Each recursive call takes O(1) time to execute, so the total time complexity is the number of recursive calls multiplied by the time complexity of each call, which is O(n) in this case.

In terms of space complexity, the factorial algorithm implemented using recursion has a space complexity of O(n) as well, since each recursive call requires a new activation record to be pushed onto the call stack until the base case is reached. This can result in a large amount of memory usage for large values of n.

*/
// SWIFT APPROAH
// func factorial(_n: Int) -> Int {
//let n = 1

// if  n <=1 {
// return 1
//}
// return n * factorial (n-1)
// print(n)
//}

// func factorial(_ n: Int) -> Int {
//     if n == 0 {
//         return 1
//     } else {
//         return n * factorial(n - 1)
//     }
// }


/*
2. Fibonacci - a sequence such that each number is the sum of the two numbers preceding it. 

The Fibonacci sequence goes as follows:
1, 1, 2, 3, 5, 8, 13, 21, ... and so on

At the 0 index, we assign value of 1.
At the 1 index, we assign value of 1.
At the 2 index, 2 is the sum of 1 and 1, so the Fibonacci number of 2 is 2.
At the 3 index, 3 is the sum of 2 and 1, so the Fibonacci number of 3 is 3.
At the 4 index, 5 is the sum of 3 and 2, so the Fibonacci number of 4 is 5.
At the 5 index, 8 is the sum of 5 and 3, so the Fibonacci number of 5 is 8.
At the 6 index, 13 is the sum of 8 and 5, so the Fibonacci number of 6 is 13.
At the 7 index, 21 is the sum of 13 and 8, so the Fibonacci number of 7 is 21.

Given an integer, n, write a function that produces it's Fibonacci number.

Example 1:
  Input: n = 5
  Output: 8
  
Example 2:
  Input: n = 6
  Output: 24

Example 3: 
  Input: n = 15
  Output: 610

Approach
  - BC: if n === 1 || 0 then return 1
  - return fib(n - 1) + fib(n - 2)
*/
function fib(n) {
  if(n <= 1) return 1
  return fib(n - 1) + fib(n - 2)
}
let n2 = 5;
console.log(fib(n2));
/* Time Complexity: O(2^n) -> every recursive call leads to two additional calls
   Space Complexity: O(n) -> callstack holds space regardless
*/





//  implementing a Node abstract data structure

//class ListNode<T> {
//     var value: T
//     var next: ListNode<T>?
// Singly linked list
  //var previous: Node? // Doubly linked list
  
    
//     init(_ value: T, _ next: ListNode<T>? = nil) {
//         self.value = value
//         self.next = next
//     }
// }

// func reverseLinkedList<T>(_ head: ListNode<T>?) -> ListNode<T>? {
//     var prevNode: ListNode<T>? = nil
//     var currNode = head
    
//     while currNode != nil {
//         let nextNode = currNode?.next
//         currNode?.next = prevNode
//         prevNode = currNode
//         currNode = nextNode
//     }
    
//     return prevNode
// }

// Sliding window

Given two strings s and t of lengths m and n respectively, return the minimum window 
substring
 of s such that every character in t (including duplicates) is included in the window. If there is no such substring, return the empty string "".

The testcases will be generated such that the answer is unique.

class Solution {
    func minWindow(_ s: String, _ t: String) -> String {
        var sArray: [Character] = Array(s)
        var tArray: [Character] = Array(t) 
        var wordDictionary: [Character: Int] = [:]

        for char in t {
            if let value = wordDictionary[char] {
                wordDictionary[char] = value + 1
            } else {
                wordDictionary[char] = 1
            }
        }

        var startIndex: Int = 0
        var endIndex: Int = 0
        var sCount: Int = s.count
        var minLength: Int = Int.max 
        var filled: Int = t.count
        var start: Int = 0

        while (endIndex < sCount) {
            let head: Character = sArray[endIndex]
            if let value = wordDictionary[head] {
                wordDictionary[head] = value - 1
                if value > 0 {
                    filled -= 1
                }
            }
            
            while filled == 0 {
                let tail: Character = sArray[startIndex]

                if minLength > endIndex - startIndex + 1 {
                    minLength = endIndex - startIndex + 1
                    start = startIndex
                }

                if let value = wordDictionary[tail] {
                    wordDictionary[tail] = value + 1

                    if value == 0 {
                        filled += 1
                    }
                }
                startIndex += 1
            }
            endIndex += 1
        }

        return minLength == Int.max ? "" : String(sArray[start ..< start + minLength])
    }
}

