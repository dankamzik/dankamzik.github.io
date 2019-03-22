JAVASCRIPT NOTES:

Begin by naming another file with the title "scripts.js"; additionally JS can be placed directly into the
html file as well using <script></script> tags. When using this method of imputing JS code into a html page, it is always a good
idea to place the script tags at the bottom of the html code sheet, rather than the top. Placing the code at the bottom allows
the html and stylesheet to load first, then the javascript.
Example of linking an HTML page to JS script(s):
Ex:

//after final div, before closing body tag
```html
<script src="js/helpers.js"></script>
<script src="js/filename.js"></script>
```
============================================================================================================================

TO BEGIN WITH...

A simple JS command:
```JS
alert("Hello from Dan Kamzik!");
```
"alert" is a command that is built into the browser; it opens a dialogue box and displays a value
(whatever is inside the parenthesis). All together this entire string of code is called a "statement."
Just as Sentences end in periods, Statements end in a semicolon.

Here's a new Statement:
```JS
document.write(<h1>Welcome to my Web Page!</h1>);
```
"write" is a command that tells the computer to display a statement to the page.
```JS
alert(<h1>Thanks for Visiting!</h1>);
```
======================================================================================================================
LINKING PAGES:
======================================================================================================================
Use the following code to link a JS file to an HTML file:
```HTML
<script src="NAME OF FILE.js"></script>

Ex:
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="css/main.css">
    <title>Random Number Guessing Game</title>
    </head>
    <body>
    <div class="container">
    <h1>Random Number Guessing Game</h1>
    <script src="script.js"></script>
    </div>
    </body>
    </html>
```
=======================================================================================================================
DEBUGGING:
=======================================================================================================================
To get to the JavaScript Inspector use the following keyboard shortcut:

CTRL+SHIFT+J

Probably the most useful tool in this inspector is located on the top right corner, across from the error message.
This tool tells you where the error is located in your script (what line) and, when clicked, is even a link to the
problemed code segment.

AN IMPORTANT COMMAND:

cosole.log is an important command to know for JS work. It allows us to write notes to ourselves within the inspector.
Its a handy tool to use for longer segments of code or delineate sections of JS script.

=======================================================================================================================
VARIABLES
=======================================================================================================================
Variables are like boxes that we can store information in.
The information we put into a variable is called as "value".
There are two common value types; numbers and strings.
Numbers are used for making calculations; add/sub, scores, computing, etc.
Strings are used for words, messages and other characters. JS allows you to use double or single quotes when writing
a string, just Be Consistent!

The basic syntax to use a variable is expressed as:
```JS
var NAME;
```
Additionally, you can add in more information:
```JS
var price=0;
```
In the above variable expression, the value to the right side of the = sign is always being told to go into the object on the left.

VARIABLE EXAMPLE:
```JS
var message= "Hello!";
alert(message);
```
The above will display an alert box with the message "Hello!"
Lets dig deeper by changing the message value again:
```JS
var message= "Hello!";
alert(message);
message="Welcome to my website";
```
Notice above that in order to change the message to "welcome to my website" we dont have to use
"var" any longer, but can simply call "message" and rewrite it's value.
Deeper. Lets create two separate messages with different values:
```JS
var message= "Hello!";
alert(message);
message="Welcome to my website";
alert(message);
```
Notice that creating two separate alert boxes with different values was as easy as adding in another "alert" under
my second message statement.

Naming Variables:

There are a few rules to consider when naming variables; variables cannot begin with a number. So "var 9lives;"
will just return a syntax error. You can, however, end a variable name in a number. So "var lives9;" will work just fine.

Names can only contain LETTERS, NUMBERS, $ and _ characters. Anything else results in an error.

The most common naming conventions are as follows;
"this_is_a_name"
and
"thisIsAName"
The first uses underscores to break up each word and the second is called Camel case and it uses uppercase lettering.

========================================================================================================================
KEYWORDS
========================================================================================================================
Browsers have a set list of keywords to help communicate and facilitate JS programming.
"var" happens to be one of these keywords. An important thing to note here is that because "var" is a Keyword,
you cannot name a variable "var". For example the code:
```JS
var var="0";
```
will never work because the variable name is also a keyword. It is therefore redundant.

===========================================================================================================================
The PROMPT command
===========================================================================================================================
 The PROMPT command is expressed as:
```JS
 prompt();
```
 You use this command to ask a question.
 Therefore, you need a message. Ex:
```JS
 prompt("What is your name?");
```
 The above returns an alert box that asks a question and has a field for a response.
 But what happens to our response after we input it?
 The computer stores our answer and sends it back to the program. We call this "returning a value".
 We can capture a returned value by using a Variable.
 For example:
```JS
 var visitorName= prompt("What is your name?");
 alert(visitorName);
```
========================================================================================================================
More advanced JS usage
========================================================================================================================
```JS
var visitor= prompt("What is your name?");
var message="Hello " + visitor;
document.write(message);
```
The above will result in a prompt box appearing on screen, which asks for your name.
After inputting your name, it then displays Hello NAME. Make sure to observe the fact that I had to put a space
in after hello and before the end quote. This ensures that there is space between "Hello" and "NAME".
Also notice the plus sign "+" that was used above to attach two strings together, this is a very common occurrence in JS.

==========================================================================================================================
LEARNING RESOURCES
==========================================================================================================================
Mozilla Developer Network: MDN for short, is an excellent resource for quick lookups and further learning. Its basically a
JS documentation compilation.

============================================================================================================================
.length property
============================================================================================================================
Ex:
```JS
message.length
```
You can put a "." after an object and then place in a property in order to perform a more complex function.
In the statement above, a return of the character length of the message is posted to the editor(inspector) menu.

A property is like a variable in that it holds information. A string's length property, for example, contains a number;
the number of characters contained in the string.

============================================================================================================================
METHODS
==============================================================================================================================
Methods are commands that you can perform on a string.
For example:
```JS
string.protoype.toLowerCase()
```
The statement above allows us to manipulate a string ( a message written either within a few quotations or within a var).
the toLowerCase() part is an action to be performed on the string. This particular method writes the string as all
lower-case letters.
Ex:
```JS
console.log("ALPHABET".toLowerCase() ); // "alphabet"
```
Take note of the () after the method. These are necessary for the compiler to understand that you have written a method.

==========================================================================================================================
Creating a JS Madlibs Game
==========================================================================================================================
Create a story-telling program:

