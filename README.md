# JavaScript Loops

## Objectives
1. Give an overview of the different options avaialable for loops in JavaScript
2. Explain the uses of each type of loop

Loops are a common programming function in programming. Though the syntax varies for each language, the concept is the same. JavaScript has a number of loops that you can leverage, depending on what is trying to be achieved with the function.

In all loops, we must initialize a variable. The variable `i` in the following examples will be our initialization statement. This is a commonly defined variable that can be incremented over each iteration of the loop. This variable can be defined as anything--such as "sasquatch" or "bananas", if using more semantic language is beneficial to your style of writing code.

Loops will continue to run until the conditions are met. Fore exampled,the conditional statement of `i < 5` will be evaluated on each iteration of the loop. If the condition is `true`, the loop will continue. If the condition is false, for example, if `i` is now equal to 5 after running the loop 4 times, the loop will not execute.

### The `while` loop
---
The `while` loop is a pretty basic loop that is available in other programming languages as well. The loop will continue to be executed so long as the condition is true. In the below example, the variable `i` starts at 0, and will continue to increment until `i` is no longer less than 0. This loop will _start_ with 0, print the statement to the console, then increment the value of `i`. It will continue to 1, 2, 3, and so on, so the loop will run 5 times. Make _sure_ that the block contains code that will either break the loop, or change the condition so that it will eventually evaluate to false. Without this, an infinite loop will be created and this block will never stop executing!

This example demonstrates what happens during the `while` loop:
**Example**
```
var i = 0
while (i < 5) {
  console.log("I is less than 5");
  i++; //this is necessary to avoid an infinite loop
}
```
**Output**
```
I is less than 5
I is less than 5
I is less than 5
I is less than 5
I is less than 5
```
Here we have another simple example with the same logic:
**Example**
```
var i = 0
while (i < 5) {
  console.log("The value of i is " + i);
  i++; //this is necessary to avoid an infinite loop
}
```
**Output**
```
The value of i is 0
The value of i is 1
The value of i is 2
The value of i is 3
The value of i is 4
//the loop stops here because i is no longer less than 5
```

### The `do...while` loop
The `do...while` loop is similar to `while`, as in it will execute a block of code based on a condition or set of conditions. It will execute at least once, and continue to execute if the condition is met

**Example**
```
var i=5;
do{
    console.log("The value of i is " + i);
    i++;
}
while(i>4 && i<10);
```
**Output**
```
The value of i is 5
The value of i is 6
The value of i is 7
The value of i is 8
The value of i is 9
```
### The `for` loop
---
Another very common type of loop that can be found in JavaScript is the `for loop`. It is similar to the `while` loop, but runs "for" a specific number of times. For loops include 3 optional expressions to initialize the variable, declare the condition, and increment or decrement the variable all in the same line. It is easier to read and reduces the chance of error, as could be easily done in `while` and `do....while` loops where infinite loops can easily be created.

With this type of loop, we have the initialization variable and the condition, as per normal, however, in the same line you will also define the `final-expression` which will increment or decrement the variable. The final expression executes at the end of each iteration of the loop automatically, and in this case, will increment by 1 each time until the condition `i < 5` is met and returns `false`. 

**Example**
```
var array = ["1st loop", "2nd loop", "3rd loop", "4th loop", "5th loop", "6th loop"]

for (var i = 0; i < 5; i++) {
  console.log(array[i]);
}
```
**Output**
```
1st loop
2nd loop
3rd loop
4th loop
5th loop
```
As you can see, it only ran for the first 5 values, and didn't print out the 6th value, because the condition for `i < 5` had already been met.

Let's use a more tangible real-world example! Let's assume we have a list of the Billboad 100's top 100 songs and artists in descending rank order from an API endpoint. We're going to use 10 in this static example, because 100 is a lot! We only want the first 5, because on our site we want to display only the top 5 chart toppers in a sidebar somewhere with limited real estate.

**Example**
```
var billboard100 =
["This Is America - Childish Gambino", "Nice For What - Drake",
"God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign",
"Meant To Be -Bebe Rexha & Florida Georgia Line", "The Middle - Zedd, Maren Morris & Grey", "No Tears Left To Cry - Ariana Grande",
"Look Alive - BlocBoy JB Featuring Drake", "Never Be The Same - Camila Cabello", "Perfect - Ed Sheeran"]

var top5 = []

for (var i = 0; i < 5; i++) {
  top5.push(billboard100[i]);
}
console.log(top5)
```
This loop is going to grab the first 5 values in our `billboard100` array, and `push` them into a new array called `top5` that contains only our values for the top 5 songs, and log that `top5` array to our console.

**Output**
```
["This Is America - Childish Gambino", "Nice For What - Drake", "God's Plan - Drake", "Psycho - Post Malone Featuring Ty Dolla $ign", "Meant To Be -Bebe Rexha & Florida Georgia Line"]
```
**Note:** If you want to iterate over the entire array and not the first 5, you can do so by using array.length, which in this case would be `billboard100.length`, which will equal 10. 

### The `forEach` loop

The `forEach()` method takes a function as an argument. We can use this method to iterate over and manipulate data in the exact same way that `for` does with a little less syntax.

