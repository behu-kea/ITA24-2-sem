# Kotlin intro



## Course outline

- CS 101
  - Weekly handins first 3 weeks
- Android with Kotlin
- 1 project
  1. large 11 week project with 2 handins (iterations) relevant for you
     - You have to find your own problem/project
- Test i uge 6. Trivselssamtaler efter 5 uger



<!--

## After class considerations

- Really nice class. 
- Nummerplade opgaven var lidt stenet

-->



### Learning goals

- My approach to learning something new
  - YouTube & ChatGPT
    - Multiple YouTube videos on same topic. What are the essential topics all the videos are focusing on? Supply with ChatGPT is that 
    - Fx learning sorting and big O:
      - **ChatGPT:** "I am learning about sorting and Big O. What are the different topics within that?". With the answer from ChatGPT. "Now figure out which of these topics i already know. do that by asking me questions, making me write code, etc. Thats up to you."
      - **YouTube:** Search for: "Big O sorting", "sorting in kotlin", "Big O kotlin", "sorting datastructure kotlin"
      - Watch videos, consolidate what i learnt. Write a markdown file that teaches the topic i am learning. 
      - Do practical coding challenges. Either from ChatGPT or from just stuff i find online. **This is where the actual learning takes place**. 
  
  - Figure out your learning gaps (if you dont know them yourself)
    - Ask ChatGPT to quiz you and give you feedback: "Hey ChatGPT, i am learning Kotlin i am not sure where my knowledge gaps are. Ask me 10 questions where i have to answer. When you are done. Give me feedback on where my knowledge gaps are."
  
  - Get an overview of what you need to learn. What can you already know? What different topics are there within what i am learning.
  - Try and use what you already know to learn new stuff.
    - Is this the `when` statement just like if else in javascript?
    - Is `Box` in Compose UI just like a `div` in html?
  
  - Now create projects, exercises, problems that i have to solve with code. This is where the learning takes place
  - Write a markdown file that teaches what i am learning. Super useful!!!
  - Seek discomfort. I go towards what i dont know. Constantly challenging myself. Learning takes place where there is discomfort/frustration (my take)
  - Be reflective about your learning strategy. Is the way you are learning right now the best strategy for you?
  -  IN CS101 your focus should be on syntax and the new concepts!
  
- Kotlin
  - Compile vs runtime
  - Interpretation vs compilation Tjek NIFR slides
  - JIT
  - Syntax
- Debugging
- Typer
  - Strenge
    - String literal
  - Boolean
  - Integer, float, double
  - Array fixed number of values
  - List
- Conditional (if/else)
  - Equality
  - When
- Loops
  - Ranges



<!--

## Peer instruction



### Question 1

What will the following code output?

```kotlin
val str = "Kotlin"
val length = str.length
println("The length of the string is: $length")
```

1. The length of the string is: 6
2. The length of the string is: Kotlin
3. The length of the string is: 7
4. Syntax error
5. None of the above



### Question 2

What will this loop print?

```kotlin
for (i in 1..5) {
    if (i == 3) break
    println(i)
}

```

1. 1 2 3 4 5
2. 1 2 3
3. 1 2
4. 3
5. None of the above



### Question 3

```kotlin
val list = listOf(1, 2, 3, 4, 5)
println(list[3])
```



-->



## Benjamin koder

Create som code that defines an array of integers. The code should iterate through the array and apply the following transformations:

- If an element is even, divide it by 2.
- If an element is odd, multiply it by 3 and add 1.

```kotlin
original_array = [1, 2, 3, 4, 5]
transformed_array = transformArray(original_array)
print(transformed_array) // [4, 1, 10, 2, 16]
```

It should log the transformed array

Cover nullability og debugging



## Preparation

