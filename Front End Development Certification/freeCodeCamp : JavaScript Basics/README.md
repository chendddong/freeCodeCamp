# Some Good Points

1. Nesting For Loops
    ```javascript
    var arr = [[1,2], [3,4], [5,6]];
    for (var i=0; i < arr.length; i++) {
      for (var j=0; j < arr[i].length; j++) {
        console.log(arr[i][j]);
      }
    }
    ```

2. Profile Lookup
    ```javascript
    //Setup
    var contacts = [
        {
            "firstName": "Akira",
            "lastName": "Laine",
            "number": "0543236543",
            "likes": ["Pizza", "Coding", "Brownie Points"]
        },
        {
            "firstName": "Harry",
            "lastName": "Potter",
            "number": "0994372684",
            "likes": ["Hogwarts", "Magic", "Hagrid"]
        },
        {
            "firstName": "Sherlock",
            "lastName": "Holmes",
            "number": "0487345643",
            "likes": ["Intriguing Cases", "Violin"]
        },
        {
            "firstName": "Kristian",
            "lastName": "Vos",
            "number": "unknown",
            "likes": ["Javascript", "Gaming", "Foxes"]
        }
    ];


    function lookUpProfile(firstName, prop){
    // Only change code below this line
      var result = "";
      
      if (firstName === "Akira" || firstName === "Harry" ||
          firstName === "Sherlock" || firstName === "Kristian") {
        
        var index;
        if (firstName === "Akira") {index = 0;}
        if (firstName === "Harry") {index = 1;}
        if (firstName === "Sherlock") {index = 2;}
        if (firstName === "Kristian") {index = 3;}
        
        if (contacts[index][prop]) {
          return contacts[index][prop];
        } else {
          return "No such property";
        }
        
      } else {
        return "No such contact";
      }
      
      
    // Only change code above this line
    }

    // Change these values to test your function
    lookUpProfile("Akira", "likes");
    ```
3. Generate Random Whole Numbers
    ```javascript
    var randomNumberBetween0and19 = Math.floor(Math.random() * 20);

    function randomWholeNum() {

      // Only change code below this line.
      

      return Math.floor(Math.random() * 10);
    }
    ```
4. Generate Random Whole Numbers within a Range
    ```javascript
    // Example
    function ourRandomRange(ourMin, ourMax) {

      return Math.floor(Math.random() * (ourMax - ourMin + 1)) + ourMin;
    }

    ourRandomRange(1, 9);

    // Only change code below this line.

    function randomRange(myMin, myMax) {

      return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin; // Change this line

    }

    // Change these values to test your function
    var myRandom = randomRange(5, 15);
    ```
5. Sift through Text with Regular Expressions

    Regular expressions are used to find certain words or patterns inside of strings.
    For example, if we wanted to find the word the in the string The dog chased
    the cat, we could use the following regular expression: /the/gi
    Let's break this down a bit:
    / is the start of the regular expression.
    the is the pattern we want to match.
    / is the end of the regular expression.
    g means global, which causes the pattern to return all matches in the string, not just the first one.
    i means that we want to ignore the case (uppercase or lowercase) when searching for the pattern.
    Instructions
    Select all the occurrences of the word and in testString.
    You can do this by replacing the . part of the regular expression with the word and.

    ```javascript
    // Setup
    var testString = "Ada Lovelace and Charles Babbage designed the first computer and the software that would have run on it.";

    // Example
    var expressionToGetSoftware = /software/gi;
    var softwareCount = testString.match(expressionToGetSoftware).length;
      

    // Only change code below this line.

    var expression = /and/gi;  // Change this Line

    // Only change code above this line

    // This code counts the matches of expression in testString
    var andCount = testString.match(expression).length;
    ```

6. Find Numbers with Regular Expressions

    We can use special selectors in Regular Expressions to select a particular type of value.

    One such selector is the digit selector \d which is used to retrieve one digit (e.g. numbers 0 to 9) in a string.

    In JavaScript, it is used like this: /\d/g.

    Appending a plus sign (+) after the selector, e.g. /\d+/g, allows this regular expression to match one or more digits.

    The trailing g is short for 'global', which allows this regular expression to find all matches rather than stop at the first match.

    Instructions
    Use the \d selector to select the number of numbers in the string, allowing for the possibility of one or more digit.

    ```javascript

    // Setup
    var testString = "There are 3 cats but 4 dogs.";

    // Only change code below this line.

    var expression = /\d+/g;  // Change this line

    // Only change code above this line

    // This code counts the matches of expression in testString
    var digitCount = testString.match(expression).length;

    ```

7.  Find Whitespace with Regular Expressions

    We can also use regular expression selectors like \s to find whitespace in a string.

    The whitespace characters are " " (space), \r (the carriage return), \n (newline), \t (tab), and \f (the form feed).

    The whitespace regular expression looks like this:

    /\s+/g

    Instructions
    Use \s to select all the whitespace characters in the sentence string.

    ```javascript
    // Setup
    var testString = "How many spaces are there in this sentence?";

    // Only change code below this line.

    var expression = /\s+/g;  // Change this line

    // Only change code above this line

    // This code counts the matches of expression in testString
    var spaceCount = testString.match(expression).length;
    ```

8.  Invert Regular Expression Matches with JavaScript

    You can invert any match by using the uppercase version of the regular expression selector.

    For example, \s will match any whitespace, and \S will match anything that isn't whitespace.

    Instructions
    Use /\S/g to count the number of non-whitespace characters in testString.

    ```javascript
    // Setup
    var testString = "How many non-space characters are there in this sentence?";

    // Only change code below this line.

    var expression = /\S/g;  // Change this line

    // Only change code above this line

    // This code counts the matches of expression in testString
    var nonSpaceCount = testString.match(expression).length;
    ```
