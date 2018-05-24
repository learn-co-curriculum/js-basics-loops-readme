# JavaScript Loops

## Objectives
1. Give an overview of the different options available for loops in JavaScript
2. Explain the uses of each type of loop

Loops are a common function in programming. Though the syntax varies for each language, the concept is the same. JavaScript has a number of loops that you can leverage, depending on what is trying to be achieved with the function.

With loops, we can iterate over datasets and manipulate the data. For example, let's assume we have a list of the Billboad 100's top 100 songs and artists in descending rank order from an API endpoint. We're only going to use 10 in these static examples, because 100 is a lot! 

In some loops, we must initialize a variable. The variable `i` in the following examples will be our initialization statement. This is a commonly defined variable that can be incremented over each iteration of the loop. This variable can be defined as anything--such as "j", "x", "y", or even "sasquatch" and "bananas", if using more semantic language is beneficial to your style of writing code.

Loops will continue to run until the conditions are met. Fore example, the conditional statement of `i < 10` will be evaluated on each iteration of the loop. If the condition is `true`, the loop will continue. If the condition is `false`, for example, if `i` is now greater-than or equal to 5 after running the loop 4 times, the loop will not execute.

### The `while` loop
---
The `while` loop is a pretty basic loop that is available in other programming languages as well. The loop will continue to be executed so long as the condition is true. In the below example, the variable `i` starts at 0, and will continue to increment until `i` is no longer less than 5. This loop will _start_ with 0, print the statement to the console, then increment the value of `i`. It will continue to 1, 2, 3, and so on, so the loop will run 5 times. Make _sure_ that the block contains code that will either break the loop, or change the condition so that it will eventually evaluate to false. Without this, an infinite loop will be created and this block will never stop executing!

This example demonstrates what happens during the `while` loop. Since arrays start with an `index` of `0`, we are incrementing it by 1 in each string, so that the ranking of each entry is synced properly. We'll also print out what the current value of `i` is before it is displayed.

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be - Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande", "Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

var i = 0
while (i < billboard100.length) {
  console.log(i)
  console.log("The #" + (i+1) + " record is " + billboard100[i] );
  i++; //this is necessary to avoid an infinite loop
}
```
**Output**
```
0
The #1 record is This Is America - Childish Gambino
1
The #2 record is Nice For What - Drake
2
The #3 record is God's Plan - Drake
3
The #4 record is Psycho - Post Malone Featuring Ty Dolla $ign
4
The #5 record is Meant To Be - Bebe Rexha & Florida Georgia Line
5
The #6 record is The Middle - Zedd, Maren Morris & Grey
6
10 The #7 record is No Tears Left To Cry - Ariana Grande
7
The #8 record is Look Alive - BlocBoy JB Featuring Drake
8
The #9 record is Never Be The Same - Camila Cabello
9
The #10 record is Perfect - Ed Sheeran
//the loop will stop here because i is no longer less than 10
```

### The `do...while` loop
The `do...while` loop is similar to `while`, as in it will execute a block of code based on a condition or set of conditions. It will execute at least once, and continue to execute if the condition is met. In this example, we will grab the the last 5 of the top 10 Billboard 100 songs:

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be - Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande", "Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

var i=5;
do{
    console.log("The #" + (i+1) + " record is " + billboard100[i] );
    i++;
}
while(i>4 && i<10);
```
**Output**
```
The #6 record is The Middle - Zedd, Maren Morris & Grey
The #7 record is No Tears Left To Cry - Ariana Grande
The #8 record is Look Alive - BlocBoy JB Featuring Drake
The #9 record is Never Be The Same - Camila Cabello
The #10 record is Perfect - Ed Sheeran
```
### The `for` loop
---
Another very common type of loop that can be found in JavaScript is the `for` loop. It is similar to the `while` loop, but runs "for" a specific number of times. For loops include 3 optional expressions to initialize the variable, declare the condition, and increment or decrement the variable all in the same line. It is easier to read and reduces the chance of error, as could be easily done in `while` and `do....while` loops where infinite loops can easily be created.

