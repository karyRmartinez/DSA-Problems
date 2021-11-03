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
**
//Given a string, return the first recurring character in that string. If there's no recurring character, return a "_"
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
