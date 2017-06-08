# Problems

1.  Reverse a String

```javascript
function reverseString(str) {
  return str.split('').reverse().join('');
}
reverseString("hello");
/* 
    split by '' ==> array of characters 
    reverse the whole array
    join the character array by '';

    They are all arrays 
    !!!!
*/

```

2.  Factorialize a Number

```javascript

// Solution 0 Recursion

function factorialize(num) {
  if (num === 0 || num === 1) {
    return 1;
  }
  return num * factorialize(num - 1);
}

factorialize(5);

// Solution 1 WithOut Recursion

function factorialize(num) {
  if (num <= 1) {
    return 1;
  }
  
  var sum = 1;
  while (num >= 2) {
    sum *= num;
    num--;
  }
  return sum;
}

factorialize(5);
```

3.  Check for Palindromes

```javascript
function palindrome(str) {
  // ignore the special cases:
  var strOnlyWord = str.toLowerCase().replace(/[^0-9a-z]/gi, '');
  // reverse it
  var strReversed = strOnlyWord.split('').reverse().join('');
  // check ch by ch
  for (var i = 0; i < strOnlyWord.length ; i++) {   
    if (strOnlyWord[i] !== strReversed[i]) {
      return false;
    } 
  }
  
  return true;
}

palindrome("five|\_/|four");

```

4.  Find the Longest Word in a String

```javascript
function findLongestWord(str) {
  var strArray = str.split(' ');
  var max = 0;
  for (var i = 0; i < strArray.length; i++) {
    var temp = strArray[i].length;
    max = temp > max ? temp : max;
  }
  
  return max;
}

findLongestWord("The quick brown fox jumped over the lazy dog");
```

5.  Title Case a Sentence

Should get comfortable with string manipulation in javascript any time soon

```javascript
function titleCase(str) {
  // convert the string to all lowercase and split them with space["i'm", "a",
  "little"]
  var strArray = str.toLowerCase().split(' ');

  // strArray[0] is a string 
  // strArray[0][0].toUpperCase() convert single letter
  // strArray[0][0].toUpperCase() + strArray[0].slice(1) convert a word with capital letter

  // loop the process and assign it to the ith element in the array
  // The result should be like: strArray = ["I'm", "A", "Little", "Tea", "Pot"]
  for (var i = 0; i < strArray.length; i++) {
    strArray[i] = strArray[i][0].toUpperCase() + strArray[i].slice(1);    
  }
 
  // Join the words back with space
  return strArray.join(' ');
}

titleCase("I'm a little tea pot");
```

6.  Return Largest Numbers in 2D Arrays

```javascript

function largestOfFour(arr) {
  // declare the array just with a pair of empty brackets
  var result = [];
  for (var i = 0; i < arr.length; i++) {
    var singleMax = findMax(arr[i]);
    // Add each max number of a single array to the result
    result.push(singleMax);
  }
  return result;
}

// find the largest number in a single array
function findMax(arr) {
  var max = Number.MIN_VALUE;
  for (var i = 0; i < arr.length; ++i) {
    max = arr[i] > max ? arr[i] : max;
  }
  return max;
}

var arr = [[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]];
largestOfFour(arr);
```

7.  Confirm the Ending Two Strings

```javascript

function confirmEnding(str, target) {
  // get the start index and end index of the substr of str
  var start = str.length - target.length;
  var end = str.length - 1;
  // just make a compare
  return target === str.substr(start, end);
}

confirmEnding("Bastian", "n");

/* 
    The difference between substring(start, end)
    and substr(start, end)
    e.g.
    str = "abcdefg";
    str.substring(1, 3); // bc
    str.substr(1, 3); // bcd
*/
```
8.  Repeat a string repeat a string

```javascript

function repeatStringNumTimes(str, num) {
  var result = "";
  // concatenate the string just by using '+'
  for (var i = 0; i < num; i++) {
    result += str;  
  }
  return result;
}

repeatStringNumTimes("abc", 3);
```

9. Truncate a string

```javascript

function truncateString(str, num) {
  // "hello" --- "6" --- "hello"
  if (str.length <= num) {
    return str.slice(0, num);
  }
  // "hello" --- "4" --- "h..."
  if (num > 3) {
    return str.slice(0, num - 3) + "..."; 
  }
  
  // "hello" --- "2" --- "he..."
  return str.slice(0, num) + "...";
}

truncateString("hello", 2);

```

10. Chunky Monkey

```javascript

function chunkArrayInGroups(arr, size) {
  var result = [];
  for (var i = 0; i < arr.length; i += size) {
    var slice;
    /* 
        If end is greater than the length of the sequence, 
        slice extracts through the end of the sequence (arr.length).
    */
//    if (arr.length - i < size) {
//      slice = arr.slice(i);
//    } else {
    slice = arr.slice(i, i + size);  
//    }
    result.push(slice);
  }
  return result;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);

```

11. Slasher Flick

```javascript

function slasher(arr, howMany) {
  if (howMany >= arr.length) {
    return [];
  }
/* How to use the splice */
//  e.g.
//  myFish.splice(2, 1); remove 1 item at 2-index position (that is, "drum")
  
  arr.splice(0,howMany);
  return arr;
}

slasher([1, 2, 3], 2);

```

12. Mutations

```javascript

function mutation(arr) {
  // should convert to lowercase first
  var dict = arr[0].toLowerCase();
  var note = arr[1].toLowerCase();
  /* e.g.
  'Blue Whale'.indexOf('Blue');     // returns  0
  'Blue Whale'.indexOf('Blute');    // returns -1
  */
  
  // traverse the note and compare every character using indexOf() with the dict
  for (var i = 0; i < note.length; i++) {
    if (dict.indexOf(note[i]) < 0) {
      return false;    
    }
  }
  return true;
  
}

mutation(["Hello", "hey"]);

```

13. Falsy Bouncer

>The double-application of the  ! operator will make the filter callback return true when the value is "truthy" and false when it's "falsy".

>(Your code is calling isNaN() but not passing it a value; that's why that test
didn't work for you. The isNaN() function returns true if its parameter, when coerced to a number, is NaN, and false otherwise.)

>Using the Boolean filter in the second solution would work too as LoremIpsum
notes in another answer, because the built-in Boolean constructor does pretty much the exact same thing as !!.

```javascript

////////////////////////////////
////////// Solution 1 //////////
////////////////////////////////

function bouncer(arr) {
  var clear1 = [];
  var clear2 = [];
  clear1 = arr.filter(function(word){
    return !!word;
});
  return clear1;
}

bouncer([1, null, NaN, 2, undefined]);

////////////////////////////////
////////// Solution 2 //////////
////////////////////////////////

function bouncer(arr) {
  var clear1 = [];
  var clear2 = [];
  clear1 = arr.filter(Boolean);
  return clear1;
}

bouncer([1, null, NaN, 2, undefined]);

```

14. Seek and Destroy

>You can also use the Array.from() method or the spread operator to convert arguments to a real Array:

    var args = Array.from(arguments);
    var args = [...arguments];

```javascript

function destroyer(arr) {
  var args = Array.from(arguments); // [[3, 5, 1, 2, 2], 2, 3, 5]
  for (var i = 1; i < args.length; i++) {
    arr = arr.filter(function(word) { 
      return word !== args[i];
    });
  }
  return arr;
}

destroyer([3, 5, 1, 2, 2], 2, 3, 5);


```

