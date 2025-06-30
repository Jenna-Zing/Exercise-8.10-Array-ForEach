# Exercise-8.10-Array-ForEach

Springboard SE Bootcamp - Array ForEach Exercise for Section 8.10

This exercise has us illustrate the usage of the array method forEach.

# ForEach - introduction

In JavaScript, **arrays** (like your `movies` array) come with a built-in method called `.forEach()`. It goes through each item in the array, **one at a time**, and runs a **callback function** on each item.

Think of it like saying:

> “Hey, JavaScript—go through each item in this array and run this code for it.”

---

# What is callback function?

A **callback function** is just a function you pass **into** another function.

In this case, `.forEach()` is expecting **_you_** to give it a function that it can call on **each item** in the array. That function you give it is called the **callback function**.

---

# What does the callback function get (argument-wise)?

When `.forEach()` runs your callback function, Javascript provides these **three arguments** into it automatically (in this order):

```javascript
function callback(value, index, array) {
  // value: the current item in the array
  // index: the current position (like 0, 1, 2, ...)
  // array: the full array itself
}
```

**_You just choose whether you want to use them or not._**

## Breaking down my code attempt:

```javascript
movies.forEach(function displayMovieInfo(movie) {
  console.log(
    `${movie.title} (${movie.yearReleased}) directed by ${movie.director}`
  );
});
```

1. `movies.forEach(...)`

   I'm telling Javascript: > “Loop through every item in the `movies` array.”

2. `function displayMovieInfo(movie) { ... }`

   This is my **callback function**.

   JavaScript will:

   - Run this function once for each movie object

   - Automatically pass that movie into the **movie** parameter

   So for example:

   - First time: `movie = { title: "Inception", ... }`

   - Second time: `movie = { title: "Interstellar", ... }`

   - And so on...

3. Inside the function:
   You're using **template literals** (the string with backticks and `${}`) to format and print:

   `Title (Year) directed by Director`

   Example output:

   `Inception (2010) directed by Christopher Nolan`

> **EXPLANATION**: Javascript automatically passes the three arguments to the forEach callback function - 1. value, 2. index, and 3. the whole array. My callback function, `displayMovieInfo(movie)` **only uses one parameter**: `movie`.

## Bonus: expanding my solution to use index too (using more forEach callback functions default arguments)

If you wanted to include which number the movie is, you can utilize the second parameter, index, to do so by doing `${index + 1}` since index starts at 0...n-1:

```javascript
movies.forEach(function displayMovieInfo(movie, index) {
  console.log(
    `${index + 1}. ${movie.title} (${movie.yearReleased}) directed by ${
      movie.director
    }`
  );
});
```

Output:

```javascript
1. Inception (2010) directed by Christopher Nolan
2. Interstellar (2014) directed by Christopher Nolan
...
```

## Summary/Recap

| Concept           | What it means                                             |
| ----------------- | --------------------------------------------------------- |
| `.forEach()`      | Runs a function for each item in an array                 |
| Callback function | The function you give to `.forEach()` to run              |
| Parameters        | `value`, `index`, and `array` are passed in automatically |
| You choose        | You only need to include the parameters you want to use   |
