

## Learning goals

- Exceptions
- Nullability
- Functions
  - Lambda Functions
    - If last parameter is function. 
  
  - Higher Order-functions



## Preparation

- [Learn Kotlin for Android: Lambda Expressions (Lesson 24)](https://www.youtube.com/watch?v=yx4CY_OUZok)
- [Learn Kotlin for Android: User Input (Lesson 6)](https://www.youtube.com/watch?v=XkBYH9vLs50)



## Topics



### Function

Remember the return types!

```kotlin
fun secondLargest(list: MutableList<Int>): Int {
    list.sort();

    return list.get(list.size - 2);
}

println(secondLargest(prices))
```



#### Lambda function

```kotlin
val max2 = {a:Int, b:Int ->
     if(a > b) {
         a // This is implicitly returned
     } else {
         b // This is implicitly returned
     }
}
println(max2(33,4)) // 33

val hundredLarger = {a:Int -> a + 100 }
println(hundredLarger(10)) // 110
```



### Exceptions

Handle errors using `try`, `catch`, and `finally` blocks.

```kotlin
try {
    val result = divideNumbers(10, 0)
} catch (e: ArithmeticException) {
    println("Cannot divide by zero.")
} finally {
    println("Operation attempted.")
}
```



## Exercises



### Opgave 2 - Level 1

Write variables to represent a rectangle:

- Height of 8.5
- Width of 5.5

Create a function that computes the area and the perimeter of the rectangle and print the results



### Opgave 7 - level 2

Write a Kotlin function that accepts two integers from the user and then prints 

- the sum
- the difference
- the product
- the average
- the distance  (the difference between integer, can only be positive)
- the maximum (the larger of the two  integers)
- the minimum (smaller of the two integers)

Here is an example:

```
Input 1st integer: 25
Input 2nd integer: 5
Expected Output:
Sum of two integers: 30
Difference of two integers: 20
Product of two integers: 125
Average of two integers: 15.00
Distance of two integers: 20
Max integer: 25
Min integer: 5
```



#### Lambda functions

**A)**

- Write a function that uses the filter function to filter all numbers of a list greater than 10



**B)**

- Write a function that takes an array of strings and returns an array with each strings length - if the strings has a length above 5 otherwise return 0 on the index.
  - Hint: Use the [map](https://kotlinlang.org/docs/collection-transformations.html) function.

**C)**

- Write a function that takes a list of degrees in fahrenheit and returns and array with each degree in celcius.
  - Hint: Use the [map](https://kotlinlang.org/docs/collection-transformations.html) function.

**D)**

- Write your own higher order function (A function that takes a function as argument)
- The higher order function takes 3 parameters: a string `s`, a number `n` and a function
- Use the higher order function with 2 lambda functions:
  - A function that returns a string containing `s` `n` amount of times: E.g hello, 3 -> hellohellohello
  - A function that returns a string with the first letter of `s` `n` amount of times: E.g hello, 3 -> hhh

Example from class:

```kotlin
// Higher order function example: Calculator
// This is the higher order function that takes a function as parameter (2 ints and returns an Int)
fun calculate(x: Int, y: Int, operation: (Int, Int) -> Int): Int {
  return operation(x, y)
}
fun add(x: Int, y: Int): Int {
  return x + y
}
fun subtract(x: Int, y: Int): Int {
  return x - y
}
fun multiply(x: Int, y: Int): Int {
  return x * y
}

fun main() {
  val result1 = calculate(10, 5, ::add)

  val result2 = calculate(10, 5, ::subtract)

  val result3 = calculate(10, 5, ::multiply)

  
  //WITH LAMBDA NOTATION the three functions add/subtract/multiply are then redundant
  val result1AsLambda = calculate(10,5) { x, y -> x + y}
  
  val result1AsLambda = calculate(10,5) { x, y -> x - y}
  
  val result1AsLambda = calculate(10,5) { x, y -> x * y}
  
} 
```



**Advanced (Optional)**

**A)**

Write a dice function that [generates](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.random/-random/) and returns a random number between 1-6.

- Write another function that uses the dice function to roll an amount of times decided by the user.
  - The functions returns the dice rolls as a list
- Write a function that takes the dice rolls as a parameter and returns the average
- Write a function that takes the dice rolls as a paramater and returns the mean
- Write a function that takes the dice rolls as a parameter and returns how many instances of 6 was rolled



- When testing your functions it could be beneficial to instantiate a test-list with values you know.



**B)**

From: [Advent of code](https://adventofcode.com/2023/day/1)

The newly-improved calibration document consists of lines of text; each line originally contained a specific *calibration value* that the Elves now need to recover. On each line, the calibration value can be found by combining the *first digit* and the *last digit* (in that order) to form a single *two-digit number*.

For example:

```
1abc2
pqr3stu8vwx
a1b2c3d4e5f
treb7uchet
```

In this example, the calibration values of these four lines are `12`, `38`, `15`, and `77`. Adding these together produces `*142*`.

Consider your entire calibration document. *What is the sum of all of the calibration values?*



- Create a file with the [data](https://adventofcode.com/2023/day/1/input) as input
- Find a way to read the file - I would suggest [readLines 2.4](https://www.baeldung.com/kotlin/read-file)
  - The correct answer is 55002