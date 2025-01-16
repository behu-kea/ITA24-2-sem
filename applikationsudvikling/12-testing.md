# Testing



## Overview

- MVP aflevering på søndag
  
- Learning from Shape visit
  
- Mandag grimmeste app (Chindoku design filosofi)
  
- Talk about testing
  - Unit tests
  - Ui tests

- Lav nogle UI tests for notes appen
- Lav nogle UI tests for jeres MVP
- Jeg giver feedforward på jeres MVP



## Preparation

- [https://developer.android.com/jetpack/compose/testing](https://developer.android.com/jetpack/compose/testing) (se video læs om Semantics, Setup og Testing APIs)
- [Writing Our First Unit Tests - Testing on Android - Part 3](https://youtu.be/W0ag98EDhGc?si=3lCv9r2_EFXq3tAL)



Three types of tests:

1. Unit tests - single units. Fx function `getSum` 
2. Integration tests - How two components work together. Interaction betwen components
3. UI tests/end-to-end - Whole interaction. Log in, then click a button etc



TDD - Test driven development. Write tests first. Then start developing code. Could maybe be huge in the age of AI



### Testing folders

`androidtest` vs `test` folder

`androidtest` - Everything that runs on the emulator or need some android context

`test` - Everything else. Fx testing a `getSum` function does not need android



## Unit test

In a unit test we test that sum function works as expected. In the following example we have two tests: 

1. One where we check that an addition works
2. One where we check a sum function we have created

```kotlin
fun getSum(list: List<Int>): Int {
    return list.sum()
}

class ExampleUnitTest {
    @Test
    fun `Addition works`() {
        assertEquals(4, 2 + 2);
    }

    @Test
    fun `Sum function works`() {
        val list = listOf(1, 2, 3);
        val sum = getSum(list);
        assertEquals(6, sum);
    }
}
```

For each test we add the `@Test` annotation followed by a function with the thing we want to test. To test something we use the `assertEquals` function. The first argument is what we expected, the next is the actual result. With this line: `assertEquals(6, sum);` we say that we expect the value of the `sum` variable to be 6



### `@Before` and `@After`

If we want some code to run before each test is run

```kotlin
@Before
fun setup() {
	// do something here
}
```



After is usually meant to destroy objects or close database connections

```kotlin
@After
fun teardown() {
	// do something here
}
```



## UI tests

These are teste that test the ui more than the functionality. That means we write code that clicks buttons, writes text in input fields and check if the right elements are on the page



To create a UI test we must first create a rule that we can use to interact with our app

```kotlin
@get: Rule
val rule = createComposeRule()
```

you could say that `rule` is kind of like `document` in javascript. With the `document` we can get elements, click and set text in input fields. 



### Create a test

To create a test write the `@Test` annotation before a function. This function will now be part of your tests. 

First we have to specify what content we are testing. We can test the full application, but we can alos just test a `@Composable`. 

```kotlin
rule.setContent { AppNavigation(notesViewModel); }
```

`AppNavigation(notesViewModel)` is a `Composable`



#### Getting a node

When we have defined the content we need to start selecting some elements. In javascript we did this with `document.querySelector` . Using a `rule` we do that with `rule.onNodeWithText("Add new note")`. Here we get a node that has the text `Add new note`. 



We can also select a node anothe way like this:

```kotlin
rule.onNode(
	hasText("Add new note")
	and
	hasClickAction()
)
```



We can also use tags like this

```kotlin
Button(
    onClick = { /* Do something */ },
    modifier = Modifier.testTag("myButtonTag")
) {
    Text("Click Me")
}
```



```kotlin
val buttonTag = composeTestRule.onNodeWithTag("myButtonTag")
```



#### Create some action

When we have a node, we can create an action on that note, fx click it, write text in the node etc.

Here we click a node

```kotlin
rule.onNodeWithText("Add new note")
	.performClick()
```



Here we write some text in a node

```kotlin
rule.onNodeWithText("Title")
	.performTextInput("olol")
```



#### Check stuff

Now we can check if some node was created with our action:

```kotlin
rule.onNodeWithText("olol")
	.assertExists()
```



#### Full example

Here is an example of a test that tests that creating a new node works as expected

```kotlin
@Test
fun addNote() {
    rule.setContent { AppNavigation(notesViewModel); }

    rule.onNodeWithText("Add new note")
        .performClick()

    rule.onNodeWithText("Title")
        .performTextInput("olol")

    rule.onNodeWithText("Content")
        .performTextInput("olol1")

    rule.onNodeWithText("Save note")
        .performClick()

    rule.onNodeWithText("olol")
        .assertExists()
}
```



Read more about UI testing in compose here: [https://developer.android.com/jetpack/compose/testing](https://developer.android.com/jetpack/compose/testing)



## Exercises



## Notes app

For the notes app we were working on last time, lets write some tests for that app. The repo can be found [here](https://github.com/behu-kea/ita-23-2-sem-code/tree/for-testing-lecture/noteapp) with all features implemented. We will be focusing on UI tests



### UI tests

You have to write some ui tests that test the following:

- Clicking on a note in the overview will take you to the right note
- When creating a new note that note will show up in the overview
- When searching for a note the correct notes will be shown in the overview
- Deleting a note will delete it from the overview



## UI tests for jeres tværfaglige projekt

Lav nogle UI tests for jeres app, der tester de vigtigste dele af jeres app



## Fastforward til jeres MVP

Jeg kommer til at sidde klar til at give jer feedback på jeres MVP



<!--

```
class UiTester {
    @get: Rule
    val rule = createComposeRule()

    val notesViewModel: NotesViewModel = NotesViewModel()

    @Test
    fun addNote() {
        rule.setContent { AppNavigation(notesViewModel); }

        rule.onNodeWithText("Add new note")
            .performClick()

        rule.onNodeWithText("Title")
            .performTextInput("olol")

        rule.onNodeWithText("Content")
            .performTextInput("olol1")

        rule.onNodeWithText("Save note")
            .performClick()

        rule.onAllNodesWithText("olol")
            .get(0).assertExists()
    }
}
```

-->