With this type of loop, we have the initialization variable and the condition, as per normal, however, in the same line you will also define the `final-expression` which will increment or decrement the variable. The final expression executes at the end of each iteration of the loop automatically, and in this case, will increment by 1 each time until the condition is no longer met and returns `false`. 

Let's say that we only want the first 5 entries of the Billboard 100, because on our site we want to display only the top 5 chart toppers in a sidebar somewhere with limited real estate.

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be - Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande", "Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

for (var i = 0; i < 5; i++) {
  console.log(billboard100[i]);
}
```
**Output**
```
This Is America - Childish Gambino
Nice For What - Drake
God's Plan - Drake
Psycho - Post Malone Featuring Ty Dolla $ign
Meant To Be - Bebe Rexha & Florida Georgia Line
```
As you can see, the loop ran and printed only for the first 5 values, and not the last 5 values, because the condition for `i < billboard100.length` had already been met, and `billboard100.length` is equal to `10`. 

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be -Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande", "Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

var top5 = []

for (var i = 0; i < 5; i++) {
  top5.push(billboard100[i]);
}
console.log(top5)
```
In this loop we add an extra step to grab the first 5 values in our `billboard100` array, and then `push` them into a new array called `top5` that contains only our values for the top 5 songs, and log that `top5` array to our console. Now we have a saved variable with our manipulated data.

**Output**
```
["This Is America - Childish Gambino", "Nice For What - Drake", "God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign", "Meant To Be -Bebe Rexha & Florida Georgia Line"]
```

### The `forEach()` loop

The `forEach()` method takes a function as an argument. We can use this method to iterate over and manipulate data in the exact same way that `for` does with a less syntax.

For the next example, we are going to use backticks, which is called `template literals` to easily create strings with variables in them. This is a much easier to read way to evaluate strings with dynamic values, versus concatenating multiple strings and variables together with the `+` sign. Be aware, that this is feature is not supported in all browsers, and features like this may require JavaScript transpilers. 

**Example**
```
billboard100.forEach(function(item, index){
    console.log(`The #${index + 1} track ${item} on the Billboard 100 is my favorite song of all time!`.toUpperCase())
});
```

In this example, we're reutilizing our Billboard 100 data from before, except this time, we're iterating over all of the values in the array by default, and shouting it in all caps. This way users will understand how much we love the popular music that is played on the radio!

**Output**
```
THE #1 TRACK THIS IS AMERICA - CHILDISH GAMBINO ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #2 TRACK NICE FOR WHAT - DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #3 TRACK GOD'S PLAN - DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #4 TRACK PSYCHO - POST MALONE FEATURING TY DOLLA $IGN ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #5 TRACK MEANT TO BE -BEBE REXHA & FLORIDA GEORGIA LINE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #6 TRACK THE MIDDLE - ZEDD, MAREN MORRIS & GREY ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #7 TRACK NO TEARS LEFT TO CRY - ARIANA GRANDE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #8 TRACK LOOK ALIVE - BLOCBOY JB FEATURING DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #9 TRACK NEVER BE THE SAME - CAMILA CABELLO ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
THE #10 TRACK PERFECT - ED SHEERAN ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
```

The `forEach()` method can cut down on the amount of code that is being written. What if our `billboard100` data was actually an array of objects, with arrays for the artist names? Here's an example of what it could look like with a `for` loop when we want to identify all the artists that appear in the Billboard 100's top 10:

**Example**
```
var billboard100 =
[
    {song: "This Is America", artist: ["Childish Gambino"]}, 
    {song: "Nice For What", artist: ["Drake"]},
    {song: "God's Plan", artist: ["Drake"]}, 
    {song: "Psycho", artist: ["Post Malone","Ty Dolla $ign"]},
    {song: "Meant To Be", artist: ["Bebe Rexha", "Florida Georgia Line"]},
    {song: "The Middle", artist: ["Zedd","Maren Morris Grey"]}, 
    {song: "No Tears Left To Cry", artist: ["Ariana Grande"]},
    {song: "Look Alive", artist: ["BlocBoy JB","Drake"]}, 
    {song: "Never Be The Same", artist: ["Camila Cabello"]}, 
    {song: "Perfect", artist: ["Ed Sheeran"]}
]

