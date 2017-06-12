# What to know

1. APIs - or Application Programming Interfaces - are tools that computers use
to communicate with one another.


###### Change Text with Click Events

```javascript
<script>
  $(document).ready(function() {
    $("#getMessage").on("click", function(){
      // Only change code below this line.
      $(".message").html("Here is the message");
      // Only change code above this line.
    });
  });
</script>
```

###### Get JSON with the jQuery getJSON Method

```javascript

<script>
  $(document).ready(function() {
    $("#getMessage").on("click", function(){
      // Only change code below this line.
        $.getJSON("/json/cats.json", function(json) {
            $(".message").html(JSON.stringify(json));
        });     
    });
  });
</script>

```
###### Convert JSON Data to HTML

The json file:

```JSON
[
{"id":0,"imageLink":"https://s3.amazonaws.com/freecodecamp/funny-cat.jpg","altText":"A white cat wearing a green helmet shaped melon on it's head. ","codeNames":["Juggernaut","Mrs. Wallace","Buttercup"]},

{"id":1,"imageLink":"https://s3.amazonaws.com/freecodecamp/grumpy-cat.jpg","altText":"A white cat with blue eys, looking very grumpy. ","codeNames":["Oscar","Scrooge","Tyrion"]},

{"id":2,"imageLink":"https://s3.amazonaws.com/freecodecamp/mischievous-cat.jpg","altText":"A ginger cat with one eye closed and mouth in a grin-like expression. Looking very mischievous. ","codeNames":["The Doctor","Loki","Joker"]}
]
```

The javascript converting code:

```javascript

<script>
  $(document).ready(function() {

    $("#getMessage").on("click", function() {
      $.getJSON("/json/cats.json", function(json) {

        var html = "";
        // for every array element        
        json.forEach(function(val) {
          // get all the keys in just one array element
          // say "id", "imageLink"...  
          var keys = Object.keys(val);
          html += "<div class = 'cat'>";
          // for each of these keys
          keys.forEach(function(key) {
            // strengthen the keys         // get the key by selecting it
            html += "<strong>" + key + "</strong>: " + val[key] + "<br>";
          });
          html += "</div><br>";
        });
        
        // Only change code above this line.

        $(".message").html(html);

      });
    });
  });
</script>

```

The HTML after the conversion:

```HTML

<div class="col-xs-12 well message">
    <div class="cat">
        <strong>id</strong>
        : 0
        <br>
        <strong>imageLink</strong>
        : https://s3.amazonaws.com/freecodecamp/funny-cat.jpg
        <br>
        <strong>altText</strong>
        : A white cat wearing a green helmet shaped melon on it's head. 
        <br>
        <strong>codeNames</strong>
        : Juggernaut,Mrs. Wallace,Buttercup
        <br>
    </div>
    <br>
    <div class="cat">
        <strong>id</strong>
        : 1
        <br>
        <strong>imageLink</strong>
        : https://s3.amazonaws.com/freecodecamp/grumpy-cat.jpg
        <br>
        <strong>altText</strong>
        : A white cat with blue eys, looking very grumpy. 
        <br>
        <strong>codeNames</strong>
        : Oscar,Scrooge,Tyrion
        <br>
    </div>
    <br>
    <div class="cat">
        <strong>id</strong>
        : 2
        <br>
        <strong>imageLink</strong>
        : https://s3.amazonaws.com/freecodecamp/mischievous-cat.jpg
        <br>
        <strong>altText</strong>
        : A ginger cat with one eye closed and mouth in a grin-like expression. Looking very mischievous. 
        <br>
        <strong>codeNames</strong>
        : The Doctor,Loki,Joker
        <br>
    </div>
    <br>
</div>

```


###### Render Images from Data Sources

```javascript

<script>
  $(document).ready(function() {

    $("#getMessage").on("click", function() {
      $.getJSON("/json/cats.json", function(json) {

        var html = "";

        json.forEach(function(val) {

            html += "<div class = 'cat'>";

            // Only change code below this line.
            html += "<img src = '" + val.imageLink + "' " + "alt='" + val.altText + "'>";
        
          
            // Only change code above this line.

            html += "</div>";

        });

        $(".message").html(html);

      });
    });
  });

</script>

```

###### Prefilter JSON

```javascript
<script>
  $(document).ready(function() {

    $("#getMessage").on("click", function() {
      $.getJSON("/json/cats.json", function(json) {

        var html = "";

        // filter out the cat whose "id" key has a value of 1.
        json = json.filter(function(val) {
          return (val.id !== 1);
        });
        
        json.forEach(function(val) {

          html += "<div class = 'cat'>"

          html += "<img src = '" + val.imageLink + "' " + "alt='" + val.altText + "'>"

          html += "</div>"

        });

        $(".message").html(html);

      });
    });
  });
</script>

```

###### Get Geo-location Data

```javascript

if (navigator.geolocation) {
  navigator.geolocation.getCurrentPosition(function(position) {
    $("#data").html("latitude: " + position.coords.latitude + "<br>longitude: " + position.coords.longitude);
  });
}

```


