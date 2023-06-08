# Code challenge 3

## Challenge - 3.1: Calculate the average age of a group of people

Instructions:
1. Define an object called "Person" with the following properties:
   - name: a string representing the person's name
   - age: a number representing the person's age

2. Create an array called "people" containing multiple Person objects with different names and ages.

3. Write a function called "calculateAverageAge" that takes the "people" array as input and returns the average age of all the people in the array.

4. Inside the "calculateAverageAge" function, use a loop to iterate over each person in the "people" array and calculate the sum of all the ages.

5. Divide the sum by the total number of people to get the average age.

6. Return the average age as the result.

This challenge will test your understanding of objects, arrays, loops, and functions in JavaScript. Have fun solving it!

## Challenge - 3.2: Library Catalog

Create a library catalog system using objects and functions. The catalog should be able to store information about books and perform various operations on them.

Requirements:
1. Create a function called `Book` that acts as a constructor for book objects. It should take parameters for the title, author, and publication year of the book, and store them as properties of the book object.

2. Create an object called `Library` that acts as a catalog for books. It should have the following properties and methods:
   - `books`: An array to store the book objects.
   - `addBook()`: A method that takes a book object as a parameter and adds it to the catalog.
   - `getBook(title)`: A method that takes a book title as a parameter and returns the book object with the matching title, if it exists in the catalog.
   - `removeBook(title)`: A method that takes a book title as a parameter and removes the book object with the matching title from the catalog, if it exists.
   - `listBooks()`: A method that lists all the books in the catalog.

This challenge allows you to practice creating objects, using constructors, and implementing methods to perform operations on those objects. Feel free to expand upon it or add additional functionality as you see fit. Good luck! 