for (var i = 0; i < billboard100.length; i++) {
  var entry = billboard100[i]; //This assigns the current billboard entry to this variable for reference in the next line of code
  for (var n = 0; n < entry.artist.length; n++) { //This iterates over the 
  "artist" array
    var artist = entry.artist[n]; //This assigns the current billboard artist name to this variable for easy reference
    console.log(artist);
  }
}
```
**Output**
```
Childish Gambino
Drake
Drake
Post Malone
Ty Dolla $ign
Bebe Rexha
Florida Georgia Line
Zedd
Maren Morris Grey
Ariana Grande
BlocBoy JB
Drake
Camila Cabello
Ed Sheeran
```

We got exactly what we needed using this function, but MAN, that was a lot of code, right? You might get a little lost in the mix and find yourself doing a lot of console logging to keep track of all the variables. This could be simplified with a `forEach()` method:

**Example**
```
billboard100.forEach(function(entry) {
  entry.artist.forEach(function(artist) {
    console.log(artist);
  });
});
```
Whew! Much easier to read, right? Now, let's talk about our `map` functionality!

### JavaScript `map` loop
The map method creates a new array with the results of a function that is called on each iteration of the block. We can revisit our Billboard 100 examples. Remember how we made a new array for our top 5 by doing a `push` of each result into an empty array? In the case where we may want to transform every element in the array, this would be an unecessary extra step. Let's rewrite our shouting Billboard 100 example using the `map` iterator and a simple array:

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be -Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande",
"Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

billboard100.map(function(item){
    return `The track ${item} on the Billboard 100 is my favorite song of all time!`.toUpperCase()
});
```

**Output**
```
["THE TRACK THIS IS AMERICA - CHILDISH GAMBINO ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK NICE FOR WHAT - DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK GOD'S PLAN - DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK PSYCHO - POST MALONE FEATURING TY DOLLA …HE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK MEANT TO BE -BEBE REXHA & FLORIDA GEORGI…HE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK THE MIDDLE - ZEDD, MAREN MORRIS & GREY O…HE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK NO TEARS LEFT TO CRY - ARIANA GRANDE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK LOOK ALIVE - BLOCBOY JB FEATURING DRAKE …HE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK NEVER BE THE SAME - CAMILA CABELLO ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!", "THE TRACK PERFECT - ED SHEERAN ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!"]
```

The output returns our new modified array. If we want to save this array into a new variable, such as `shoutingTop10`, we could write it like so:

**Example**
```
var shoutingTop10 = billboard100.map(function(item){
    return `The track ${item} on the Billboard 100 is my favorite song of all time!`.toUpperCase()
});
console.log("The results of our new array is: " + shoutingTop10)
```
**Output**
```
The results of our new array is: THE TRACK THIS IS AMERICA - CHILDISH GAMBINO ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK NICE FOR WHAT - DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK GOD'S PLAN - DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK PSYCHO - POST MALONE FEATURING TY DOLLA $IGN ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK MEANT TO BE -BEBE REXHA & FLORIDA GEORGIA LINE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK THE MIDDLE - ZEDD, MAREN MORRIS & GREY ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK NO TEARS LEFT TO CRY - ARIANA GRANDE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK LOOK ALIVE - BLOCBOY JB FEATURING DRAKE ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK NEVER BE THE SAME - CAMILA CABELLO ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!,THE TRACK PERFECT - ED SHEERAN ON THE BILLBOARD 100 IS MY FAVORITE SONG OF ALL TIME!
```

### The `for...in` loop
You might be getting overhwhelmed by the many loops, especially since some seemingly have redundant functionality. However, the `for...in` loop is quite different from the previous examples so far, as its functionality is to iterate through an object and its `enumerable` properties. An enumerable property is defined as a property of an object that has an Enumerable value of `true`. The `for...in` loop also iterates in an arbitrary order, so it should not be used if things need to happen in a specific sequence.

**Example**
```
var number1 = {song: "This Is America", artist: "Childish Gambino"}

for (var key in number1){
   console.log(number1[key])
}
```

**Output**
```
This Is America
Childish Gambino
```
The output gives us the same results as logging `number1.song` and `number1.artist`.

