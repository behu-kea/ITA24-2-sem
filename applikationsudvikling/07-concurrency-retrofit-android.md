# Async with coroutines & retrofit



## Learning goals

- Coroutines
  - `suspend`
  - `runBlocking`
  - `lifecycleScope.launch`
  - `CoroutineScope(Dispatchers.Main).launch {`
- Repository pattern



## Preparation

- [WHY: Co-Routines](https://youtu.be/ne6CD1ZhAI0?si=0WWltvIn1skCfkV9)
- [WHAT: Co-Routines](https://youtu.be/ShNhJ3wMpvQ?si=cXQfE2A6wYuoxt2v)
- [HOW: Co-Routines](https://youtu.be/kvfpuzSwVZ8?si=6khS1C1za8mts_a3)
- [Retrofit Co-routines](https://youtu.be/S-10lLA0nbk?si=YT9YQvK6TIWsiw6O)
- Mangler noget med repository pattern her. Suspend funktion sov


(Optional) Documentation
[https://developer.android.com/kotlin/coroutines](https://developer.android.com/kotlin/coroutines)



## Overview

- Concurrency slides
- Opgaver
- Students teachers



## Topics



### Coroutines



```
lifecycleScope.launch {
```



#### Repository pattern

Here is a simple repository pattern:

```kotlin
data class User(val id: Long, val name: String, val email: String)

interface UserRepository {
    fun getUserById(id: Long): User?
    fun getAllUsers(): List<User>
    fun addUser(user: User)
    fun removeUser(user: User)
}

class UserRepositoryImpl : UserRepository {
    private val users = mutableListOf<User>()

    override fun getUserById(id: Long): User? {
        return users.find { it.id == id }
    }

    override fun getAllUsers(): List<User> {
        return users.toList()
    }

    override fun addUser(user: User) {
        users.add(user)
    }

    override fun removeUser(user: User) {
        users.remove(user)
    }
}

fun main() {
    val userRepository: UserRepository = UserRepositoryImpl()

    val user1 = User(1, "John Doe", "john.doe@example.com")
    val user2 = User(2, "Jane Doe", "jane.doe@example.com")

    userRepository.addUser(user1)
    userRepository.addUser(user2)

    println("All users:")
    userRepository.getAllUsers().forEach { println(it) }

    println("User with ID 1: ${userRepository.getUserById(1)}")
}
```





## Opgaver



### Opgave 1 - Timer app

1. Lav en timer der venter 5 sekunder før den viser konfetti. Gør det både med blocking og ikke blocking. Brug `lifecycleScope.launch`, `runblocking` og `delay` funktionen

2. Gør sådan at en bruger kan skrive hvor lang tid der skal ventes før Konfetti skal vises. Når brugeren klikker på en knap skal der gå den tid brugeren har sagt der skal ventes før konfettien kommer



[Her er starterkoden](https://github.com/behu-kea/konfetti-android) til at få konfetti når man klikker på en knap. Hvad er forskellen mellem blocking og ikke blocking?



### Opgaver 2 - Tænk over din arkitektur

Resturkturer din [https://reqres.in/](https://reqres.in/) app så den følger **repository pattern**, men også disse patterns:

- MVVM
- Stateless komponenter

Det skal gøres med `suspend` funktioner inde i repoet.



### Opgave 3 - Teachers students

Duration: 30 min

In the following exercise one group will randomly be selected to be teachers and the other group will be students

In groups of two people prepare a small 5 minute lecture. The lecture should explain the topic of **Coroutines and repository patters** any way you like. That might be with a small slideshow or it might be with code, thats up to you. 

- As teachers present the 5 minute lecture
- As students ask good interesting questions



### Opgave 4 - Arbejd videre på din GenAI app

Arbejd videre med din GenAI app. Fokuser på repository pattern og suspend funktioner