- [Installer Android Studio](https://developer.android.com/studio)
- [Kotlin in 100 Seconds](https://www.youtube.com/watch?v=xT8oP0wy-A0)
- [Learn Kotlin in 12 Minutes](https://www.youtube.com/watch?v=iYrgWO2oibY)
- [Learn Kotlin for Android: When (Lesson 8)](https://www.youtube.com/watch?v=dollprkCDnk)
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



### Conditional statement

```kotlin
val age = 18
if (age >= 25) {
    println("You are an older adult")
} else if(age >= 18) {
    println("You are an adult")
} else {
    println("You are a minor.")
}
```



Using `if` as an Expression. Also called a ternary expression

```kotlin
val max = if (a > b) a else b
```



`when` Expression

```kotlin
val grade = 'A'
when (grade) {
    'A' -> println("Excellent")
    'B' -> println("Good")
    'C' -> println("Fair")
    else -> println("Poor")
}
```



### Loops

For Loop

```kotlin
for (i in 1..5) {
    println("Iteration $i")
}
```



While loop

```kotlin
var i = 0
while (i < 5) {
    println("Count: $i")
    i++
}
```



Ranges

```kotlin
val numbers = 1..10 // Includes 10
val letters = 'a' until 'z' // Excludes 'z'
```



## Opgaver



### Benjamins læringstilgang

I kan prøve min tilgang til læring hvis i tør. Men husk at være refleksiv omkring jeres læring! Ellers er der mere klassiske opgaver nedenfor



### Opgave 1 - Level 1

Do these steps one step at a time! Think about what type of data should be stored in the different variables

1. Create a variable called `age` (no reassignment!)
2. Create another variable called `height`
3. Assign `age` to be your age
4. Assign `height` to be your height in meter
5. Create the variable `shoeSize` and assign it to be your shoesize
6. Create a variable called `name` and assign this to your name



### Opgave 2 - Level 1

- Convert a string to uppercase
- Get the character on index 3
- Print the index of a character in the string
- Concatenate two different string
- Check these strings are equal to each other. Uppercases should be ignored!
  - `hello`, `ollhe` should print `false`
  - `bike`, `banana` should print `false`
  - `name`, `NaMe` should print `true`
  - `yes`, `yes` should print `true`



### Opgave 3 - level 1

Create a program that calculates and prints the sum of all even numbers between 1 and 50 using a `for` loop.



### Opgave 4 - level 2

Create a `List`. Add some prices to the `List`. Now find the second largest integer in that array



### Opgave 5 - level 1

Assign three variables `sideA`, `sideB`, and `sideC` representing the lengths of a triangle's sides. Use conditionals to determine and print the type of triangle:

- If all sides are equal, print `"Equilateral triangle"`.
- If exactly two sides are equal, print `"Isosceles triangle"`.
- If all sides are different, print `"Scalene triangle"`.
- If the sides cannot form a valid triangle (the sum of any two sides must be greater than the third), print `"Not a valid triangle"`.



### Weekend or Weekday - level 1

Create a program that takes an integer (1-7) representing a day of the week (1 for Monday, 7 for Sunday) and prints whether it's a weekday or weekend using a `when` expression.



### Exercise 5 - level 2

Write a program that loops through the numbers from 1 to 100. For each number, use conditionals to check the following:

- If the number is a perfect square **and** even, print the number and its square root.
- If not, continue to the next number without printing.

*A perfect square is an integer that is the square of an integer (e.g., 16 is a perfect square because it is 4 squared).*



### Opgave 6 - level 2

Simulate the growth of a population starting with 1,000 individuals. Each year, the population increases by 5%. Use a loop to calculate and print the population at the end of each year for up to 10 years. If at any point the population exceeds 1,500, print `"Population has exceeded 1,500"` and stop the simulation.



### Opgave 6 - level 2

Write some code that prompts the user to provide a number, computes the half of the number and prints the result with a friendly message

*Research how inputs work in Kotlin*



## 🔐 The code breaker - Level 3

[https://behu.gitbook.io/java-first-semester/projects/the-code-breaker#the-code-breaker](https://behu.gitbook.io/java-first-semester/projects/the-code-breaker#the-code-breaker)