### The `for...of` loop
---

The last loop we're going to introduce is the `for...of` loop. This is actually a newer loop that ES6 introduced. 

##### What is ES6?
ECMAScript 6, abbreviated as ES6 or referred to as "Harmony", was the 6th major release of the ECMAScript language standards. ECMAScript is another name for what we know as JavaScript. 

These specifications change regularly, so you may encounter different methods and syntax across different resources, such as using `arrow functions` to write functions or `let` instead of `var` to define local variables. You'll want to pay attention to these changes over time, as they are not always compatible across major browsers. New standards can mean easier or alternative ways of writing JavaScript! 

ES5 already had most of the previous loops discussed thus far--the  `for` loop, the `while` loop, the `do....while` loop and the `for...in` loop to iterate through keys and objects.

The following example demonstrates the newer `for...of` loop's functionality:

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be -Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande",
"Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

for (let entry of billboard100) {
    console.log(billboard100)
}
```

**Output**
```
This Is America - Childish Gambino
Nice For What - Drake
God's Plan - Drake
Psycho - Post Malone Featuring Ty Dolla $ign
Meant To Be -Bebe Rexha & Florida Georgia Line
The Middle - Zedd, Maren Morris & Grey
No Tears Left To Cry - Ariana Grande
Look Alive - BlocBoy JB Featuring Drake
Never Be The Same - Camila Cabello
Perfect - Ed Sheeran
```

When you execute this function, the values are printed out. This could be achieved before with a `for` or `forEach()` loop, but this is a shorter syntax which is perfect for looping through arrays.

#### These all do very similar things, when should I apply them?

So you're probably wondering, if they do the same thing, why not go for the less-involved method each time? There are a few cases where we might prefer one loop over another:

##### 1. Using `for` for breaking loops early
With the `for` loop, you can add a conditional statement that will stop the loop as soon as some criteria is met. 
```
var billboard100 =
[
    {song: "This Is America", artist: ["Childish Gambino"]}, 
    {song: "Nice For What", artist: ["Drake"]},
    {song: "God's Plan", artist: ["Drake"]}, 
    {song: "Psycho", artist: ["Post Malone","Ty Dolla $ign"]},
    {song: "Meant To Be", artist: ["Bebe Rexha", "Florida Georgia Line"]},
    {song: "The Middle", artist: ["Zedd","Maren Morris Grey"]}, 
    {song: "No Tears Left To Cry", artist: ["Ariana Grande"]},
    {song: "Look Alive", artist: ["BlocBoy JB","Drake"]}, 
    {song: "Never Be The Same", artist: ["Camila Cabello"]}, 
    {song: "Perfect", artist: ["Ed Sheeran"]}
]

