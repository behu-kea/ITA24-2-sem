# Exercises

### Arrays, HashMap & Set

**A)**

- Write a function that takes an array of strings and returns the **<u>indices</u> NOT the number** of the top 2 longest strings of the array.

  - You can assume the array has at least 2 elements.

  - Hint: Could the return type be a data structure?

    

```kotlin
//Printing every index number in an array
  for (i in ints.indices){
      println(i);
  }
```



To solve the following exercises you need to understand how to [read text files](https://www.baeldung.com/kotlin/read-file) 

**B)**

- Write a basic dictionary using a HashMap.
- The keys will represent words and the values will be descriptions of the words



**C)**

1. Create a HashMap named `spaceLog` to store entries in an astronaut's log. [The key will be the date of the entry](https://www.baeldung.com/kotlin/current-date-time), and the value will be a description of the events that occurred on that date (String).
2. Implement the following functions for the space log:
   - `addLogEntry(date: LocalDate, entry: String)`: Adds a new entry to the log with the specified date and description.
   - `updateLogEntry(date: String, newEntry: String)`: Updates an existing log entry with a new description for the specified date.
   - `removeLogEntry(date: String)`: Removes an entry from the log for the specified date.
   - `viewLog()`: Displays all entries in the log, showing the date and corresponding description.
3. Create a main function to test the functionality of the log:
   - Add several entries to the log using the `addLogEntry` function.
   - Update one of the entries using the `updateLogEntry` function.
   - Remove one of the entries using the `removeLogEntry` function.
   - Display the remaining entries using the `viewLog` function.



**D)**

- We have users from 3 different platforms ([users-1, users-2, users-3](https://kea-fronter.itslearning.com/Resources?FolderID=1235819&PlayPlanDialogView=False&ReloadTree=False) 
- We want to know:
  - What users are identical across all platforms
  - What users are only specific to each platform.



**Advanced (Optional)**

We want to analyse [The republic by Plato.](https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1235821)

- How many times does each word occur?
  - Plato, PlAtO and plato should all count as the same word
- What are the top 10 words that are not in the top 10 of [conjuctions](https://www.grammar-monster.com/lists/list_of_conjunctions.htm)



### Comparable

**A)**

- Write a class student
- A student has the following fields:
  - Name
  - Email
  - Age
  - Subjects : list
- Implement the comparable interface such that students can be sorted by age
  - Improve the solution such that if students are the same age, they are sorted by amount of subjects
  - I.E A student with the same age as another student is rated "higher" if the have more subjects



**B)**

1. Create a data class named `Book` with the following properties:
   - `title`: The title of the book.
   - `author`: The author of the book.
   - `isbn`: The ISBN (International Standard Book Number) of the book.
   - `price`: The price of the book.
2. Implement a class called `Bookstore` with the following methods:
   - `addBook(book: Book)`: Adds a book to the inventory.
   - `removeBook(isbn: String)`: Removes a book from the inventory based on its ISBN.
   - `searchBookByTitle(title: String): Book?`: Searches for a book in the inventory by its title and returns the book if found, otherwise returns null.
   - `displayInventory()`: Displays all books in the inventory.
3. Create a main function to test the functionality of the `Bookstore` class:
   - Instantiate a `Bookstore` object.
   - Add a few sample books to the inventory.
   - Test adding, removing, searching for, and displaying books in the inventory.



**D)**

- Write a method called `smallWordFilter` that, given a non-`null` `String` (not list!) containing words separated by single spaces (`" "`), returns all the words in the original `String` that are 3 characters or shorter in the same order in which they appeared in the original `String`, as a `List<String>`.

- For example, given the input "Xyz is the very best cat" you would return the `List<String>` containing `{"Xyz", "is", "the", "cat"}`. We have skipped both "very" and "best" because they are longer than 3 characters.

From: https://www.learncs.online/practice/kotlin/small-word-filter-with-list/challen@illinois.edu?returnTo=lists

Hint: https://kotlinandroid.org/kotlin/kotlin-split-string/

**Advanced (Optional)**

(This question was asked by microsoft for a coding interview)

Given a string and a pattern, find the starting indices of all occurrences of the pattern in the string. For example, given the string "abracadabra" and the pattern "abr", you should return `[0, 7]`.
