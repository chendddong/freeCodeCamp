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
