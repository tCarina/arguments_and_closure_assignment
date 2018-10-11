# Exercises

1. Create two functions: `double` and `square`.
`double` should take a number and return the number times two.
`square` should take a number and return the number squared.

const double = (num) => {
  return num + num
}

const square = (num) => {
return num * num
}

 * Create a third function `doubleSquare` that uses both of the functions to return a number that is first doubled and then squared.

 const doubleSquare = (num) => {
let dubFirst = double(num);
sqNow = square(dubFirst);
return sqNow }
doubleSquare(3);

2. Create a function `classyGreeting` that takes as input the strings `firstName`  and `lastName`,
and returns a string with a greeting using the two.

  * Create a second function `yell`  that takes string as input and returns the string in all capitalized letters.
  * Create a third function  `yellGreeting`  that will take the `firstName`  and `lastName`  as inputs and yell a greeting using the two.


  const classyGreeting = (...args) =>
  `Hello ${args[0]} ${args[1]} `;
    console.log(classyGreeting("Jon", "Bayne"))


    const classyYell = str => str.toUpperCase();
    console.log(classyYell("dunna dunna batman"))

    const yellGreeting = (...args) => yell(classyGreeting(args))
    console.log("Jon", "Bayne")

    const yellGreeting = (...args) => classyYell(classyGreeting(args[0], args[1]))
    console.log(yellGreeting("Jon", "Bayne"))

3. The [concat](https://www.w3schools.com/jsreF/jsref_concat_array.asp) array method is used to merge two (or more) arrays.
Write a `removeDupes` function that takes an array as an argument and returns a copy without any duplicate elements.
Then, write a function `concatAndRemoveDupes`  that combines two arrays and removes any duplicates.

  _Hint:_ Use the array method `includes`, an object, or a Set. Or the spread operator instead of concat.  

  const removeDupes = (arr) => {
 let output = [];
 let obj = {};
  for(let i = 0; i < arr.length; i< i++){
   if (!obj[arr[i]]) {
     obj[arr[i]] = 1;
     output.push(arr[i]);
      }
    }   
  return output;
  }
console.log(removeDupes(["A", "A", "B", "C", "C", "C", "D", "E", "E"]))
-----------------------------
const joinDupes = (a,b) => {
let c = [...a,...b];

return removeDupes(c);
}
console.log(joinDupes([1,2,3],[3,2,4,5]))

4. Given a list of grades, we can get the median grade by sorting the list and taking the middle element, or the average of the two middle elements.
Create the functions `sort` and `middleElement`, and then use them to create the functions `median`.

const sorted = arr => arr.sort((a,b) => a-b);
const midElem = arr => {
  let mid = Math.floor(arr.length / 2);

  return (arr.length % 2) ? arr[mid]:arr[mid]+arr[mid - 1] / 2
}
midElem([4, 8, 12, 16])
let  grades = [91, 85, 100, 92, 88];
const median = grades => midElem(sorted(grades));
console.log(median(grades));


5. Write a function called `repeat` that takes in a string and numberOfTimes. The function should log to the screen the string however
many times as numberOfTimes. If the user does not enter a numberOfTimes it should default to 2.

const repeat = (str, numTimes = 2) => {
  for(let i = 1; i <= numTimes; i++) {
    console.log(str);
  }
}
repeat("a",3);

6. Using the spread operator, write a function that can take any number of arguments and return the sum of all of them.

const getSum = (...args) => {
 let sum = 0
  for(i = 0; i < args.length; i++){
  sum += args[i]
  }
  return sum
}
console.log(getSum(1,2,3))

7. Write a function called `adder` takes in one number and returns a function that will add that number with another number.
Using `adder` create an `add5` and an `add9` function. Hint: Closures!


const adder = (...arg) => arg[0] += arg[1];
console.log(adder(1,2));
const adds = a => adder(9,5);
console.log(adds(2));
const add9 = b => adder(b, 9);
console.log(add9(9));
  .
