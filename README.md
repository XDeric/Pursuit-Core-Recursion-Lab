# Recursion Exercises

- ### Sum of all from 1 to n

Write a function that takes in a number as input and recursively finds the sum of all numbers up to and including that number.

```js
input: 6
output: 21

//21 = 6 + 5 + 4 + 3 + 2 + 1
```
```swift
var input = 6
var test = 0

func addItUp(_ currentNum: Int) {
if currentNum <= 0 {
return
}
test += currentNum
//print(test)
addItUp(currentNum - 1)
}

addItUp(input)
print(test)
```

- ### Multiply array

Write a function called `multArr` that takes in an array of numbers as an argument and recursively multiplies together all of the values in the array.

```js
multArr([2, 3, 5]); // returns 30
multArr([5, 5, 1, 2]); //returns 50
```
```swift
var newArr1 = [2, 3, 5] // returns 30
var newArr2 = [5, 5, 1, 2] //returns 50

func multArr(_ arr: [Int]) -> Int {
//base case
if arr.count == 1 { return arr[0] }

//recursive call
let firstElement = arr[0]
let remainingElements = Array(arr[1...])
return firstElement * multArr(remainingElements)
}
multArr(newArr1)
multArr(newArr2)
```

- ### Concatenate array

Write a function called `concatArr` that takes in an array of strings as an argument and recursively concatenates the strings together into a single string, with spaces between each original string.

```js
concatArr(['is', 'it', 'tomorrow']); // returns 'is it tomorrow'
concatArr(['or', 'just', 'the', 'end', 'of', 'time']); //returns 'or just the end of time'
```
```swift
func concatArr(_ arr: [String]) -> String{
//base case
if arr.count == 1 { return arr[0] }

//recursive call
let firstElement = arr[0]
let remainingElements = Array(arr[1...])
return "\(firstElement) \(concatArr(remainingElements))"
}

var test1 = ["is", "it", "tomorrow"] // returns 'is it tomorrow'
var test2 = ["or", "just", "the", "end", "of", "time"]
//returns 'or just the end of time'
concatArr(test1)
concatArr(test2)
```

- ### Sum evens

Write a function called `sumEvens` that takes in an array of numbers as an argument and recursively sums only the even numbers in the array.

```js
sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24
```
```swift
func sumEvens(_ arr: [Int]) -> Int {
//base case
if arr.count == 1 { if arr[0] % 2 == 0 {
return arr[0]
}
else {
return 0
}
}

//recursive call
var firstElement = Int()
if arr[0] % 2 == 0 {
firstElement = arr[0]
}
else {
firstElement = 0
}
let remainingElements = Array(arr[1...])
return firstElement + sumEvens(remainingElements)
}

sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24
```


- ### Recursive range

Write a function called `range` which takes in two numbers (num1, num2) as arguments. The function should return an array of numbers between num1 and num2.

```js
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]
```
```swift
func range(_ num1: Int, _ num2: Int) -> [Int]{
if num1 == num2{
return [num2]
}

//    var test = [Int]()
//    test.append(num1)

return [num1] + range(num1 + 1, num2)
}
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]
```


- ### Triple Step

A child is running up a staircase with n steps and can hop either 1 step 2 steps or 3 steps at a time. Write a function called 'tripleStep', that takes in an argument `n` that represents the number of steps in the staircase, and returns a count of how many possible ways the child can run up the stairs.

```js
tripleStep(3); //returns 4
tripleStep(4); //returns 7
tripleStep(5); //returns 13
tripleStep(10); //returns 274
```

Source: Cracking the Coding Interview

- ### Coin Combos

Given an infinite number of quarters, dimes, nickels, and pennies, write code to calculate the number of possible ways of giving exact change for `n` cents.

In other words, write a function called `coinCombos` that takes in one argument: `n`, which represents the total amount of money (in cents) that you need to make change for. Your function should return the amount of possible combinations you can make to return that exact amount of change.

For example:
```js
coinCombos(5); //returns 2
coinCombos(10); //returns 4
coinCombos(25); //returns 13
coinCombos(60); //returns 73
```

Source: CTCI

# Resources
- [JavaScript Recursion Exercises](http://www.w3resource.com/javascript-exercises/javascript-recursion-functions-exercises.php)
- [Swift Recursion Exercises](https://www.weheartswift.com/recursion/)