1. Use the prompt() command several times to collect different types of words -- nouns, verbs, adjectives.
2. Store the result of each prompt() command in a different variable.
3. Combine the variables with other strings to create one or more non-sensical statements.
4. Print the resulting story to the browser using the document.write() command.

CODE:
```JS
alert("welcome to my JavaScript Madlib Program!");

var adjective= prompt("Please provide an adjective");

var noun= prompt("Please provide a noun");

var verb= prompt("Please provide a verb");

var adjective2= prompt("Please provide an adjective");

var noun2= prompt("Please provide a noun");

var message="The " +  adjective + " " + noun +  " " + verb + " down the " +  adjective2 + " " + noun2;

alert("Ready for your Madlib?");

document.write(message);

alert("Thanks for Playing!");
```
=========================================================================================================================
Basic Calculations Using Variables
=========================================================================================================================
Example of a score keeping program:

The score begins at:
```JS
var score=0;
```
And say you get 100 points for something:
```JS
score = score + 100;
```
In the above you see the variable "score" appear twice. Remember that when we put a value into a variable,
the stuff on the right goes into the variable on the left. In the example above, the stuff on the right is the current
contents of the variable "score", plus and added 100. The total is then stored in the variable on the left.
That is how you Update a Variable.

Calculating seconds in a day, hours in a week or minutes in a year:
```JS
var secondsPerMinute=60;
var minutesPerHour=60;
var hoursPerDay=24;
var daysPerWeek=7;
var weeksPerYear=52;
```
Lets calculate secondsPerDay:
```JS
var secondsPerDay= secondsPerMinute * minutesPerHour * hoursPerDay;
document.write("There are" + secondsPerDay + " " + "seconds in a day")
```
Lets calculate how many seconds you have lived:
```JS
var myAge=25;
var secondsOfLife= secondsPerMinute * minutesPerHour * hoursPerDay * daysPerWeek * weeksPerYear * myAge;
document.write ("You have lived " + secondsOfLife + " seconds of life");
```
=========================================================================================================================
Mathematical Shorthands
=========================================================================================================================
There are also shorthand methods for performing each of the basic mathematical operations on a variable.
Example:
Add 10 to the contents of a variable using shorthand:
```JS
var+=10;
```
This can be done with each of the basic mathematical operators:

score = score + 10;     |     score+=10;
score = score - 20;     |     score-=20;
score = score * 5;      |     score*=5;
score = score / 2;      |     score/=2;

=========================================================================================================================
PITFALL: Working with numbers in strings
=========================================================================================================================
Because JS treats every character in a string as just that, a character, numbers are also considered characters as well.
Numbers contained within strings cannot be calculated.
Ex:
```JS
var cats = prompt("How many cats do you have?");            // example integer: 14
var dogs = prompt("How many dogs do you have?");                             // 9
var totalPets = (cats) + (dogs);
alert("Wow you have " + totalPets + " !");                       //   answer: 149
```
The above is still able to be computed, but you need a way to show that the string contains real numbers.
We can do this with the "parseInt" command.
Ex:
```JS
var cats = prompt("How many cats do you have?");             //example integer: 14
var dogs = prompt("How many dogs do you have?");                      //         9
var totalPets = parseInt(cats) + parseInt(dogs);
alert("Wow you have " + total pets + " !");                       //    answer: 23
```
IMPORTANT! REMEMBER: parseInt returns whole numbers (integers), IF you have a floating point number in a string, you MUST use the command
"parseFloat" in order to be returned the correct value. If not, the program will return an error called NaN or Not A Number.

=========================================================================================================================
Creating a counter in a prompt succession:
=========================================================================================================================

var questions = 3;
var questionsLeft = " [" + questions + "questions left]";
var adjective = prompt("please type an adjective" + questionsLeft);
questions -= 1;
var questionsLeft = " [" + questions + "questions left]";
var verb = prompt("please type a verb" + questionsLeft);
questions -= 1;
var questionsLeft = " [" + questions + "questions left]";
var noun = prompt("please type a noun" + questionsLeft);
questions -= 1;
var questionsLeft = " [" + questions + "questions left]";
alert(Ready for your Madlib?)
var message = "<h2>var message="The " + adjective;
sentence += " programmer who wanted to use JavaScript to " + verb;
sentence += " the " + noun + " .</h2>";
document.write(sentence);


=========================================================================================================================
The Math object:
=========================================================================================================================
JS is made up of "objects". Numbers are an object, as are strings.
We use the "math" object to generate random numbers via the correct "method"
which is a command specific to the "object".

Ex:
```JS
Math.round(2.2)
result: 2
```
In the above example, "math" is the object and "round" is the "method".
Here is the proper syntax for adding in a Math object. Keep in mind that the "M" in Math is always capitalized:
Ex:
```JS
var temperature = parseFloat(37.5);
alert (Math.round(temperature));
```
Generating Random Numbers:

A note on Randomness:
Randomness is important in creating applications, websites, programs and other web based platforms. You can generate random
questions for a quiz, have a random picture show up each time a user visits your site, make spawn points in a game, etc.

The random number generation command is expressed as:
```JS
Math.random
```
Math.random generates a floating point number anywhere between 0 and 1, with 1 not being recognized as a potential number generation and 0 being included as a permissible number generation.

Math. random returns a value like this:
0.25800076578004

There are many other Math methods as well, such as "floor" and "ceil". Both of these methods convert decimal values to integers.
With each method, you specify a number in () and the method returns a new value, depending on what the method does.
Math.floor returns the closest whole value to the decimal rounded down. Math.ceil returns a whole value closest to the decimal
rounded up. Hence, floor and ceil(ing). If you provide a whole number rather than a floating point number, the return is simply the
whole number.

Ex:
```JS
Math.floor(4.7)
```
Return: 4

Ex:
```JS
Math.ceil(4.2)
```
Return: 5

Ex:
```JS
Math.floor(8) Return: 8
Math.ceil(8) Return: 8
```
In programming, code executes from the inside out, meaning that the code in the innermost parentheses will be computed first.

Ex:
```JS
Math.floor(Math.random() * 6 );
```
In the above example, the Math.random * 6 would be computed first, and then the return of that will be floored.

Full Ex:
```JS
Math.floor(Math.random(0.72407) * 6 );
```
Return: 4.34442
```JS
Math.floor(4.34442);
```
Return: 4

