# Kotlin learning

[https://kotlinlang.org/docs/home.html](https://kotlinlang.org/docs/home.html)

`val` is like const

`var` is like let



## Loops

Can be done like this

```kotlin
for (i in 0..5) {
    println(i) // 0,1,2,3,4,5   --> upto 5
}
```



## Collections

Array is a part of collections. 

```kotlin
// static number of elements
var names = ListOf("asd", "asd2");
names.add("asdss"); // Error!

// Now it can be changed
var names2 = MutableListOf("asd", "asd2");
names.add("asdss"); 
```



## Classes

`val` property is read only

`var` property is read and write



Can create custom getters like this:



```kotlin
val area: Int // property type is optional since it can be inferred from the getter's return type
	get() = this.width * this.height
```



Or like this

```kotlin
val area get() = this.width * this.height
```



Or custom setters like this

```kotlin
var test = 0
  set(value) { field = 30};
```

Called when the property is set like fx `rectangle.test = 10;`



### Visibility modifiers

```kotlin
open class Outer {
    private val a = 1
    protected open val b = 2
    internal open val c = 3
    val d = 4  // public by default

    protected class Nested {
        public val e: Int = 5
    }
}
```





## What i dont understand



### Nullable

val b: Int = 10000
println(b == b) // Prints 'true'
val boxedB: Int? = b
val anotherBoxedB: Int? = b
println(boxedB == anotherBoxedB) // Prints 'true'



### Unsigned integer types



### Sequences



### MutableList

```kotlin
 MutableList<Person> = mutableListOf()
```

```kotlin
val test = mutableMapOf<String, Int>();
test.put("price1", 10);
```





### Class constructors fully

Something with a primary and a secondary



### Lambda







## This is cool

```kotlin
when (x) {
    in 1..10 -> print("x is in the range")
    in validNumbers -> print("x is valid")
    !in 10..20 -> print("x is outside the range")
    else -> print("none of the above")
}
```





## Sorting and searching



### Sorting

- Nævn nogle almindelige sorteringsalgoritmer, og beskriv deres tidskompleksitet.

- Forklar, hvordan en **QuickSort** fungerer, og analyser dens tidskompleksitet i bedste og værste tilfælde.
- Hvordan fungerer MergeSort, og hvorfor er den mere effektiv end BubbleSort?
- Hvorfor bruges ofte **Heapsort** eller **Quicksort** i praksis frem for BubbleSort eller InsertionSort?
- Hvordan kan man forbedre en simpel sorteringsalgoritme som BubbleSort?
- Hvorfor bruger man ikke altid **Counting Sort** selvom den har O(n) kompleksitet?
- Hvilke sorteringsalgoritmer er rekursive, og hvilke er iterative?



- What does it mean for a sorting algorithm to be “stable”?
- In Big-O notation, how would you compare the average and worst-case time complexities of MergeSort, QuickSort, and BubbleSort?
- Can you describe the merge process in MergeSort? How does merging sorted sublists work?
- How do Insertion Sort and Selection Sort differ in terms of their approach and performance characteristics?
- How do the space requirements compare for MergeSort, QuickSort (using in-place partitioning), and Counting Sort?





Merge sort, quickSSort and bubblesort



### BubbleSort

Most popular. Switches place if two elements are in the wrong order. 

Has  O(n<sup>2</sup>)  time complexity worst. O(n) best 



### Selection Sort

For each position in the list: Finds the smallest value and swaps it to the current position of the array. 

Selection sort works by finding the minimum element in an unsorted  portion of the array and placing it at the beginning, then repeating  this for the remaining elements.



#### Time complexity

We have to first find the smallest element for the first position O(n). But we have to do it for all positions in the array O(n<sup>2</sup>) 



### Insertion sort

[Good explanation](https://www.youtube.com/watch?v=O0VbBkUvriI&t=41s)

Insertion sort is a simple sorting algorithm that works by iteratively inserting each element of an unsorted list into its correct position in a sorted portion of the list. It is like sorting playing cards in your hands.

![Insertion-sorting](assets/Insertion-sorting.png)

We only have to move forward in the array. 

We move specific portions of the array over in order to put the newest unsorted array into the correct position in the array. 



#### Time complexity

O(n<sup>2</sup>) worst. We have to go through each element in the list. But wa also have to shift all the elements in the sorted position.



Best O(n). If all elements are sorted. We only have to run through the array. 



### MergeSort

Divide and conquer





### QuickSort





### 
