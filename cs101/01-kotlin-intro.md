# Kotlin intro



## Content



### Course outline

- CS 101
  - Weekly handins
- Android with Kotlin
- 1 project
  1. large 11 week project with 2 handins (iterations) relevant for you
     - You have to find your own problem/project
- Trivselssamtaler efter 5 uger



<!--

## After class considerations

- Really nice class. 
- Nummerplade opgaven var lidt stenet

-->



### Learning goals

- Kotlin
  
  - Compile vs runtime
  - Syntax
- Debugging
  
- Typer
  - Strenge
    - String literal
  - Boolean
  - Integer, float, double
  - Array fixed number of values
  - List
  - Map
    - mapOf
- Input
- Functions
- Nullability



## Benjamin koder

Create a function named `transformArray` that takes an array of integers as input. The function should iterate through the array and apply the following transformations:

- If an element is even, divide it by 2.
- If an element is odd, multiply it by 3 and add 1.

```kotlin
original_array = [1, 2, 3, 4, 5]
transformed_array = transformArray(original_array)
print(transformed_array) // [4, 1, 10, 2, 16]
```

It should return the transformed array

Cover nullability og debugging



## Preparation

- [Installer Android Studio](https://developer.android.com/studio)
- [Kotlin in 100 Seconds](https://www.youtube.com/watch?v=xT8oP0wy-A0)
- [Learn Kotlin in 12 Minutes](https://www.youtube.com/watch?v=iYrgWO2oibY)
- [https://kotlinlang.org/docs/basic-syntax.html](https://kotlinlang.org/docs/basic-syntax.html) Optional



## Topics



### Main function

A kotlin file needs a main function

```kotlin
fun main() {
		println("Hello World");
}
```



### Variables

`var` is a variable that can be changed (mutable)

`val` is a variable that cannot be changed (nonmutable)



```kotlin
var price = 43;
price = 33;

val age = 36;
age = 55; // Error here!
```



### Types

For CS101 please declare your types for all variables and functions. If you do not declare your type the type will be interpreted (guessed) by the interpreter



```kotlin
var price: Int = 43;
price = 33;

val height: Double = 1.78;

val isExpensive: Boolean = true;
```



For some type we can just write the value directly. Like fx a string `val name: String = "Benjamin"`. For other more complex types we need to call a function to get the type we need. 



WRITE MORE HERE!!!



### `List`

A `List` is like an array in javascript. 

An array in Kotlin cannot be changed! Therefore usually we use `List` in Kotlin. Only if we have a usecase where a list should not be changed should we use an array

```kotlin
val array: Array<String> = arrayOf("asd", "hej");
```



To create a list, remember to think about if it should be mutable or non mutable (can be changed or cant be changed)

```kotlin
val prices: MutableList<Int> = mutableListOf(2,3,4,5);
```

The list works a lot like in js

```kotlin
val prices: MutableList<Int> = mutableListOf(2,3,4,5);
println(prices[1])

prices.add(67);
println(prices)
```



### `Map`

```kotlin
val cars:MutableMap<String, String> = mutableMapOf("asd" to "23");
cars["hej"] = "asd";
cars.get("hej")
```



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



## Opgaver



### Opgave 1 - Level 1

Do these steps one step at a time! Think about what type of data should be stored in the different variables

1. Create a variable called `age` (no reassignment!)
2. Create another variable called `height`
3. Assign `age` to be your age
4. Assign `height` to be your height in meter
5. Create the variable `shoeSize` and assign it to be your shoesize
6. Create a variable called `name` and assign this to your name



### Opgave 2 - Level 1

Write variables to represent a rectangle:

- Height of 8.5
- Width of 5.5

Create a function that computes the area and the perimeter of the rectangle and print the results



### Opgave 3 - Level 1

- Convert a string to uppercase
- Get the character on index 3
- Print the index of a character in the string
- Concatenate two different string
- Check these strings are equal to each other. Uppercases should be ignored!
  - `hello`, `ollhe` should print `false`
  - `bike`, `banana` should print `false`
  - `name`, `NaMe` should print `true`
  - `yes`, `yes` should print `true`



### Opgave 4 - level 1

Create a `Map` that contains the numberplate of a car and that cars color



### Opgave 5 - level 2

Create a `List`. Add some prices to the `List`



Now create a function that takes a `List` of integers and returns the second largest integer in that array



Use the function to find the second largest integer of the `List` created above



### Opgave 6 - level 2

Create a function that prompts the user to provide a number, computes the half of the number and prints the result with a friendly message

*Research how inputs work in Kotlin*



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



## 🔐 The code breaker - Level 3

[https://behu.gitbook.io/java-first-semester/projects/the-code-breaker#the-code-breaker](https://behu.gitbook.io/java-first-semester/projects/the-code-breaker#the-code-breaker)
