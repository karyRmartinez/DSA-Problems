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