**Example**
```
billboard100.forEach(function(item, index){
    console.log(`The #${index + 1} track ${item} on the Billboard 100 is my favorite song of all time!`.toUpperCase())
});
```

In this example, we're reutilizing our Billboard 100 data from before, except this time, we're iterating over all of the values in the array and shouting it in all caps. This way users will understand how much we love the popular music that is played on the radio. 
**Note:** We are using backticks to create strings with variables in them. This is a much easier to read way to evaluate strings with dynamic values, versus concatenating multiple strings and variables together with the `+` sign. We are also incrementing the `index` by 1, so that the index of 0 is not printed out for the first item in the array, when we actually want "1".

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

The `forEach` method can cut down on the amount of code that is being written. What if our `billboard100` data was actually an array of objects, with arrays for the artist names? Here's an example of what it could look like with a `for` loop when we want to identify all the artists that appear in the Billboard 100's top 10:

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

for (let i = 0; i < billboard100.length; i++) {
  let entry = billboard100[i];
  //console.log(entry); This would give us each object containing the song name and artists
  for (let n = 0; n < entry.artist.length; n++) {
    let artist = entry.artist[n];
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

We got exactly what we needed using this function, but MAN that was a lot of code, right? You might get a little lost in the mix and find yourself doing a lot of console logging to keep track of all the variables. This can be simplified with `forEach`:

**Example**
```
billboard100.forEach((entry) => {
  entry.artist.forEach((artist) => {
    console.log(artist);
  });
});
```
Whew! Much better, right? Now, let's talk about our `map` functionality!

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

```
var shoutingTop10 = billboard100.map(function(item){
    return `The track ${item} on the Billboard 100 is my favorite song of all time!`.toUpperCase()
});
console.log("The results of our new array is: " + shoutingTop10)
```
### The `for...in` loop
You might be getting overhwhelmed by the many loops, especially since some seemingly have redundant functionality. However, the `for...in` loop is quitedifferent from the previous examples so far, as its functionality is to iterate through an object and its `enumerable` properties. An enumerable property is defined as a property of an object that has an Enumerable value of true. The `for...in` loop also iterates in an arbitrary order, so it should not be used if things need to happen in a specific sequence.

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

The last loop we're going to introduce is the `for...of` loop. This is actually a newer loop that ES6 also introduced. 

##### What is ES6?
ECMAScript 6, abbreviated as ES6 or referred to as "Harmony" was the 6th major release of the ECMAScript language standards. ECMAScript is another name for what we know as JavaScript. These specifications change regularly, so you may encounter different methods and syntax across different resources, such as using `arrow functions` to write functions or using `let` instead of `var` to define local variables. You'll want to pay attention to these changes over time, as new standards can mean easier or alternative ways of writing JavaScript--once the new specifications are adopted across and compatible with major browsers.

ES5 already had most of the previous loops discussed thus far--the  `for` loop, the `while` loop, the `do....while` loop and the `for...in` loop to iterate through keys and objects. 

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

When you execute this function, the values are printed out. This could be achieved before with a `for` or `forEach` loop, but this is a shorter syntax which is perfect for looping through arrays.

#### These all do very similar things, when should I apply them?

So you're probably wondering, if they do the same thing, why not go for the less-involved method each time? There are a few cases where we might want to utilize a `for` loop instead:
##### 1. Using `for for breaking loops early
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
In this example, we have a very biased loop that's not interested in moving forward with looping over the array if it encounters an artist name under 5 characters. Zedd's name is only 4 characters, and therefor Maren Morris Grey is excluded as well. 

>"And this doesn't work with a `forEach` loop?"

You can try this...
```
billboard100.forEach((entry) => {
  entry.artist.forEach((artist) => {
    if(artist.length < 5) {
            console.log(`No! The artist ${artist} does not have enough letters!`)
            break; //kill it. it's canceled!
        }
        console.log(`The artist '${artist}' meets the criteria.`)
  });
});
``` 
 Sorry, Charlie. It does not work. You'll receive an `Illegal break statement` error. If you remove the break statement, the code will work, however, your program will be convinced that "Zedd" meets the 5 letter minimum criteria, even after _just_ saying that he doesn't meet the criteria! The loop can be made to work, but not in this fashion.

 ##### 2. The `forEach()` and `map` loops ONLY works on arrays
 If you want to do counting, `forEach()` and `map` are not going to be as accommodating. This may not be a major concern for many, though.

##### 3. The `for` and `map` loops are more performant than `forEach`
As ugly as it may be, unfortunately many developers may choose the `for` loop route to optimize on performance. The `forEach()` loop invokes a callback for each iteration, and with that it carries some overhead. However, there are ways around this that we won't get into just yet, but you can actually use `map` to optimize for speed as well, _if_ you are working with creating a new array, versus changing the new array.

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

Ultimately, some developers would agree that we write code for humans--not computers. So it's up to the developers to decide what makes the most sense for maintenance and performance. There is no single _right_ way, but it's good to have an understanding of all options available, including options like `for...of` which leverages existing technology in other basic programming languages like `C++`, `Java`, and `C#`, and gives you a seemingly endless number of options to iterate over different data structures.