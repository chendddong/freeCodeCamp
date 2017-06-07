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

