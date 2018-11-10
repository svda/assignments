/**
 * Question 1
 * 
 * Write the function "createBase" that allows
 * the following
 */

const addSix = createBase(6);
console.log(addSix(10)); // => 16
console.log(addSix(21)); // => 27

/**
 * Question 2
 * 
 * Implement the "counter" function
 */
const c = counter();
c.add(5);
c.add(9);
console.log(c.retrieve()); // => 14

/**
 * Question 3
 * 
 * Rewrite the inner code of the 
 * "doSomethingAsync" function below so that the 
 * calls "a" and "b" don't have to wait on eachother
 */

function timeout(x) {
    return new Promise(resolve => setTimeout(() => resolve(x), 1000));
}

const doSomethingAsync = async () => {
    const a = await timeout('a');
    const b = await timeout('b');
    console.log('done', a, b);
};

/**
 * Question 4
 * 
 * Fix the for loop below so that "i" will log the right value
 * to the console
 */

for (var i = 0; i < 5; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000);
}

```
for (var i = 0; i < 5; i++) {
    setTimeout(
      (function(j) {
        return function() {
            console.log(j);
            }})(i), 1000);
}
```

/**
 * Question 5
 * 
 * Why does this below evaluate to false?
 */
console.log({ name: 'henk' } == { name: 'henk' })

/**
 * Question 6
 * 
 * A: How would you calculate the sum of the array below?
 * B: How would you increase the value of every number by 5?
 */
const myArrayOfNumbers = [2, 3, 5, 10];

/**
 * Question 7
 * 
 * Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.
 */

moveZeros([false,1,0,1,2,0,1,3,"a"]) // returns[false,1,1,2,1,3,"a",0,0]

/**
 * Question 8

    Write a function, which takes a non-negative integer (seconds) as input and returns the time in a human-readable format (HH:MM:SS)

    HH = hours, padded to 2 digits, range: 00 - 99
    MM = minutes, padded to 2 digits, range: 00 - 59
    SS = seconds, padded to 2 digits, range: 00 - 59
    NOTE: The maximum time never exceeds 359999 (99:59:59)
 */

humanReadable(0) // returns 00:00:00
humanReadable(60) // returns 00:01:00
humanReadable(86399) // returns 23:59:59
