# Exercises

#### **Inheritance**

**A)**

Write a class called `Animal` An `animal` has 3 properties:

- name
- nrOfLegs
- isMammal

Animal has a method: makeSound() that prints the sound of the an-
imal.

- Create 2 animal classes that extends the Animal class and overrides
  the method to produce their unique sound.
- Create a list, add 5 animals to the list and print every animals sound.
- Override the `toString` method such that if an animal object is printed, it will return a string in the following format: [name=`name`, nrOfLegs=`nrOfLegs`, isMammal=`isMammal`]



**B)**

Create a hierarchy of food items in a restaurant menu. Implement a base class called `FoodItem` with properties `name`, `description`, and `price`. 

- Derive two classes `Dessert`, `Appetizer` and `MainCourse` from `FoodItem`. Implement the properties: 
  - `servingSize` for `Appetizer` 
  - `spicinessLevel` for `MainCourse`
  - `isVegan` for `dessert`

- Additionally, implement the method `cook()` for all classes, which print out a message indicating what kind of fooditem is currently being cooked.



#### Access modification

**A)**

- Create a Kotlin class called `BankAccount` with the following properties:

1. `accountNumber`: The account number of the bank account.
2. `balance`: The current balance of the bank account.

- Implement custom getter and setter methods for the `balance` property. The setter should ensure that the balance is always non-negative. If a negative value is attempted to be set, it should be adjusted to 0.

**B)**

- Create a class named `Student` to represent student information. 
- Include properties such as `name`, `birthdate`, and `grade`. 
- Implement a custom setter for the `grade` property to ensure that the grade is within a valid range (e.g., 0 to 100).
- Additionally, implement a custom getter for the `age` property to calculate the student's age based on their birthdate, which is passed as a parameter during object construction.



**C)** **(Advanced Optional)**

- Create a class Person
- A person has a cpr number and name
- A person has a private function that calculates the age of the person by their CPR number
- A person has a field: age.
  - The field is public and uses the private function to return a result.
  - The setter is private, as no one from outside should be able to use the function
