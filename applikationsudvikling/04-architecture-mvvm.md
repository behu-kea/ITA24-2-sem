# Architecture components & MVVM



## Learning goals

- App Architecture
- MVVM architecture
- ViewModels
- UI Layer
- Hoisting



## Preparation

- [MVVM in 100 Seconds](https://youtu.be/-xTqfilaYow?si=KWIuays0YUOqO3Dn)
- [ViewModels & Configuration Changes - Android Basics 2023](https://youtu.be/9sqvBydNJSg?si=Zq2EveH-FIY-VzES)
- [Intro to app architecture](https://youtu.be/AfCzIEwt_i4?si=yoMf_5ABKgzeDMEe)



**(Optional) Reference**

https://developer.android.com/codelabs/basic-android-kotlin-compose-viewmodel-and-state?continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-compose-unit-4-pathway-1%23codelab-https%3A%2F%2Fdeveloper.android.com%2Fcodelabs%2Fbasic-android-kotlin-compose-viewmodel-and-state#0



## Overview

- Talk about 



## How to save state

- [Should You Use Compose State or StateFlow in Your ViewModels?](https://www.youtube.com/watch?v=T8vApYJlW8o)
- [https://chatgpt.com/c/675ae6af-2de8-8008-a841-9b367fce5c80](https://chatgpt.com/c/675ae6af-2de8-8008-a841-9b367fce5c80)





## Exercises



### Opgave 1

For hver arkitektur skriv fordele og ulemper ved de forskellig approaches. De er lavet til en fiktiv todo app. Hvilken en ville i foretrække og hvorfor? Er der ulemper ved at gøre det på den her måde?



**Arkitektur 1**

```
app/
└── src/
    └── main/
        ├── java/
        │   └── com/example/todoapp/
        │       ├── data/
        │       │   ├── model/
        │       │   │   └── Todo.kt
        │       │   ├── repository/
        │       │   │   └── TodoRepository.kt
        │       ├── ui/
        │       │   ├── add/
        │       │   │   ├── AddTodoFragment.kt
        │       │   │   └── AddTodoViewModel.kt
        │       │   ├── list/
        │       │   │   ├── TodoListFragment.kt
        │       │   │   ├── TodoListViewModel.kt
        │       │   │   └── TodoAdapter.kt
        │       │   └── main/
        │       │       └── MainActivity.kt
        │       ├── utils/
        │       │   └── DateUtils.kt
        │       ├── TodoApplication.kt
        │       └── MainActivity.kt
        └── res/
            └── ... (resources)
```



**Arkitektur 2**

```
app/
└── src/
    └── main/
        ├── java/
        │   └── com/example/todoapp/
        │       ├── data/
        │       │   ├── model/
        │       │   │   └── Todo.kt
        │       │   ├── repository/
        │       │   │   └── TodoRepository.kt
        │       ├── ui/
        │       │   ├── add/
        │       │   │   └── AddTodoFragment.kt
        │       │   ├── list/
        │       │   │   ├── TodoListFragment.kt
        │       │   │   └── TodoAdapter.kt
        │       │   ├── main/
        │       │       └── MainActivity.kt
        │       ├── viewmodel/
        │       │   ├── add/
        │       │   │   └── AddTodoViewModel.kt
        │       │   ├── list/
        │       │   │   └── TodoListViewModel.kt
        │       ├── utils/
        │       │   └── DateUtils.kt
        │       ├── TodoApplication.kt
        │       └── MainActivity.kt
        └── res/
            └── ... (resources)
```



Add the following to your projects gradle file dependency: 

```kotlin
implementation("androidx.lifecycle:lifecycle-viewmodel-compose:2.7.0")
```



### Opgave 2 - Todo list app

at lave en todo list app er en af softwareudviklernes Rite of passage og det er der en rigtig god grund til:

- Det er et klassisk eksempel på state (en liste af todo elementer)
- Der er forskellige former for state. 
  - Man kan krydse et element ud
  - Man kan slette det
  - Man kan tilføje et nyt element
- Der skal bruges noget input fra brugeren

Der findes [1000 YouTube videoer](https://www.youtube.com/results?search_query=develop+todolist+app) der viser hvordan man laver sådan en app i alle mulige forskellig programmeringssprog



#### Kravene til appen

- Man skal kunne lave et nyt todo element med en titel og en beskrivelse
- Man skal kunne se todo elementerne
- Man skal kunne se antal elementer man har tilbage (dem der ikke er krydset ud)
- Man skal kunne se antal elementer man har i sin liste
- Man skal kunne slette elementer - *optional*



**Inden** i går igang med at programmere, skal i lave en struktur som den vist ovenfor. I skal tænke over hvordan i vil strukturere jeres arkitektur.



Kl. 11:15 vælger jeg 3 grupper der skal præsentere deres valg. Tænk over hvor jeres Views, view models og models ligger henne. 



Tag udgangspunkt i det her kode: [https://github.com/behu-kea/note-app-mvvm](https://github.com/behu-kea/note-app-mvvm). Start med at dele UI'et op i nogle relevant komponenter

