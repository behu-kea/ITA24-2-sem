# Interfaces & abstract



## Preparation

- [Learn Kotlin for Android: Abstract Classes & Functions (Lesson 19)](https://www.youtube.com/watch?v=_KoBfDb4Gtw)
- [Learn Kotlin for Android: Interfaces (Lesson 20)](https://www.youtube.com/watch?v=RctW18zpgec)



Optional

- https://kotlinlang.org/docs/interfaces.html



<!--

## After class considerations

- Bedre forbered Streamingtjeneste. Det var lidt messy.
- Det er svært at kende forskel

-->



## Overview

- https://aicolors.co/
- Snak om konteksten for hvorfor vi skal lære om interfaces og abstract
- Go through some examples and discuss if we should use inheritance, abstract, contract, just classes



### Streamingtjeneste

Design et system for en streamingtjeneste, lignende Netflix, der håndterer medieindhold og brugerabonnementer



#### Indholdshåndtering
Administrer forskellige typer medieindhold såsom film, serie og dokumentar



#### Abonnementstyper
Håndter forskellige abonnementstyper (fx basis, standard, premium) med varierende adgangsniveauer og funktioner, såsom antal skærme, HD/UHD-adgang. 



#### Indholdsbibliotek
Skab et system, der effektivt kan søge og filtrere indhold baseret på genre, udgivelsesår, popularitet osv. 



## Peer instruction



### Question 1

What kind of error does the follwing code produce?

```java
interface UserInterface {
    var name: String
    var email: String

    fun displayUserInfo()
    fun updateEmail(newEmail: String)
}


class User(override var name: String, override var email: String) : UserInterface {
    override fun displayUserInfo() {
        println("User Name: $name")
        println("User Email: $email")
    }

    override fun updateEmail(newEmail: String) {
        email = newEmail
        println("Email updated to: $email")
        return newEmail
    }
}
```

1.  Wrong assignment in `updateEmail`
2.  `updateEmail` incorrectly returns a value
3.  `displayUserInfo` prints incorrect information 
4.  `User` does not override `displayUserInfo` properly



### Question 2 - 2 minutter

What happens when `camilla.sayHi();` is called?

```java
package interfaces

interface PersonInterface {
    fun sayHi();
    val age: Int;
    val name: String;
}

class Person(override val name: String, override val age: Int) : PersonInterface {
    override fun sayHi() {
        println("Hi, I'm $name!")
    }
}

fun main() {
    val camilla = Person("Camilla", 6)
    camilla.sayHi()
}

```

- `null`
- 6
- Syntax error
- None of the above



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



### Abstract

An abstract class is a class that cannot be instantiated. The classic example of an abstract class is an animal. An `Animal` is an abstract concept (it is not a elephant or mouse or dog which are specific animals) therefore it does not make sense to instantiate an `Animal`

```kotlin
abstract class Animal {
    abstract val name: String;
    abstract val size: Double;
    abstract fun makeSound();
}

class Elephant(
    override val name: String,
    override val size: Double
) : Animal() {
    override fun makeSound() {
        println("asd");
    }
}

fun main() {
  // This will not work!!! We cannot instantiate or create an object of a Abstract class!
  val Dog: Animal = Animal("Perter the elephant", 1000.0); // Error
  // But we can do this:
  val Elephant: Elephant = Elephant("Perter the elephant", 1000.0);
}
```



## Exercises



### Computer

Create two classes `Mobile` and `RaspberryPi` that implements this interface:

```java
public interface Computer {
    val name: String;
    val price: Int;
  
  	fun printNameAndPrice();
}
```

Create two `Mobile` and two `RaspberryPi` objects



### Instagram like service

We need to create functionality for an Instagram-like Service.



#### Social Media Content

Design a system to manage social media content for a platform that supports different types of posts, such as text posts, photo posts, and video posts. Each type of post shares common properties like a caption, uploader (the user who posted it), and the timestamp of when it was posted. Additionally, each post type can have unique properties and behaviors:

- **Common Post Features**: Every post, irrespective of its type, should allow operations to get the number of likes it has received and support like/dislike actions.

- **Text Post**: A simple post containing text content.
- **Photo Post**: A post that includes a photo along with the common features. It may have additional properties like photo resolution, filters applied, etc.
- **Video Post**: Similar to a photo post but contains a video. It could have properties like video length, resolution, etc.



#### Content Management System (CMS)
A Content Management System (CMS) should be designed to manage the different types of posts. The CMS should allow:
- Adding new posts to the collection.
- Searching for posts using criteria such as caption, uploader, or post type.
- Retrieving the top N most liked posts across all types.



### 📝 Exercise 5 - study groups - teachers and students - after the break at 10:15

Duration: 20 min

In the following exercise one group will randomly be selected to be teachers and the other group will be students

In groups of two people prepare a small 5 minute lecture. The lecture should explain the topic of difference between abstract and interface any way you like. That might be with a small slideshow or it might be with code, thats up to you. 

- As teachers present the 5 minute lecture
- As students ask good interesting questions



After you have created the presentation it should be presented for each other



### I må gerne arbejde på næste aflevering



### Internet profile - Level 1

https://developer.android.com/codelabs/basic-android-kotlin-compose-kotlin-fundamentals-practice-problems#5



### Last 8 - Level 2

https://www.learncs.online/practice/kotlin/last-8/challen@illinois.edu?returnTo=encapsulation



### Inheritance

https://www.learncs.online/practice/kotlin/simple-person-inheritance/challen@illinois.edu



### Chat-GPT opgave

Hop ind på [https://chat.openai.com/chat](https://chat.openai.com/chat) og lav en konto. Det er ikke obligatorisk! Hvis i ikke vil kan i bare bruge opgaven der er lidt længere nede

Brug den her prompt til at lave en interface opgave der er tailored til et emne i synes er sjovt



#### Prompt

```
Act as an experienced lecturer with many years of experience in creating fun and easy to understand exercises for students

Create a fun, easy to understand, short and interesting exercise for students. The exercise should learn the students how to use a kotlin interface. 

The exercise should fit the students interests. Here are the student interests: COMMA_SEPERATED_INTERESTS
```



### Eksempel på opgave om Hip-hop: Hip-Hop Playlist Interface in Kotlin

#### Objective:

Implement a Kotlin interface to manage a hip-hop music playlist.

#### Background:

Interfaces in Kotlin are used to define a contract that a class needs to conform to, without providing the actual implementation of the methods. It's a way to achieve abstraction and is essential in designing robust and scalable software systems.

#### Task:

Create a Kotlin interface named `HipHopPlaylist` that includes the following methods:

1. `addSong(songName: String, artist: String)`: Adds a new song to the playlist.
2. `removeSong(songName: String)`: Removes a song from the playlist.
3. `getCurrentSongs()`: Returns a list of current songs in the playlist.

#### Implementation:

1. Define the `HipHopPlaylist` interface with the methods mentioned above.
2. Create a class `MyPlaylist` that implements `HipHopPlaylist`. Use a mutable list to store the songs.
3. Each song can be a Pair of `songName` and `artist`.
4. Implement all the methods in `MyPlaylist` class.
5. In the main function, create an instance of `MyPlaylist` and demonstrate adding, removing, and listing songs.

#### Sample Output:

- Adding songs like "Lose Yourself" by Eminem, "Juicy" by Notorious B.I.G.
- Display the current playlist.
- Remove a song and show the updated playlist.

#### Challenge:

- Enhance the `HipHopPlaylist` interface with a method `findSong(artist: String)` to find all songs by a specific artist.
- Implement this method in the `MyPlaylist` class.

This exercise will help students understand the concept of interfaces in Kotlin and how they can be used to design a system, while also engaging their interest in hip-hop music.