Say we wanted to return a value between 1 and 6 for a program that calls for it.
We would add an additional 1 integer to the equation to achieve that result.
Ex:
```JS
Math.floor(Math.random(0.72407) * 6 ) + 1;
```
We would not use the ceil method to achieve this result, because there is a very slight chance that you may end up with 0 as a return.
With the above method, this result is impossible.
Lets see this function fleshed out fully in a real life example:

Ex:
```JS
var dieRoll=Math.floor(Math.random() * 6 );
alert("You rolled a " + dieRolls );
```
=========================================================================================================================
Conditional Statements:
=========================================================================================================================
Conditional statements provide your program with decision-making capability.
Conditional statements can be as simple as true false, if this then that.
For example, if you coded a game that ends when the player is out of lives, that would be based on a conditional statement.
"If the player is out of lives, then end the game"

Lets try another example; programming a quiz:

We begin by asking a question and getting a response from a user:
```JS
var answer = prompt ("Who was the first President of the United States?");
```
Next, we add in the basic structure for a conditional statement:
```JS
if ( answer==="George Washington"){
  document.wirte("Correct, good job!");
}
```
In the above, we begin with an "if" statement which checks whether or not the user input was true or false. If true, then the program will
execute the code block located inside the curly braces. The triple equal sign "===" is called an "equality operator" and its used to test
if two values are exactly the same.
But what if the answer supplied by the user is incorrect? We can kick off an event if a statement is found to be false as well.
This is called an "else" clause. You add it directly to the if statement like this:
```JS
if ( answer==="George Washington"){
  document.write("Correct, good job!");
} else{
  document.write("Sorry, that is incorrect.");
}
```
Now we have a fully running conditional statement. However, there is still a problem. If the user inputs the correct answer to the question
but in a different format, the computer will handle it literally and count the answer as false. For example "gerorge washington" or
"George washington" or "GerogE WashingTon", etc would be considered false to the computer.
To skirt around this, we can employ the "toUpperCase" method. This automatically converts the answer the user inputs in any case, to upper case.
Now we just change our answer to uppercase, and the computer will always be able to recognize the correct answer.
Ex:
```JS
if ( answer.toUpperCase()==="GEORGE WASHINGTON"){
  document.write("Correct, good job!");
} else{
  document.write("Sorry, that is incorrect.");
}
```
Now the program will run without any quirks.

=========================================================================================================================
Conditional Statements: Boolean
=========================================================================================================================

Boolean can either be true or false, 0 or 1.
You use boolean by simply inputting true or false into a conditional statement.
Ex:
```JS
    if ( false ){
        document.write(<p>"The condition is true"</p>);
    }
    else{
        document.write(<p>"The condition is false"</p>);
    }
```
Notice in the code above that the boolean value has no quotes around it. This is an important syntax qwerk to keep in mind.

You can also have a third type of statement called an "if else" statement. It allows you to write more in depth programs that have multiple, branching options.
Ex:
```JS
    if else ( var === false ){
        document.write("");
    }
```
=========================================================================================================================
Commenting in JS:
=========================================================================================================================

JavaScript provides us with multiple ways to comment out sections of code as well as input developer notes.
The first is the double forward slash "//". This allows you to comment out a full single line of code.
The next is used to comment out multiple lines of code or to drop in a developer comment, it is the same as HTML with two forward slashes encasing two asterisks.

=========================================================================================================================
Combining Boolean Tests:
=========================================================================================================================

Rather than write out individual t/f tests you can combine them in JS to facilitate speed in coding.
Say, for example, you want to solve the question "Do I want to go swimming?" The parameters are "Is it hot outside?" and "Can I swim?" Both of these parameters have to be true in order to move on in the equation and decide to go swimming. Rather than write out two separate blocks for each parameter, we can combine them using the "and operator" described as "&&".
Ex:
```JS
      (20 < age && age < 30)
```

In the above equation, there are two parameters being tested in order to figure out if the variable contains an integer between 20 and 30. Each side of the && is tested separately and produces its own true/false value.
The and operator is very strict, as you can see above. It takes both  parameters to be true for the and operator to run the function.

Sometimes you would want to perform an action if either parameters are met. This can be achieved using the "or operator", described as "||".
Ex:
```JS
    (agree === "yes" || agree === "y")
```
In the above equation, we have set the or operator to run when either parameter is true. If the variable is set to either "yes" or "y", then the function runs. Any other input is not acceptable, however.

As an important side note, you can string together as many operators and parameters to be met as you would like within a single equation.

=========================================================================================================================
JavaScript Functions:
=========================================================================================================================

Functions are nothing more than a set of detailed instructions you want to give to your computer, so that it can perform a task. This task can and will be performed again and again until the computer is told otherwise.
You begin by declaring a function, using the keyword "function". Then you set the functions parameters within the curly braces which form a code block. Finally, you must call the function, which is described at the bottom of our code as the function name, followed by empty parentheses and then a semicolon.
Ex:
```JS
    function goToCoffeeShop(){
        alert("Coffee is on the way!");
    }
        goToCoffeeShop();
```
Functions are usually placed at the top of a JS code sheet. Remember that just because you wrote a function, that does not mean it will be run as soon as the computer reads it. The computer is simply memorizing the function for the time being. You must call the function in order to run it; that can be done anywhere in the code sheet.


=========================================================================================================================
JavaScript Functions with Boolean Decision Making:
=========================================================================================================================

Functions do two main things: perform specified actions and return values. To return a value from a function, use the "return" keyword.
Ex:
```JS
    function goToCoffeeShop(){
        return("Coffee is on the way!");
    }
        goToCoffeeShop();
```
Now we can put some of the above concepts to work with one another. Below I will write a small program that checks to see if there has been any input into an Email field. If there has not been any input, it will give an alert saying "please enter your email".
Ex:
```JS
    function is_mail_empty(){
        var field = document.getElementById("email");
        if(field.value === " "){
        return true;
        } else{
        return false;
        }
    }

    var field_test = is_mail_empty();
    if (field_test === true){
        alert("Please Provide an Email address");
    }
```
Below is an example of a JS function named max, which has two integer arguments and always outputs the larger of the two numbers.
Ex:
```JS
    function max(a, b) {
    if (a > b) {
        return a;
    } else {
      return b;
    }
    }
    alert ((10, 20));
```
More on Functions:

Functions act as their own stand alone pieces of code. In other words, functions act like their own separate universes in which what happens in another function does not affect another function. The variables named and called within a function are individual to that particular function. In this way, you can have multiple variables that have the same name such as "width" "height" "age" or any other commonly used variable name.
 Ex:
 ```JS
        function greeting(){
            var person = "Dan";
            alert (person);
        }
         var person = "George";
         greeting();
         alert(person);
         greeting();
```
So the code above, given the limited scope of a function, would first return a value of "Dan", then "George" and then "Dan" again. In this script there are two different variables named "person" and they have two separate values. Each variable lives in a different scope. There is a scope inside the function and one outside the function. The variable outside the function is called the GLOBAL SCOPE, and is the larger universe of the two. Whereas the variable "person" inside of the function is limited to that function's scope, the variable "person" living in the global scope can be accessed by ALL FUNCTIONS. In other words, a function can change the value of a variable that resides in the global scope. Because of their ability to be overwritten, it is generally a bad idea to make any functions dependent on global variables, as another function my accidentally change them. Always use the keyword "var" within a function to name a variable within your function, otherwise it will overwrite values from the global scope.

Loops Arrays and Objects:

Loops:

A loop is a way in which to run a particular action a certain number of times, or else until a certain condition is true.
When writing a loop, the code that you want to run a number of times is contained within.

While Loop:
```JS
  var counter = 0;
  while( counter < 10 ){
    var randNum = randomNumber (6);
    document.write(randNum + " ");
    counter += 1;
  }
```
  The code above is an example of a while loop. It will generate 10 random numbers between 1 and 6. Take note of the placement of variables here. The counter variable is located outside of the loop, while the randNum variable is within the loop. The + " " is to give us a blank space between each of our randomly generated numbers, else they will come out as one long string of digits.

  Conditional Loop:

  Sometimes you want a block of code to run until a certain criteria is met. Below is a small program that generates a random number between X and Y, then has another computer guess the number. The program logs how many times the computer had to guess before it came to the correct  number, and prints it to the screen.
  Ex:
```JS
  var upper = 10000;
  var randomNumber = getRandomNumber(upper);
  var guess;
  var attempts = 0;

  function getRandomNumber(upper){
    return Math.floor(Math.random() * upper) + 1;
  }

  while( guess !== randomNumber){
    guess = getRandomNumber(upper);
    attempts += 1;
}
document.write("<p>The random number was : " + randomNumber + "<p>");
document.write("<p>It took the computer " + attempts + " attempts to get it right.</p>");
```
Do While Loop:

Do while loops are basically an extension of while loops. The main difference being that a do while loop always executes at least once. This is because the condition isnt tested until after the code block.
A do while loop is used to bring an alert to the screen, generally asking for information. If that information is supplied correctly, then the code block is finished running. If not then the alert repeats until the info is supplied.
Here's the basic structure of a do while loop:

do{

}while()

Lets write a program that generates a random number for a user to guess, then writes the number to the screen as well as how many tries it took to guess.
Ex:
```JS
var randomNumber = getRandomNumber(upper);
var guess;
var guessCount = 0;
var correctGuess = false;

function getRandomNumber(upper){
var num = Math.floor(Math.random() * upper) + 1;
return num;
}

do{
    guess = prompt("I am thinking of a number between 1 and 10. What is it?")
    guessCount += 1;
    if(parseInt(guess) === randomNumber){
        correctGuess = true;

    }
}while( ! correctGuess)
document.write("<h1>You guessed the number!</h1>")
document.write("It took you " + guessCount + "tries to guess the correct number!");
```

For Loops:

For loops perform the same task as while and do while loops, with the difference being that for loops execute a particular number of times.
Below is an example of a for loop that adds a total number of 10 div's to a web page:
Ex:
```JS
var html = " ";

for (var i =1; i <= 10; i += 1){
  html += "<div>" + i + "</div>";
}
document.write(html);
```
Break Statements:

We know that if a loop doesn't eventually evaluate to "false" or reach a loop limit, then we have an endless loop, which is useless/detrimental to your code. Sometimes however, it is necessary that we give a variable the value of "true". We can do this and still stop our code from running appropriately by using what is know as a BREAK STATEMENT.
Ex:
```JS
var randomNumber = getRandomNumber(10);
var guess;
var guessCount = 0:
var correctGuess = false;

function getRandomNumber(upper){
var num = Math.floor(Math.random() * upper) + 1;
return num;
}

while (true){
    guess = prompt("I am thinking of a number between 1 and 10. What is it?")
    guessCount += 1;
    if(parseInt(guess) === randomNumber){
        correctGuess = true;
        break;
    }
}
if (correctGuess){
document.write("<h1>You guessed the number!</h1>")
document.write("It took you " + guessCount + "tries to guess the correct number of: " + randomNumber);
}
else{
    document.write(<h1>"Sorry. You did not guess the correct number.</h1>");
}
```
Arrays:

Arrays are data structures, meaning that they are used to organize and store data. But more than this, Arrays are variables that can hold multiple sets and types of data. An array can hold integers, strings, single digits, boolean values and even other arrays. Arrays are flexible because you can add or remove values from it as the program runs, unlike variables which have a fixed value.
Here's how to write an array:
Ex:
```JS
var shoppingList = [
    'carrots',
    'milk',
    'eggs'
];
```
Accessing items within an Array:

You can select an item from an array by calling its number within the list. It is important to remember that the list begins counting from zero.
Here's how you call an item from an array:
Ex:
```JS
alert( groceries[0] );
```
Above, we specified a way to access the data in the form of "alert", we specified the array we want to access "groceries", and then we put in square brackets next to our array the data's item number that we wan to access.
Should you try to access an item number that's too high for an array, it will return an error of "undefined".

Adding data to an array:

We can add data to an array by using the "numbers.length" keyword.
Ex:
```JS
var numbers = [ 1, 2, 3, 4, 5, 6 ];
numbers[numbers.length] = 9;
alert(numbers);

returns:
1, 2, 3, 4, 5, 6, 9
```

The above code will tack on the number 7 to the end of the array. This is because numbers.length counts to the end of the list and then adds an additional item code number, thereby creating a new space for a new entry.
```JS
numbers[numbers.length] = 9; //translates to
/* numbers[6] = 9; */
// Indexes: 0-5, actual length: 6
```

