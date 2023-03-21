/*
This kata is about multiplying a given number by eight if it is an even number and by nine otherwise.
*/

// Solution 1
func simpleMultiplication(_ num: Int) -> Int {
  return num * (num % 2 == 0 ? 8 : 9)
}
// Solution 2
func simpleMultiplication(_ num: Int) -> Int {
  num * (num.isMultiple(of: 2) ? 8 : 9)
}

// ===============================================================

/*
Given a non-empty array of integers, return the result of multiplying the values together in order. Example:

[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24
*/

// Solution 1
func grow(_ arr: [Int]) -> Int {
  return arr.reduce(1,*)
}

// Solution 2
func grow(_ arr: [Int]) -> Int {
  var product = 1
  for num in arr {
    product *= num
  }
  return product
}

// Solution 3
func grow(_ arr: [Int]) -> Int {
  var number: Int = 1
  arr.forEach { number *= $0 }
  return number
}

// ===============================================================

/*
You will be given an array a and a value x. All you need to do is check whether the provided array contains the value.

The type of a and x can be String or Int.

Return true if the array contains the value, false if not.
*/

// Solution 1
func check<T: Equatable>(_ a: [T], _ x: T) -> Bool {
  return a.contains(x)
}

// Solution 2
func check<T: Equatable>(_ a: [T], _ x: T) -> Bool {
  return a.contains(x) ? true : false
}
// Solution 3
func check<T: Equatable>(_ a: [T], _ x: T) -> Bool {
  let result = a.filter {$0 == x}
  return !result.isEmpty
}

// ===============================================================

/*
You get an array of numbers, return the sum of all of the positives ones.

Example [1,-4,7,12] => 1 + 7 + 12 = 20

Note: if there is nothing to sum, the sum is default to 0.
*/

// Solution 1
func sumOfPositives (_ numbers: [Int] ) -> Int {
  return numbers.filter{$0 > 0}.reduce(0, +)
}

// Solution 2
func sumOfPositives (_ numbers: [Int] ) -> Int {
  var total = 0
  for number in numbers {
    if number > 0 {
      total += number
    }
  }
  return total
}

// Solution 3
func sumOfPositives (_ numbers: [Int] ) -> Int {
  return numbers.reduce(0){$0 + max($1, 0)}
}

// ===============================================================

/*
Your goal is to return multiplication table for number that is always an integer from 1 to 10.

For example, a multiplication table (string) for number == 5 looks like below:

1 * 5 = 5
2 * 5 = 10
3 * 5 = 15
4 * 5 = 20
5 * 5 = 25
6 * 5 = 30
7 * 5 = 35
8 * 5 = 40
9 * 5 = 45
10 * 5 = 50
P. S. You can use \n in string to jump to the next line.

Note: newlines should be added between rows, but there should be no trailing newline at the end. If you're unsure about the format, look at the sample tests.
*/

// Solution 1
func multi_table(_ number: Int) -> String {
  (1...10).map {"\($0) * \(number) = \($0 * number)"}.joined(separator: "\n")
}

// Solution 2
func multi_table(_ number: Int) -> String {
  var multiplicationTable = ""
  for num in 1...10 {
    multiplicationTable += ("\(num) * \(number) = \(number * num)\(num != 10 ? "\n" : "")")
  }
  return multiplicationTable
}

// Solution 3
func multi_table(_ number: Int) -> String {
  var result: String = ""
  for i in 1...10 {
    if i < 10 {
      result = result + "\(i) * \(number) = \(number * i)\n" 
    } else {
      result = result + "\(i) * \(number) = \(number * i)" 
    }
  }
  return result
}

// ===============================================================

/*
Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.
*/

// Solution 1
func evenOrOdd(_ number:Int) -> String {
  return number % 2 == 0 ? "Even" : "Odd"
}

// Solution 2
func evenOrOdd(_ n: Int) -> String {
    return n.isMultiple(of: 2) ? "Even" : "Odd"
}

// Solution 3
func evenOrOdd(_ number:Int) -> String {
  if number%2 == 0 {
    return "Even"
  } else {
    return "Odd"
  }
}

// ===============================================================

/*
Create a function take that takes an Array<Int> and an Int, n, and returns an Array<Int> containing the first up to n elements from the array.

If you need help, here's a reference:

https://developer.apple.com/documentation/swift/array
*/

// Solution 1
func take(_ arr: [Int], _ n: Int) -> [Int] {
  return Array(arr.prefix(n))
}

// Solution 2
func take(_ arr: [Int], _ n: Int) -> [Int] {
  return arr.count > n ? Array(arr[0..<n]) : arr
}

// ===============================================================

/*
Terminal game move function

In this game, the hero moves from left to right. The player rolls the dice and moves the number of spaces indicated by the dice two times.

Create a function for the terminal game that takes the current position of the hero and the roll (1-6) and return the new position.

Example:

move(3, 6) should equal 15
*/

// Solution 1
func move(_ p: Int, _ r: Int) -> Int { 
  return r * 2 + p
}

// ===============================================================

/*
Very simple, given an integer or a floating-point number, find its opposite.

Examples:

1: -1
14: -14
-34: 34
*/

// Solution 1
func opposite(number: Double) -> Double {
  return -number
}

// ===============================================================

/*
Complete the method that takes a boolean value and return a "Yes" string for true, or a "No" string for false.
*/

// Solution 1
func boolToWord(_ bool: Bool) -> String {
  bool ? "Yes" : "No"
}

// Solution 2
func boolToWord(_ bool: Bool) -> String {
  return bool == true ? "Yes" : "No"
}

// ===============================================================

/*
Given an array of integers, return a new array with each value doubled.

For example:

[1, 2, 3] --> [2, 4, 6]
*/

// Solution 1
func maps(a : Array<Int>) -> Array<Int> {
  return a.map { $0 * 2 }
}

// ===============================================================

/*
In this simple exercise, you will create a program that will take two lists of integers, a and b. Each list will consist of 3 positive integers above 0, representing the dimensions of cuboids a and b. You must find the difference of the cuboids' volumes regardless of which is bigger.

For example, if the parameters passed are ([2, 2, 3], [5, 4, 1]), the volume of a is 12 and the volume of b is 20. Therefore, the function should return 8.

Your function will be tested with pre-made examples as well as random ones.

If you can, try writing it in one line of code.
*/

// Solution 1
func findDifference(_ a: [Int], _ b: [Int]) -> Int {
  abs(a.reduce(1,*) - b.reduce(1,*))
}

// Solution 2
func findDifference(_ a: [Int], _ b: [Int]) -> Int {
  let reduceA = a.reduce(1, *)
  let reduceB = b.reduce(1, *)
  let result = reduceA - reduceB
  if result < 0 {
    return -result
  }
  return result
}

// Solution 3
func findDifference(_ a: [Int], _ b: [Int]) -> Int {
  var first: Int = a.reduce(1, { accum, next in accum * next })
  var second: Int = b.reduce(1, { accum, next in accum * next })
  return first > second ? first - second : second - first
}
