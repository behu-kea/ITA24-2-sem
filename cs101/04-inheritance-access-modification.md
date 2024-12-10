# Inheritance and access modifiers



## Learning goals

- Properties
- Access Modifiers
- Inheritance
  - Override
- 4 pillars
- Interface



## Overview

- Talk about 4 pillars of OOP. With code examples



## Preparation

- [Fundamental Concepts of Object Oriented Programming](https://www.youtube.com/watch?v=m_MQYyJpIjg)
- [Learn Kotlin for Android: Inheritance (Lesson 17)](https://www.youtube.com/watch?v=33DNMPOFvuA)
- [Learn Kotlin for Android: Getters & Setters ( Lesson 16)](https://www.youtube.com/watch?v=tOCXISsfgUg)
- [Learn Kotlin for Android: Interfaces (Lesson 20)](https://www.youtube.com/watch?v=RctW18zpgec)



<!--

## Peer instruction

### Question 1

```kotlin
open class Base {
    open fun showMessage() {
        println("Base Message")
    }
}

class Derived : Base() {
    override fun showMessage() {
        println("Derived Message")
    }
}

fun main() {
    val obj: Base = Derived()
    obj.showMessage()
}

```

1. `Base Message`
2. `Derived Message`
3. Compilation error due to improper override
4. Runtime exception
5. None of the above



### Question 2

What access modifier is used to ensure a property can be accessed only within the same file?

1. `private`
2. `internal`
3. `protected`
4. `file`
5. None of the above



### Question 3

What will the following code print?

```kotlin
class User {
    var name: String = "Guest"
        set(value) {
            field = value.uppercase()
        }
}

fun main() {
    val user = User()
    user.name = "john"
    println(user.name)
}
```

1. `Guest`
2. `john`
3. `JOHN`
4. Compilation error due to invalid setter
5. None of the above

-->



## Topics



### Interface

An interface works a lot like a contract or a set of rules. In an interface we define attributes and functions a class should have to implement that specific interface. 

Lets get concrete:

This Interface defines what it is like to be a `Product`. That means that classes implementing this interface **has to have** 

- An attribute called `name` which is a `String`
- An attribute called `price` which is an `Int`
- An attribute called `name` which is an `Int`
- An function called `printProductDetails` 

```kotlin
interface Product {
    val name: String;
    val price: Int;
  	val id: Int;
    fun printProductDetails();
}
```

Here is how an `interface` gets implemented by a class

```kotlin
class Television: Product {
		override val name: String,
    override val price: Int,
    override val id: Int
) : Product {
    override fun printProductDetails() {
				println("${this.name} is an amazing television");
    }
}
```

Let's initialise a television

```kotlin
val samsungTelevision: Television = Television("Samsung TV", 8000, 123456789);
```

We use the `override` keyword because we are overwriting a property from the interface we are implementing

We can even add functionality inside of the interface:

```kotlin
interface Computer{
    val name: String;
    val price: Int;
    val location: Map<String, Double>;

    fun printLocation() {
        println("${this.name} is an amazing television");
    };
}
```

Now we dont need to override the `printLocation` method because it has been defined

A class can inherit from only one class but can implement mutiple interfaces





## Opgaver



### Opgave 1 - level 2

Write a class called `Animal` An `animal` has 3 properties:

- `name`
- `nrOfLegs`
- `isMammal`

Animal has a method: `makeSound()` that prints the sound of the an-
imal.

- Create 2 animal classes that extends the Animal class and overrides
  the method to produce their unique sound.
- Create a list, add 5 animals to the list and print every animals sound.
- Override the `toString` method such that if an animal object is printed, it will return a string in the following format: [name=`name`, nrOfLegs=`nrOfLegs`, isMammal=`isMammal`]



### Opgave 2 - level 2

Create a hierarchy of food items in a restaurant menu. Implement a base class called `FoodItem` with properties `name`, `description`, and `price`. 

- Derive two classes `Dessert`, `Appetizer` and `MainCourse` from `FoodItem`. Implement the properties: 
  - `servingSize` for `Appetizer` 
  - `spicinessLevel` for `MainCourse`
  - `isVegan` for `dessert`

- Additionally, implement the method `cook()` for all classes, which print out a message indicating what kind of fooditem is currently being cooked.



### Opgave 3 - level 2

Create a Kotlin class called `BankAccount` with the following properties:

1. `accountNumber`: The account number of the bank account.
2. `balance`: The current balance of the bank account.

- Implement custom getter and setter methods for the `balance` property. The setter should ensure that the balance is always non-negative. If a negative value is attempted to be set, it should be adjusted to 0.



### Opgave 4 - level 2

Create a class named `Student` to represent student information.  Include properties such as `name`, `birthdate`, and `grade`. 

- Implement a custom setter for the `grade` property to ensure that the grade is within a valid range (e.g., 0 to 100).
- Additionally, implement a custom getter for the `age` property to calculate the student's age based on their birthdate, which is passed as a parameter during object construction.



### Opgave 5 - level 2

Create two classes `Mobile` and `RaspberryPi` that implements this interface:

```java
public interface Computer {
    val name: String;
    val price: Int;
  
  	fun printNameAndPrice();
}
```

Create two `Mobile` and two `RaspberryPi` objects



### Opgave 6 - level 3

Create a class `Person`. A person has a cpr number and name

- A person has a private function that calculates the age of the person by their CPR number
- A person has a field: age.
  - The field is public and uses the private function to return a result.
  - The setter is private, as no one from outside should be able to use the function
- The setter for the CPR number should check if the CPR number is valid before setting it. 