There are many different methods of adding data to an array.
The "push" method, for instance, allows you to tack on one or more items to an array.
Here's an example of using the 'push' method.
Ex:
```JS
var numbers = [ 1, 2, 3, 4, 5, 6 ];
numbers.push(7, 8, 9);
```
This method, much like the .length method, will tack on a value to the end index of your array. You can add multiple values by separating them with a comma within the parenthesis.

There are also methods you can use to add a value to the very beginning index of your array. The value you add, in other words, will have an index of zero. You can do this by using the '.unshift' method.
Ex:
```JS
var numbers = [ 1, 2, 3, 4, 5, 6 ];
numbers.unshift( 9 );

// returns: 9, 1, 2, 3, 4, 5, 6
```
Removing Items from an Array:

Just as important as adding to an array, it is necessary that we can subtract values from an array list as well.
A method we can use to do this is with the "pop" keyword. It is the opposite of the "push" method. Where the push method adds a value to the end of an array, the pop method removes a value from the end of an array list.
Ex:
```JS
anArray.pop()
```
Another way we can subtract a value from an array is the "shift" method. This method removes a value from the very beginning of the list (the 0 index).
Ex:
```JS
anArray.shift()
```
Combining Loops and Arrays:

Sometimes you want to run an array for a specified amount of cycles or until a particular criteria is met. You would achieve this by looping an array.
Ex:
```JS
var students = ["Dan", "Tom", "Greg", "Tim"];
for (var i = 0; i < students.length; i += 1){
    console.log(students[i]);
}
```
The above code runs an array containing four names. the "students.length" method returns the current length of the array index. Because it is possible for people to come and go from the list, the count must remain fluid; the ".length" method is how we achieve this. var i = 0 starts our loop count at 0. i < students.length stops the loop count when it has reached the current array index length.  i += 1 adds one to the loop count each time it runs. console.log(students[i]); logs the total number of students in the array index list to the console by using the variable "i" to count and return the names off of the array index.

Useful Array Methods:

.join:
Returns an array's database as a string with all the items in it, separated by a supplied character like a comma or colon, even a letter. On top of that, you can also pass multiple characters together such as a space and a comma. This is a great way to display all the contents of an array on a single line.

Ex:
```JS
var dayInWeek = ['monday', 'turesday', 'wenesday', 'thursday', 'friday', 'saturday', 'sunday'];

var daysString = daysInWeek.join(',');

.concat:
Adds one list to another. So you can take two array lists and combine them into one new list. Simply name the array you want listed first in the new variable.

var dayInWeek = ['monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday', 'sunday'];

var firstThreeMonths = ['January', 'February', 'March'];

var daysAndMonths = daysInWeek.concat(firstThreeMonths);
```
.indexOf:
Searches for a particular supplied value in an array list.
For example, you could use indexOf to see if the word 'apple' is in an array. If the value you are searching for is present in the array, then .indexOf returns it's numerical position within the array list. If the value you are searching for doesnt exist within the array list, then it returns a value of -1.
Ex:
```JS
 var fruit = ['Apple', 'Orange', 'Clementine'];

 var position = fruit.indexOf('Apple');
```
Building a Basic Program:

Lest build a program that stores the contents of a grocery store and allows a user to search for what is in stock.
Ex:
```JS
var inStock = ['milk','eggs', 'bread', 'tofu', 'cookies', 'cheese', 'meat', 'potato', 'carrots', 'tasty javascript', 'beer', 'scotch', 'ultra jet', 'whiskey', 'mentats'];
var search;
function print(message){
    document.write('<p>' + message + '</p>');
}

while (true){
    search = prompt ("Search for a product in our store. Type 'list' to show all of the items in the store, and 'quit' to exit the search.");
}
search = search.toLowerCase();
if (search === 'quit'){
    break;
} else if (search === 'list'){
    print(inStock.join(', '));
} else{
    if (inStock.indexOf(search) > -1){
    print("Yes, we have" + search + "in stock.");
    } else{
        print(search + " is not in stock.");
    }
}
```
Two Dimensional Arrays:

Arrays can hold many types of values; strings, words, characters, numbers and boolean values. It can contain any combination thereof. But even this isnt all that arrays can contain. Arrays can even contain other arrays. In fact, you can create an array that is comprised of nothing but other arrays!
This is called a two-dimensional array.
Ex:
```JS
var grades = [
    [80, 79, 72, 90],
    [63, 100, 90, 98],
    [78, 60, 90, 100]
];
```
It is as simple as adding arrays within an master array. Each new list added to this array is still assigned an identification number, starting at 0. This allows us to access each list individually. Rather than each number in the master array, each array list has an ID number.
In order to select a particular value from a particular list from a two-dimensional array, you use another set of square brackets to locate it, sort of like coordinates. The array index number comes first and then the secondary index number for the value you want to access.
Ex:
```JS
print(grades[0][3]); //returns 90

document.write(grades[2][1]); //returns 60
```
PRACTICE PROGRAM: JS QUIZ:
```JS
//JS QUIZ PRACTICE

var qAndA = [
    ['How many stars are on the American flag?', 50],
    ['What day in July is Independence Day?', 4],
    ['How many legs does a spider have?', 8],
];
var correct = [];
var wrong = [];
var correctAnswers = 0;
var question;
var answer;
var response;
var html;

console.log("checkpoint A");
function print(message) {
  console.log("in print()");
  var outputDiv = document.getElementById('output');
  outputDiv.innerHTML = message;
}
console.log("checkpoint B");
function buildList(arr){
  console.log("in buildList()");
  var listItem = '<ol>';
  for (var i = 0; i < arr.length; i += 1){
    listItem += '<li>' + arr[i] + '</li>';
  }
  listItem += '</ol>';
  return listItem;
}

console.log("checkpoint C");
for (var i = 0; i < qAndA.length; i += 1 ){
  console.log("in for loop");
  console.log("for loop i:");
  console.log(i);
  question = qAndA[i][0];
  answer = qAndA[i][1];
  response = parseInt(prompt(question));
  if (response === answer){
    correctAnswers += 1;
    correct.push(question);
  }else{
    wrong.push(question);
  }
}

console.log("checkpoint D");
html = "You got " + correctAnswers + " questions correct!";
html += '<h2>You got these questions correct:</h2>';
html += buildList(correct);
html += '<h2>You got these questions wrong:</h2>';
html += buildList(wrong);
print(html);
```
Objects:

JavaScript is a Object Oriented Programming Language. As a short definition, an object is something that has properties and methods. A property is like a variable that belongs to the object and a method is something that the object can do or can be done to the object.
An array, for example, is an object. It has a property named .length, and it also has many methods that lets you do something with or to the array. As a more advanced programmer, you can even create your own objects! For now, we will focus on storing and moving data.
JS objects let you store data in what are called key vale pairs or property value pairs. a key, or property name, is kind of like a variable name, and a value is like the value of that variable. So you can think of an object like a single item that holds multiple variables.
Heres how to create an object:
Ex:
```JS
var student = {
    name: "Dan",
    grades: [100, 90, 99, 100]
};
```
We begin by assigning whats called an object literal to a variable. The curly braces represent an object. Whereas square brackets indicate an array,  curly braces create an object.
Within the braces you add a property name, also known as a key, followed by a full colon, and then a valid value key like a string, number, boolean, or array. You can separate each property name value pair with a comma. I did this above and then added in an array of my grades.
Here's another example of an object, slightly larger:
Ex:
```JS
var person = {
    name: "Dan",
    country: "US",
    age: 26,
    student: true,
    skills: ['JavaScript', 'HTML', 'CSS', 'Python']
};
```
Objects are similar to arrays in that they both allow you to store multiple pieces of data within a single variable. The difference is that arrays use an index number to catalogue and access an array item, whereas objects use a key to access their properties. There are also two ways we can access an object's items two different ways:
Ex:
```JS
var person{
    name: "Dan",
    age: 26
};
alert( person['name'] );
```
Above is an example of the first way we can access an object's items. But there is another, easier and more common way to access properties of an object called .notation:
Ex:
```JS
var person{
    name: "Dan",
    age: 26
};
alert( person.name );
```
Dot notation is the most common way of pulling data out of an object. Dot notation can also assign a name key a different value or add another name key and value all together. We do this like so:
Ex:
```JS
var person{
    name: "Dan",
    age: 26
};
person.name = 'Emily';
person.country = 'US';
```
Lets start using Objects. Below is a small program that prints a message out to an HTML document, pulling some of the information it prints from an object.
Ex:
```JS
var person = {
  name : 'Sarah',
  country : 'US',
  age : 35,
  treehouseStudent : true,
  skills : ['JavaScript', 'HTML', 'CSS']
};

function print(message) {
  var div = document.getElementById('output');
  div.innerHTML = message;
}

var message = '<p> Hello. My name is ' + person.name + '.</p>';
message += '<p> I live in the ' + person.country + '.</p>';
person.name = 'Goobersnoochy';
message += '<p> But I wish my name was ' + person.name + '.<p>';
person.age += 1;
message += '<p>My age is now ' + person.age + '.</p>';
message += person.skills.join(", ") + '</p>';

print(message);
```
Accessing Objects:

Because arrays list their data with a numerical system, it is easy to access them using a for loop, as shown earlier in these notes. You would not use this method to pull data out of an objects however. To access an object you need to use a special kind of loop called a for-in loop. A for-in loop loops through each key or property name contained within an object.
You write one like this:
Ex:
```JS
for ( var key in object ){
    // do something
}
```
The code above allows us to access the contents of a specified object. We name that object in the code right after the 'for'.
Lets look at a for-in loop that does something:
Ex:
```JS
var student = {
    name: "Dave",
    grades: [80, 85, 90, 70]
};
for ( var key in student ){
    console.log(key);
}
```
The code above would print out the property names, name and grade to the console.
It is important to note that the 'key' in 'var key in object' is just a variable name and can be swapped out for other commands.
Lets look at how to access specific parts of an object:
Ex:
```JS
var student = {
    name: "Dave",
    grades: [80, 85, 90, 70]
};
for ( var propName in student ){
    console.log(propName);
}
```
This code will now only give you access to the key names.
To access to the data in the object's key names, use square bracket notation to access the key names:
Ex:
```JS
var student = {
    name: "Dave",
    grades: [80, 85, 90, 70]
};
for ( var propName in student ){
    console.log(student[propName])
};
```
It is important to note that you cannot use dot notation in lieu of square bracket notation in this case.
Lets see a more in depth use of the for-in loop:
Ex:
```JS
var person = {
    name: "Dan",
    country: "US",
    age: 26,
    student: true,
    skills: ['JavaScript', 'HTML', 'CSS', 'Python']
};

for (prop in person){
  console.log(person[prop])
};
```
Combining Arrays and Objects:

It is common practice to combine the two storage devices (Arrays and Objects) to create an even more powerful data storing device. You can do this by creating an array of objects.
Lets look back at the quiz program we made earlier in these notes.
```JS
//JS QUIZ PRACTICE

var qAndA = [
    ['How many stars are on the American flag?', 50],
    ['What day in July is Independence Day?', 4],
    ['How many legs does a spider have?', 8],
];
var correct = [];
var wrong = [];
var correctAnswers = 0;
var question;
var answer;
var response;
var html;

console.log("checkpoint A");
function print(message) {
  console.log("in print()");
  var outputDiv = document.getElementById('output');
  outputDiv.innerHTML = message;
}
console.log("checkpoint B");
function buildList(arr){
  console.log("in buildList()");
  var listItem = '<ol>';
  for (var i = 0; i < arr.length; i += 1){
    listItem += '<li>' + arr[i] + '</li>';
  }
  listItem += '</ol>';
  return listItem;
}

console.log("checkpoint C");
for (var i = 0; i < qAndA.length; i += 1 ){
  console.log("in for loop");
  console.log("for loop i:");
  console.log(i);
  question = qAndA[i][0];
  answer = qAndA[i][1];
  response = parseInt(prompt(question));
  if (response === answer){
    correctAnswers += 1;
    correct.push(question);
  }else{
    wrong.push(question);
  }
}

console.log("checkpoint D");
html = "You got " + correctAnswers + " questions correct!";
html += '<h2>You got these questions correct:</h2>';
html += buildList(correct);
html += '<h2>You got these questions wrong:</h2>';
html += buildList(wrong);
print(html);
```
We are going to re-write this quiz, turning the double arrays into an array of objects. All we have to do is get rid of the square brackets and replace them with curly braces, then add property names.
```JS
//JS QUIZ PRACTICE, RE-WRITTEN:

var qAndA = [
    {
    question: 'How many stars are on the American flag?',
    answer: 50},
    {
    question: 'What day in July is Independence Day?',
    answer: 4},
    {
    question: 'How many legs does a spider have?',
    answer: 8}
];
var correct = [];
var wrong = [];
var correctAnswers = 0;
var question;
var answer;
var response;
var html;

console.log("checkpoint A");

function print(message) {
  console.log("in print()");
  var outputDiv = document.getElementById('output');
  outputDiv.innerHTML = message;
}
console.log("checkpoint B");

function buildList(arr){
  console.log("in buildList()");
  var listItem = '<ol>';
  for (var i = 0; i < arr.length; i += 1){
    listItem += '<li>' + arr[i] + '</li>';
  }
  listItem += '</ol>';
  return listItem;
}

console.log("checkpoint C");

for (var i = 0; i < qAndA.length; i += 1 ){
  console.log("in for loop");
  console.log("for loop i:");
  console.log(i);
  question = qAndA[i].question;
  answer = qAndA[i].answer;
  response = parseInt(prompt(question));
  if (response === answer){
    correctAnswers += 1;
    correct.push(question);
  }else{
    wrong.push(question);
  }
}

console.log("checkpoint D");

html = "You got " + correctAnswers + " questions correct!";
html += '<h2>You got these questions correct:</h2>';
html += buildList(correct);
html += '<h2>You got these questions wrong:</h2>';
html += buildList(wrong);
print(html);

Take note that along with changing the arrays into array-objects, we also have to change the notation of our for loop. Rather than:

 question = qAndA[i][0];
 answer = qAndA[i][1];

we change the notation to:

  question = qAndA[i].question;
  answer = qAndA[i].answer;
```
This is the notation to pull information out of an object.