for (var i = 0; i < billboard100.length; i++) {
    let entry = billboard100[i];
    for (let n = 0; n < entry.artist.length; n++) {
        let artist = entry.artist[n];
        if(artist.length < 5) {
            console.log(`No! The artist ${artist} does not have enough letters!`)
            break; //kill it. it's canceled!
        }
        console.log(`The artist '${artist}' meets the criteria.`)
    }
}
```
In this example, we have a very biased loop that's not interested in moving forward with looping over the artist array if it encounters an artist name under 5 characters. Zedd's name is only 4 characters, and therefor Maren Morris Grey is excluded as well. 

>"And this doesn't work with a `forEach()` loop?"

You can try this...
```
billboard100.forEach(function(entry) {
  entry.artist.forEach(function(artist) {
    if(artist.length < 5) {
            console.log(`No! The artist ${artist} does not have enough letters!`)
            break; //kill it. it's canceled!
        }
        console.log(`The artist '${artist}' meets the criteria.`)
  });
});
``` 
 Sorry, Charlie--It does not work. You'll receive an `error`. If you remove the break statement, the code will work, however, your program will be convinced that "Zedd" meets the 5 letter minimum criteria, even after _just_ saying that he doesn't meet the criteria! The loop can be made to work, but not in this fashion.

 ##### 2. The `forEach()` and `map` loops ONLY work on arrays
 If you want to do counting, `forEach()` and `map` are not going to be as accommodating. This may not be a major concern for many, though.

##### 3. The `for` and `map` loops are more performant than `forEach()`
As ugly as it may be, unfortunately many developers may choose the `for` loop route to optimize on performance. The `forEach()` loop invokes a callback for each iteration, and with that it carries some overhead. However, there are ways around this that we won't get into just yet, but you can actually use `map` to optimize for speed as well, _if_ you are working with creating a new array, versus changing the original array.

##### 4. The `for...of` loop might be the best of both worlds?
Remember our example from the `for` loop? `for...of` let's us emulate the functionality of `for` with the readability of `forEach()`. Let's try our `billboard100` example again, first with the `break`:

```
var billboard100 =
[
    {song: "This Is America", artist: ["Childish Gambino"]}, 
    {song: "Nice For What", artist: ["Drake"]},
    {song: "God's Plan", artist: ["Drake"]}, 
    {song: "Psycho", artist: ["Post Malone","Ty Dolla $ign"]},
    {song: "Meant To Be", artist: ["Bebe Rexha", "Florida Georgia Line"]},
    {song: "The Middle", artist: ["Zedd","Maren Morris Grey"]}, 
    {song: "No Tears Left To Cry", artist: ["Ariana Grande"]},
    {song: "Look Alive", artist: ["BlocBoy JB","Drake"]}, 
    {song: "Never Be The Same", artist: ["Camila Cabello"]}, 
    {song: "Perfect", artist: ["Ed Sheeran"]}
]

for (let entry of billboard100) {
    let artists = entry.artist
	for(let artist of artists) {
		if(artist.length < 5 ) {
			console.log(artist + " does not have enough letters. Stopping...")
			break
		}
		console.log("This artist meets the 5 letter minimum: " + artist)
	}
}
```

**Output**
```
This artist meets the 5 letter minimum: Childish Gambino
This artist meets the 5 letter minimum: Drake
This artist meets the 5 letter minimum: Post Malone
This artist meets the 5 letter minimum: Ty Dolla $ign
This artist meets the 5 letter minimum: Bebe Rexha
This artist meets the 5 letter minimum: Florida Georgia Line
Zedd does not have enough letters. Stopping...
This artist meets the 5 letter minimum: Ariana Grande
This artist meets the 5 letter minimum: BlocBoy JB
This artist meets the 5 letter minimum: Drake
This artist meets the 5 letter minimum: Camila Cabello
This artist meets the 5 letter minimum: Ed Sheeran
```

We can try the same function again without the break, and get the same results as `forEach()` would give us. This time, we've changed it the function to give the output by changing the conditional slightly.

**Example**
```
for (let entry of billboard100) {
    let artists = entry.artist
	for(let artist of artists) {
		if(artist.length < 5 ) {
			console.log(artist + " does not have enough letters.")
		} else {
		    console.log("This artist meets the 5 letter minimum: " + artist)
        }
	}
}
```

**Output**
```
This artist meets the 5 letter minimum: Childish Gambino
This artist meets the 5 letter minimum: Drake
This artist meets the 5 letter minimum: Post Malone
This artist meets the 5 letter minimum: Ty Dolla $ign
This artist meets the 5 letter minimum: Bebe Rexha
This artist meets the 5 letter minimum: Florida Georgia Line
Zedd does not have enough letters.
This artist meets the 5 letter minimum: Maren Morris Grey
This artist meets the 5 letter minimum: Ariana Grande
This artist meets the 5 letter minimum: BlocBoy JB
This artist meets the 5 letter minimum: Drake
This artist meets the 5 letter minimum: Camila Cabello
This artist meets the 5 letter minimum: Ed Sheeran
```
Now we can still see "Maren Morris Grey" in the list of names, instead of excluding her for working with an artist with too few letters!

### Conclusion

Ultimately, some developers would agree that we write code for humans--not computers. So it's up to the developers to decide what makes the most sense for maintenance and performance. There is no single _right_ way, but it's good to have an understanding of all options available, including options like `for...of` which leverages existing technology in other basic programming languages like `C++`, `Java`, and `C#`. You have a seemingly endless number of options to iterate over different data structures.
