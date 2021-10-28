# DSA-Problems

** get intersection

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




/* 
Given a string str, a duplicate removal consists of choosing two adjacent and equal letters, and removing them.

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