JSON:

JSON stands for JavaScript Object Notation. JS objects provide a structured way to store data, as we know. It is such a good system, it is one of the most widely used data storing systems on the web. A technology called AJAX is often used in conjunction with JSON to exchange data between a server and a web browser.
AJAX would make the request for something off of a server (say pictures off an image hosting site like flickr). The information from the server will be delivered in JSON format which can easily be converted into a JavaScript object and used to display those images on a webpage.
Web servers also exchange information between each other using JSON format. For example, you can create a program using Ruby, Python, PHP or Java that runs on your web server and talks to the social media site twitter.

JAVASCRIPT AND THE DOM:

Interactivity can be broken down into three basic actions: selecting elements on the page, manipulating elements and listening for user actions. This is as simple as finding something to click, clicking it, and something else happening as a result of the click. Not all selected elements will be manipulated, however. Sometimes you will want to listen for what a user is doing. In an Excell spreadsheet for example, when a user clicks on a cell, the JS selects the cell and then waits and listens for user input.

JavaScript's global environment is full of controls your code can use to make things happen. These controls come in the form of JavaScript objects and functions. Inside a browser, they allow your code to see and manipulate web pages.

Heres an example of connecting a JS function to a HTML web page:

The HTML has to have the proper setup to accept the JS script.
It looks like this:
Ex:
```JS
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript and the DOM</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1 id="myHeading">JavaScript and the DOM</h1> //These id's are very important because they allow you to target a specific section of your site in the JS script.
    <p>Making a web page interactive</p>
    <script>../myJsFile.js</script> // This establishes a link between my JS file and my HTML document.
  </body>
</html>
```
Okay, so that's your HTML document and it's set up to accept JS. Below is an example script. We will write a really simple function that changes the title of our h1 element.
Ex:
```JS
documnet.getElementById('myHeading').style.color = 'red'
```
The code above targets the HTML document, then we use the getElementById method to target our specific element of which we specify next within the parentheses. Finally we provide an action to take using dot-notation. We target the style of the h1 element, then it's color and finally we change the color to red.
This is a common sequence when controlling a page with JS. Take note that we just overwrit a webpage's CSS using JS. This is a taste of how powerful and versatile JS can be.

If we wanted to target something that is two words long, we would use camel case to target it.
Ex:
```JS
documnet.getElementById('myHeading').style.backgroundColor = 'black'
```
DOM is the Document Object Model and it is central to creating a website containing JS functionality. The document is a global object representing the HTML and content of a web page. We call it a global object because it contains everything we see on a page.
The DOM is like a map that JS can use o navigate a web page. Unlike a map, a DOM is a live entity subject to change whenever JS manipulates it. The DOM represents a web page as a tree-like structure. In HTML, we always have a head and body, which contains lots of other elements. The head may contain a title element and the body a heading, paragraph and a few div elements, for example. IF you have a <ul> element(s), it will also have <li> items within it. The point is that these nested elements can be thought of as a tree.
The document element, or 'node' would be thought of as the root node of the tree. The head and body nodes sprout like branches leading to other branches. At the top of the tree are leaves, like a heading element or list item nodes. The leaves represent the most deeply nested tags of an HTML page. In Computer Science it is important to note that trees like this are drawn upside down, more like a family tree, meaning that the roots are at the top, branches in the middle and leaves at the bottom. Relationship between nodes are even described in family-like terms.
For example, the body is the parent of the <h1>, <p>, and <ul> nodes. The <li> nodes are all children of the <ul> node and other <li> nodes are siblings of each other. Similarly the head and body are siblings as well.
This tree-like structure and family relationship model is used by JS to alter the structure of webpages.

So lets get into how to "physically" program events, make JS listen and manipulate our selections:
Ex:
```JS
const myHeading = document.getElementById('myHeading');
//This targets the constant 'myHeading' then it targets a specific id within the document specified as 'myHeading'

myHeading.addEventListener('click', () => {
    myHeading.style.color = 'red';
});
 //This tells the heading element to start listening for browser events. Clicking, scrolling, mouse movements, etc. are all browser events. In this example we are telling JS to listen for a click in the header element. When that element is clicked, then the header turns red.
```
 Despite the above code being a common convention in JS, sometimes we can achieve the same result in a different way. In the following example we will change the header color again, but this time we will do it by clicking a button instead.
 Ex:
```JS
// the first step is to create a button to click. We do this by going into our HTML document and creating a button, as seen below:

<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript and the DOM</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1 id="myHeading">JavaScript and the DOM</h1>
    <p>Making a web page interactive</p>
    <button id='myButton'>Make heading red</button>
    <script../myJsFile.js></script>
  </body>
</html>

const myHeading = document.getElementById('myHeading');
const myButton = document.getElementById('myButton');

myButton.addEventListener('click', () => { //Now that we want to listen for a click on the button for a change in color, we have to make sure we tell the event listener to listen for 'myButton', rather than 'myHeading'
    myHeading.style.color = 'red';
 });
```
Thats a good bit of code in the above section. Now we will add a text input that we can manipulate.
We begin by creating a section for the input itself in our HTML document like so:
Ex:
```JS
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript and the DOM</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1 id="myHeading">JavaScript and the DOM</h1>
    <p>Making a web page interactive</p>
    <input type="text" id="myTextInput">
    <button id='myButton'>Make heading red</button>
    <script src="../myJsFile.js"></script>
  </body>
</html>


//Then we write the code in our JS file, much like what we did to change the header color those previous times:
Ex:
const myHeading = document.getElementById('myHeading');
const myButton = document.getElementById('myButton');
const myTextInput = document.getElementById('myTextInput');

myButton.addEventListener('click', () => { //Now that we want to listen for a click on the button for a change in color, we have to make sure we tell the event listener to listen for 'myButton', rather than 'myHeading'
    myHeading.style.color = 'red';
 });

//The code above will allow you to create a text input field within your HTML document. Anything written within the field will be stored as a value for that id and will be printed out to the console with the correct command (myTextInput.value)
```
But lets take this one step further. We are now going to make it so that any recognized value typed into the field will change the color of the header text. The change is relatively small and simple, but has a lot of power behind it.
Ex:
```JS
const myHeading = document.getElementById('myHeading');
const myButton = document.getElementById('myButton');
const myTextInput = document.getElementById('myTextInput');

myButton.addEventListener('click', () => {
    myHeading.style.color = myTextInput.value; //Now we replace 'red' with our id name. Because our element is now linked to the style and color of 'myHeading', we can now input a color and have it reflected in our HTML window when the button is clicked.
 });
```

SELECTING MULTIPLE ELEMENTS WITH NO ID

Sometimes you will want to select an element(s) that don't have id's.
For example, you might want to select all of the items inside of an ordered or unordered list. You wouldn't write an ID for each list item, because it might be a very long list. You do this by using another dot-notation called ".getElementsByTagName()". This method of targeting is very similar to the ".getElementById" method, but differs in a big way; with the plural word "elements". This method returns a collection of elements. Accessing the items inside the "array" of returned elements is done just like accessing the items of a regular array; by using the list item's index number. Alternatively you can write a loop that goes through all of the returned elements in a list.
In the example below we will target all of the paragraph tags in an HTML document.
Ex:
```JS
const myParagraph = document.getElementsByTagName();

//to access a specific paragraph tag within HTML, you select it like so:

myParagraph[0];

//now lets turn the paragraph to blue:

myParagraph[0].style.color = 'blue'

//now lets select an entire list of items and change their color:

const myList = document.getElementsByTagName('li');
for (let i = 0; i < myList.length; i += 1){
    myList[i].style.color = 'purple';
}
```
SELECTING ELEMENTS WITH THE SAME CLASS NAME:

We will be working with the notation "document.getElementByClassName()" method. Classes are used to select and style in CSS.
Say that we had a list of items that are purple, but there's a problem. Within this list are apples, oranges and bananas as well, which are decidedly not purple. We want to change the color of these non-purple items to red, so that they stand out as erroneous within our list.
We go about doing this by first assigning a class to our list items that are not purple. Lets name it something appropriate like "errorNotPurple".
Ex:
```JS
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript and the DOM</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1 id="myHeading">JavaScript and the DOM</h1>
    <p>Things that are purple:</p>
    <ul>
        <li>grapes</li>
        <li>amethyst</li>
        <li>lavender</li>
        <li class="error-not-purple">apples</li>
        <li>plums</li>
        <li class="error-not-purple">oranges</li>
        <li class="error-not-purple">bananas</li>
    </ul>
    <script src="../myJsFile.js"></script>
  </body>
</html>

Next, we create a new constant out of our new class and then plug it into the .getElementsByClassName method and then into the for loop.
Lets incorporate our code to turn our list purple as well, and then turn the erroneous items red.
Ex:

const myList = document.getElementsByTagName('li');

for (let i = 0; i < myList.length; i += 1){
    myList[i].style.color = 'purple';
}

const errorNotPurple = document.getElementsByClassName('error-not-purple');

for (let i = 0; i < errorNotPurple.length; i += 1){
    errorNotPurple[i].style.color = 'red';
}

//The above code will change the color of all of the items in the list to purple, before turning our selected items to red. However, this happens faster than we can really track with our eyes.
```
Using CSS Queries to Select Page Elements:
```JS
document.querySelector()
document.querySelectorAll()
```
The above selectors are the most flexible selectors we have encountered thus far. They will accept ID's, classes, tag names, and more.
Lets begin by selecting a <li> tag with querySelectorAll:
Ex:
```JS
document.querySelectorAll('li')

//This selector will return all of the list items in the document. If we were to use the document.querySelector() because it is a singular selector, it would only print the first <li> it encounters in the document to the console.
```
Lets select our Header element by it's CSS selector "myHeading".
Ex:
```JS
document.querySelector('#myHeading')
```
Lets select the <li> by the class "errorNotPurple".
Ex:
```JS
document.querySelectorAll('.error-not-purple')
```
We can even select by HTML attribute.
Lets first go into our HTML document and create an attribute to select. In this case it will be title="label"
Ex:
```JS
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript and the DOM</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1 id="myHeading">JavaScript and the DOM</h1>
    <p title="label">Things that are purple:</p>
    <ul>
        <li>grapes</li>
        <li>amethyst</li>
        <li>lavender</li>
        <li class="error-not-purple">apples</li>
        <li>plums</li>
        <li class="error-not-purple">oranges</li>
        <li class="error-not-purple">bananas</li>
    </ul>
    <script src="../myJsFile.js"></script>
  </body>
</html>

//now lets select the attribute

document.querySelector('[title=label]')
```
We technically dont even have to use selectors, id's, or class names to select elements. We can also use a CSS pseudoclass called "nth child".
Ex:
```JS
const evens = document.getElementsByClassName('li:nth-child(even)');

for (let i = 0; i < evens.length; i += 1){
    evens[i].style.color = 'red';
}

//All I did above was take copy the "error-not-purple" code and replace the "error-not-purple" with "evens" and changed out what the getElementByClassName is targeting. Now it is targeting the children housed within "li" and then from those children, it selects the evens from the list. You could also change the "even" to "odd" and the inverse would be selected. The nth-child selector begins counting from 1, rather than 0.
```
