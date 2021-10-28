# DSA-Problems
'''
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


'''

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





'''

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
'''
