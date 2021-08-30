# Scripting Guide
Guide to Scripting: Learning the Very Basics of GSC Syntax

### About the Author(s):
*NateSmithZombies:*
My name is Nate Smith aka natesmithzombies. I served on the Alpha Mod Tools test team for Call of Duty Black Ops III prior to its open Beta in 2016. I am a self taught scripter in the GSC language, but I have had the opportunity to learn from many great scripters in the modding community (special thanks to harryb021 for his countless hours explaining syntax). I am not a "know it all" when it comes to scripting, so feel free to notify me of your suggestions and corrections: natesmithzombies@gmail.com. Now lets get started!

Need to get ahold of me? Follow me on twitter: [@NSmithZombies](https://twitter.com/NSmithZombies))

*Holofya:*
I'm pretty new in the BO3 and zombie modding community but I would say scripting is my strongest aspect in it. I don't have any major projects but most of my work has been on scripts to help others. (I also made a custom perk that no one uses and am porting Afterlife)

Discord: Holofya#7133

---

## Learning the Basics

### Data Types
COD script is a derivative of 'C code', with a lot of changes that make scripting easier. Below is a list of the most common data types you will use in COD script aka GSC code:

__Int aka Integer:__ 
An int is exactly what it is in math, a whole number. Examples: 1, 52, 97, 4

__Float:__
A float is another number, but unlike an int it has decimals. Examples: 5.17549435, 6.57549836

__String:__
A string is a character or set of characters that make up a word or phrase. Examples: "this is a string", "321 String", "strings are cool :)"

__Boolean:__
A boolean can have two values, true (same as 1) or false (same as 0). Examples: true, 1, false, 0

__Array:__
An array isn't really a data type but it is a data structure. An array is a collection of any data type. Arrays are a bit confusing to understand and will have a dedicated section. They are essential!

__Comments:__
A comment definitely isn't a data type but it belongs in this section anyway. Comments are lines in code starting with // that are not read by the compiler. Use these to make notes to yourself in script.

---
## Using Data Types to Make Variables (Declaring a Variable)

Defining variables correctly is very simple, but in order to define variables correctly you must understand how code executes. I will break down varibles into 2 types:

__Local variable:__
A variable that can only be referenced in the function it is created in (more about functions in a second). Example: `teddys_to_shoot = 3;`

__Global variable:__
A variable that can be called anywhere in a script or in other scripts. Example: `level.teddys_to_shoot = 3;`

Note the difference between a local and a global variable. Notice the local variable does not have a 'level.' in front of it. Defining a variable on the "level" allows for it to be referenced anywhere in script. Also note that variable declarations end with a ';'. A ';' tells the compiler to stop reading and start reading again. This is the most common mistake of new programmers. If you ever get an error like "unexpected paranthesis" or "unexpected ." this is a tell tale sign of a missing ';'.

> **IMPORTANT:** some variables may be considered an `"ent"` or `"entity"`. You need to understand the idea of an entity early or you will run into a "g_spawn" error. An `ent` is a spawned script_model or a script_model placed in radiant. Any type of animated model or manipulated model in script is an `ent`. **ALWAYS** delete an ent after you are done using it with the syntax: ent delete(); where ent is the entity variable. 

> **NOTE:** In WaW triggers also act as entities, but this is no longer the case for Bo3. Triggers will be covered in a new wiki section on level manipulation. You should always treat a trigger as an ent regardless of the game you are working with. 

---

## Quickly Modifying Numerical Variables

The basic way to modify a numerical variable (int or float) is simply to take that variable and perform a mathematical operation on it `+, -, *, /`. But you can also use one of the shortcuts for modifying a numerical variable:
-  `++`: increments the variable by 1
-  `--`: decrements the variable by 1
-  `+=`: adds the value that follows the equal sign to the value of the variable before the plus sign
-  `-=`: subtracts the value that follows the equal sign from the value of the variable before the minus sign
-  `*=`: multiplies the value that follows the equal sign by the value of the variable before the plus sign
-  `/=`: divides the value of the variable before the plus sign by the value that follows the equal sign
Each of these operators save the value of the operation to the variable before the operator.

For example, this:
``` php
i = 0; // declare an int "i", value of i = 0
i = i + 1; // add 1 to the current value of i, value of i = 1
i = i - 1; // subtract 1 from the current value of i, value of i = 0
i = i + 25; // add 25 to the current value of i, value of i = 25
i = i - 12; // subtract 12 from the current value of i, value of i = 13
i = i * 3; // multiply the current value of i by 3, value of i = 39
i = i / 13; // divide the current value of i by 9, value of i = 3
```
is the same as:
``` php
i = 0; // declare an int "i", value of i = 0
i++; // add 1 to the current value of i, value of i = 1
i--; // subtract 1 from the current value of i, value of i = 0
i += 25; // add 25 to the current value of i, value of i = 25
i -= 12; // subtract 12 from the current value of i, value of i = 13
i *= 3; // multiply the current value of i by 3, value of i = 39
i /= 13; // divide the current value of i by 9, value of i = 3
```
If you make long variable names to be descriptive, these shortcuts make modifying those values much nicer, but they are helpful to know and use in general.

---

## Using Variables to Make Functions

Now that we understand how data types make up variables, it is time to make up a function out of variables. I will provide a simple example of a function below (This function would work in BO3 but not in WaW. I will explain further in a minute.) 

``` php
      function example_function()
      {
          iprintlnbold("This is an example function"); 
          teddys_to_shoot = 3; 
          iprintlnbold( "You have " + teddys_to_shoot + " Teddy Bears to Shoot" ); 
      }
```

In the above example we first define a function by writing '**function**' in front of the function name. Then we name our function `example_function()`. This function has no **arguments** that need to be passed into it. We open the function with an opening **brace**; then we utilize an **engine function** to print text to the screen; then we define our local variable; and then we conclude the function with an additional **engine function** and a closing **brace**. See the definitions of the bolded words below:

- **arguments**: data types or structures that can be passed into a function. Know that the only way data types can be transfered into a function are through the use of `self` and function arguments. This will be explained in the next section.
- **function**: this statement must be written in front of an function in gsc/csc. Just keep that in mind when debugging errors in script. (This is specific to BO3.)
- **engine function**: these are predefined functions written in gsc/csc code. A list of engine functions and their functionality is listed in the provided documents for the mod tools. Open `root\docs_modtools\bo3_scriptapifunctions.htm` in your web browser to read what each function does. Here is a copy and paste example of "iprintlnbold" used in the above example:


``` php
void IPrintLnBold(<text>)

	[MANDATORY] <text> text to be written
	CATEGORY: 
	CLIENT/SERVER: Server
	SUMMARY: Write bold line to the screen
	EXAMPLE: IPrintLnBold( "Mitchell!" )
```
- **brace**: these are curly braces `{ }`. Any function statement or logical statement needs curly braces to enclose its set of operations. Logical statements will be covered in another section. Arrays use square braces `[ ]`, to be covered later.

--- 

## Using Functions to Their Fullest Potential: Passing Data Types and `self`

Earlier I mentioned passing data types and information to a function through the use of `self` and `arguments`. In order to utilize a function to its fullest potential we need to understand how to pass information and data to a function, and it is important to interpret the data we are sharing and receiving. Check out this example:

``` php
function main()
{
	average_exam_grade = take_an_average_of_3( 80, 90, 100 ); 
	iprintlnbold( "Your Average Exam Grade Is: "+average_exam_grade );
}

function take_an_average_of_3( num1, num2, num3 )
{
	sum_of_nums = num1 + num2 + num3; 
	average_of_nums = sum_of_nums/3; 
	return average_of_nums; 
}
```

This is an example we can all relate to, so this shouldn't be too hard to understand. When scripting there is always a "main" function, and in some languages the "main" function has to actually be named "main" for the code to work. So in this main function we are accomplishing some averaging of your 3 exam grades. We use **arguments** and pass them to the function "take_an_average_of_3". If we look at said function, we see in its **function definition** that it wants 3 **arguments**: num1, num2, and num3. It then takes those arguments and adds them together; then divides by 3. Then we **return** the average. Notice that you can return a data type to a string using the +variable_name after you write the string in iprintlnbold. This is very useful to know!

- **function definition**: this is how a function is defined. A function definition will contain the word "function" then the function name, followed by ( ) containing arguments seperated by commas. Again this is specific to Bo3.
- **return**: this is an operator that does exactly what it sounds like it does; it returns a data type. Returns will be discussed in another section

Now lets take a look at a similar example but with a new concept: the idea of `self`. Notice how the function is different!

``` php
function main()
{
	players = getplayers(); // getplayers is an engine function, see bo3_scriptapifunctions.htm
	host_player = players[0]; // players is an array, for now know that players[0] is the host
	host_player take_an_average_of_3( 80, 90, 100 ); 
	iprintlnbold( "The Host's Average Exam Grade Is: "+host_player.average_of_nums );
}

function take_an_average_of_3( num1, num2, num3 )
{
	sum_of_nums = num1 + num2 + num3; 
	average_of_nums = sum_of_nums/3; 
	self.average_of_nums = average_of_nums; 
}
```
This example is the heart of 'object oriented' programming. Let's explain what happened differently here than in the previous example. 

In this example we used an engine function to get the host of the game. Then we called the function "take_an_average_of_3" on the host player (I know we don't take exams in COD, but let's pretend haha). Now the host player is running the function "take_an_average_of_3". Because the function was called on the host, the host is *self* inside the function. Remember when we defined a global variable "level.teddys_to_shoot" at the beginning of the wiki? Now we are defining a variable on the player entity (the host player). A variable defined on an entity is called a field and is a property of that entity. "self.average_of_nums" is a new variable stored on the host player, just like how a level variable is stored on the level. As long as the host player exists, aka is defined, you can always reference this variable, given you have access to the host player. //Take a Second to Think//: This is why a level.variable is considered "global" because the level is always defined.

That might seem like a lot to take in, but re-read that above paragraph. It is **REALLY** important to understand.

---	

## If Statements: if, else if, else

If statements are a very crucial part of interpretting data in functions. It is never enough to just have variables in a function and that's it. If you find yourself saying, "I want this to happen `if` this is true" then you need if statements and/or logical statements. We can use **logical operators** to further narrow down and interpret our data from the game. Let's look at the exam average example again with some more tweaks:

``` php
function main()
{
	players = getplayers(); // getplayers is an engine function, see bo3_scriptapifunctions.htm
	host_player = players[0]; // players is an array, for now know that players[0] is the host
	host_player take_an_average_of_3( 80, 90, 100 ); 
	iprintlnbold( "The Host's Average Exam Grade Is: "+host_player.average_of_nums );
	if( host_player.average_of_nums >= 70 )
	{
	    iprintlnbold( "The host has a passing grade" );
	}
	else if( host_player.average_of_nums < 70 )
	{
	    iprintlnbold( "The host has a failing grade." ); 
	}
}

function take_an_average_of_3( num1, num2, num3 )
{
	sum_of_nums = num1 + num2 + num3; 
	average_of_nums = sum_of_nums/3; 
	self.average_of_nums = average_of_nums; 
}
```

Like before we are getting the host's average exam grades, but now we are checking if the host has passed. We check the host's average exam grade against a score of 70. `If` it is //greater than or equal to// 70 we print to screen that the host has passed. `else if` it is //less than// 70 we print that the host has failed. Note that only one of those logical operations will run on the host: whichever one is true. A list of the logical statements most commonly used are listed below:
- `if`: an if statement checks "if" the statement inside the ( ) is either true or false, and runs if the statement is true
- `else if`: this is always used after an `if` or an `else if`. This checks another statement if the previous `if` or `else if` is not true
- `else`: I like to think of an else statement as "if all else is false then do this". Like the `else if` an `else` needs to be after an `if` or an `else if` statement

`else if` and `else` are not necessary to have an if statement if you do not need them.

---

## Knowing How Logical Statements are Evaluated: Logical Operators ( &&, ||, <, >, ==, ! )

Logical statements check for a `boolean` which we defined earlier as a true or 1, false or 0. Logical Statements can also run functions inside them to check for a boolean. Logical statements are manipulated and evaluated by several **logical operators**. The main ones are listed below:
-  `&&` : this is an "and" operator. This will link two conditions, and if both of them are true, it will return a value of true. If either is false it will return a value of false.
-    `||`: this is an "or" operator. This will link 2 conditions, and if either of them are true, it will return a value of true. If both are false it will return a value of false.
-    `==` : this is the "is equal to" operator, it checks if two values are equal. It returns true if they are and false if they are not. e.g.: `if( grade == 100 ) iprintlnbold( "This is a perfect grade" ); `
-  `<` and `>`: less than and greater than, alternatively could be `<=` or `>=` for less than or equal to and greater than or equal to
-  `!` : the "not" operator. I use this one A LOT. Some also call it an "invert operator". What it does is inverts the evaluated statement or inverts the operator. A value of true becomes false and vice versa. Here are 3 examples: `if( grade != 100 ) iprintlnbold( "This is not a perfect grade" );` and `if( !isDefined( grade ) ) iprintlnbold( "The grade is not defined. The student didn't take the exam" );` and `if( !false ) iprintlnbold( "the value is true!" );`

**Some Pro Tips for Speed with Logical Statements**
You will notice scripters are lazy (all coders are). We don't like to type. Hell typing this wiki is killing me haha, but to get to the point there is a faster way to check if something is true or false. Take a look at the code below: 


``` php
      true_variable = 1; 
      false_variable = 0; 
      if( true_variable ) // This will evaluate because I set true_variable equal to 1 which is also true
          iprintlnbold( "The variable true_variable is true" ); 
      else // This wont execute
          iprintlnbold( "The variable true_variable is not true" ); 
      if( !false_variable ) // This is true. We invert the false value of false_variable to be true
          iprintlnbold( "The variable false_variable is false" );
      else 
          iprintlnbold( "The variable false_variable is not false" ); 
```
Notice that there are a few interesting things about the above code: a) the lack of braces after the logical statement and b) that there are is no `==` operator. I am evaluating the true_variable and false_variable in the logical statement and checking if that value is 1 or 0 aka true or false. Also braces are not needed in an if statement if the code below it is only 1 line. To help you understand further the code is rewritten below to do the same exact thing:


``` php
      true_variable = 1; 
      false_variable = 0; 
      if( true_variable == true ) // This will evaluate because I set true_variable equal to 1 which is also true
      {
          iprintlnbold( "The variable true_variable is true" ); 
      }
      else // This wont execute
      {
          iprintlnbold( "The variable true_variable is not true" ); 
      }
      if( false_variable == false )
      {
          iprintlnbold( "The variable false_variable is false" );
      }
      else 
      {
          iprintlnbold( "The variable false_variable is not false" ); 
      }
```

You can see the first block of code was much faster and cleaner to write. Chances are you are not getting paid to code, so use whichever code you find easiest to remember or understand. 

> **NOTE:** using comments (`// comments`) is a good way to make notes in your code. It might make sense today, but maybe not tomorrow.

----

## Arrays: The fastest way to store a family of Data Types

Sometimes you will find that you are making a family of variables that are very similar. This would be a tell tale sign to use arrays. Arrays are used A LOT by me and 3arc. Most people shy away from them at first because they seem scary, but trust me they are your best friend.

Arrays are a data structure (a way of storing data types), but they are declared in much the same way as other variables: `array = [];` this creates an empty array.

Let's do the all too familiar shootable teddy bear for a song example.

**Indices**
Lets start slow and talk about an array's index/indices. An index is a representation of a position within an array. //An index can be an integer or a string.// The advantage of a string index is that it can be directly referred. I use string indices when I make buildables because I may want to call a specific part from the array. The advantage of integer indices is that they are easily looped through in a for loop. Strings can also be looped through but it is a bit more complex. Lets show examples of an integer index VS a string index:

```php
      // Below is an engine function to get the script_models or triggers in game with KVPs targetname:shootable_teddy
      teddys_to_shoot = GetEntArray( "shootable_teddy", "targetname" );
      teddys_to_shoot[0]; // This is the first element in the array teddys_to_shoot
      teddys_to_shoot[1]; // This is the second teddy in the array
```

Notice that for an integer indexed array, that the array starts at the integer 0. So the 8th element would be index 7. It is confusing at first, but it is the way things are done in almost every coding language.

Now let's look at a string index. I will use an example that is not exact to Treyarch code, but is familiar.

``` php
      powerups = []; // anytime we are "forcing" an array we need to initialize the variable as an array
      powerups[ "full_ammo" ] = "Max ammo"; 
      powerups[ "nuke" ] = "Nuke"; 
```

The code above is doing nothing really but it helps you understand that the array "powerups" holds 2 elements: "Max ammo" which is stored at/with the index "full_ammo", and "Nuke" which is stored at/with the index "nuke".

When it comes down to it, you are going to have to study arrays. When I first learned to script I spent a lot of time reading 3arc scripts with limited guidance. This section will help you understand what an array is and what an index is, but the fine details you will need to study and practice. Take a look at the engine function GetArrayKeys to further understand how to loop through a string index as if it were an integer index.

---

## Loops: Probably the most important part of scripting

Loops are used to do the same operation (aka execute the same code) several times. You can do something forever, do something until something is true or false, or do something for a few times. If you don't wrap your head around loops and how to use them, you probably won't be able to script very much of anything so be sure to listen up. These are the most common loops:

Note that in GSC you need to have a wait statement in an infinite loop or you will ruin your script. In COD WaW you will get a lag spike if you forgot the wait statement. In bo3 you will get "Connection Interupted".

`for`: the foor loop needs 3 inputs to work: a definition, a condition, and an operation. Take a look at this example and I will explain:


``` php
      for( i=0; i<10; i++ ) // this is not an infinite loop (it has a condition that is not always true)
      {
          iprintlnbold(i); // show i on screen
          wait(2); // wait 2 seconds so the player can actually read the printed statement
      }
```

The above code defines *i* as 0, then the code contained by the braces of the for loop will execute, then we increment `i` by 1, then we check if `i` is less than 10, and if it is we do the same thing again. Note that this code will execute 10 times. For each time through I will list the values of `i`: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9. Notice `i` never equals 10 because the index starts at 0 and the loop stops when i = 10 (from the condition).

`while`: the while loop happens as long as the statement inside the ( ) is true. Check out the example below:


``` php
      i = 0; 
      while(1) // this is an infinite loop
      {
          iprintlnbold(i); 
          i++; 
          wait(0.05); // this is the fastest you can possibly execute a loop in GSC
      }
```

In the above example the code inside the ( ) of the while is always true, therefore it will go on forever unless we `break` out or `endon` a notify, which I will discuss later. Note that the code above is printing how many times the loop executed to screen, and each execution takes 0.05 seconds. The user will never be able to read this, but this is just so you understand how a while loop works. Lets do another while loop example: 


``` php
      players = GetPlayers(); 
      player = players[0]; 
      while( player isOnSlide() )
      {
          iprintlnbold( "The player is sliding" ); 
          wait(0.05); 
      }
```

In the above example the we are checking if the host player is on a slide. If he is we are spamming the screen with a message saying that the player is sliding.

`foreach`: the foreach loop is more complicated than the two previous types. It takes an array and executes it's body code *for each* item in the array. In scripting, the foreach loop is usually used to call a function on a list of entities.

Two examples:
``` php
      teddies = GetEntArray("shootable_teddy", "targetname");
      foreach (teddy in teddies) // teddies is the input array and teddy is used to reference each item in the array
      {
          teddy Hide(); // hides each teddy in the array
      }
```

``` php
      foreach (player in GetPlayers()) // GetPlayers() returns an array of the players, so it is the array that is input and "player" is used to reference each "item" (player) in the array
      {
          player DoDamage(10, player.origin); // this loop deals 10 damage to each player
      }
```

`do while`: the do while loop is rarely used but worth mentioning. A do while loop is used when you want the body code to be executed at least once before the condition is checked. In a do while loop, the code block is run, then the condition is checked and while the condition is true it gets run repeatedly (like a while loop).

``` php
      players = GetPlayers();
      player = players[0];
      do
      {
          player DoDamage(10, player.origin);
      } while(player.health > 30 && player IsTouching(damage_trig)); // damages the player while they are above 30 health and touching the trigger, executes at least once
```

--- 

## Loop Manipulation: notify, endon, continue, break, and return

I think I struggled understanding this the most when I first learned to code, so don't feel bad if you revisit this section a few times to understand yourself. I will briefly explain how each of the statements can help you manipulate a loop:

`continue`: this is a counter intuitive statement. You would think continue means move forward but it actually means "skip". A continue statement inside a loop ( either for or while ) will bring execution back to the top of the loop. If it is a for loop it will increment the *i* and start the next iteration. Check out this example with an array "grades". We will assume the grades array is already defined with a numerical index and filled with values:


``` php
      failing_students = 0; 
      for( i=0; i<grades.size;i++ ) // this loop will execute the amount of times as there are elements in "grades"
      {
          if( grades[i] > 70 )
          {
              iprintlnbold( "The student passed" ); 
              continue; 
          }
          failing_students++; // adds 1 to the variable only failing students if grades[i] is > than 70
      }
```

Note that the continue inside the check for a passing grade will force the execution back to the top, not allowing the failing_students variable to increment if they passed. 

`return`: returns are interesting because they have two functions a) they can return a value and b) they stop a function from running any further. Functions stop and return a value when a `return` is read in code. You can return any data type with a `return`. Lets keep doing the lame failing grades example:

``` php
      function main()
      {
          grades =  GetStudentGrades(); // This doesnt exist but lets pretend we got the array of grades somehow
          failed = did_a_student_fail( grades ); // lets call another function and return a true or false from it
          if( failed )
              iprintlnbold( "At least one student failed" ); 
          else 
              iprintlnbold( "No students failed" ); 
      }
      
      function did_a_student_fail( grades )
      {
          for( i=0; i<grades.size;i++ ) // this loop will execute the amount of times as there are elements in "grades"
          {
              if( grades[i] < 70 )
              {
                  return true; // A student did fail
              }
          }
          return false; // This will never execute if any student failed, but if no one failed it will
      }
```

Take the time read the above example and understand why the false will not be returned. Remember: return statements break the loop and the function!

`break`: a break statement will stop the execution of a loop, and continue execution on any code below the loop. Note that this is different than a return because a return breaks the loop and the function. Breaks are often useful if you just want a certain piece of information from a function or if you want to break out of the function to do something more important. Take a look below:


``` php
      while(1)
      {
          if( level.next_dog_round == level.round_number )
              break; 
          iprintlnbold( "This line and below wont execute if the break is called" ); 
          wait(1);
      }
```

This function isn't all that useful and there is probably a better way to wait for a dog round, but this helps you understand the break statement. We are always going to be in that loop checking if the next dog round is the round we are on and if that is the case we will leave the while loop. 

`notify`: notifies are another way to break a loop by pairing it with an `endon`. These are so useful that I will talk about them in the next section.

Note: `break` and `continue` are the only two things here that can ONLY be used in a loop. If you use either outside of a loop you will get an error.

---

## Notify and Its Dependents: Endon & Waittill

Notifies are exactly as they sound; they are a notification. So imagine your phone notifying you that a message has been received. This would happen with a beep and a visual on your phone, but in script a notify is sent as a string to the entity it is called on. 

**How Do You Use a Notify?**

Engine Notfies:
Some notifies are automatically scripted into the game. Some of these notifies include: "death", "intermission", "all_players_connected", "trigger", and "projectile_impact". If I ever manage to get a list of engine notifies I will include them in a seperate section of the Wiki. It is also worth noting that some notifies can also pass variables. An example is `notify( "death", attacker );`

Custom Notifies:
You will often times want to make your own notifications through script. Notifies are passed onto either the `level` or an `ent`. An example of a situation where you might want to use a notify on a player is to get blood splatter to show on screen. You can check if a player is close enough to a zombie after the zombie has died and then use something like:


``` php
      player notify( "splatter_blood_onscreen" ); 
```

**How to Take Advantage of a Notification**

Like I mentioned in the title of this section there are dependents on a `notify` called `endon` and `waittill`. I will define what they do below:
- `endon`: this kills a function when a notify of the same string is received. You will often be running multiple functions at once, but one function may be dependent on the execution of the other. Passing a notify to an ent and using and endon can kill the dependent function.
- `waittill`: this does exactly as it sounds. A waittill waits until it receives the exact string notification you place in it. Waittills can also pass through variables as I stated earlier when I said notifies can pass variables.

Check out this example where *self* would be the player entity:

``` php
      function blood_splatter()
      {
          self endon( "death" ); 
          while(1)
          {
              self waittill( "splatter_blood_on_screen" ); 
              iprintlnbold( "splatter blood now" ); 
          }
      }
```

Lets take a look at a few things here. Note how this is an infinite loop. //Whenever you have an infinite loop it is best practice to have something that can end that loop, whether it be a break, return, or endon//. So notice this function will quit running when the player ( *self* in this example ) dies. Also note that the player ent is always waiting for a notification to splatter blood on screen. `Recall`: that every infinite loop needs some sort of wait statement. In this example it is a waittill statement. 

---

## Threading Functions

Another very important thing you will need to know is how to thread a function, as well as when you should or shouldn't. Something Nate did not mention is that the execution of a function pauses when you call a function inside it. If you call a function with an infinite loop in the `main()` function of your mapname.gsc you will cause a connection interrupt because the main function will never end as it is waiting for the other function you called to finish:
``` php
      function main()
      {
          /* main function stuff */
          level infinite_loop();
      }
	
      function infinite_loop()
      {
          while(1)
	  {
              wait(1);
	  }
      }
```
This setup will cause a connection interrupt regardless of the fact the loop has a wait. This is because, like I said, the `main()` function pauses it's execution when `infinite_loop()` is called, and since `infinite_loop()` never ends the execution on `main()` can never continue. We can solve this by *threading* the function. *Threading* a function allows it to execute while not stopping the execution of the function it gets called from.
``` php
      function main()
      {
          /* main function stuff */
          level thread infinite_loop();
      }
	
      function infinite_loop()
      {
          while(1)
	  {
              wait(1);
	  }
      }
```
Here you can see that I have *threaded* `infinite_loop()` which will allow `main()` to continue while also running the infinite loop.

You want to *thread* functions when they need to run at the same time as the function they are called from, like functions from Nate's notify examples. You don't always want to *thread* functions however. If you are waiting for a value to be returned, you want the function to be run before execution of the logical operators occurs, like in Nate's example from *return* in **Loop Manipulation**.

---

## Syntax Style

Everyone has their own style of coding, it can be whatever looks best to you, feels most comfortable, or is just easiest/shortest to type. You may see different styles if you look at other people's scripts, Nate uses the same style as Treyarch does, and my style differs from that. Whatever style you use, try to be consistent with that style.

Treyarch/Nate's Style
``` php
      function main()
      {
          grades =  GetStudentGrades(); // This doesnt exist but lets pretend we got the array of grades somehow
          failed = did_a_student_fail( grades ); // lets call another function and return a true or false from it
          if( failed )
              iprintlnbold( "At least one student failed" ); 
          else 
              iprintlnbold( "No students failed" ); 
      }
      
      function did_a_student_fail( grades )
      {
          for( i=0; i<grades.size;i++ ) // this loop will execute the amount of times as there are elements in "grades"
          {
              if( grades[i] < 70 )
              {
                  return true; // A student did fail
              }
          }
          return false; // This will never execute if any student failed, but if noone failed it will
      }
```

Holofya's Style
``` php
      function main()
      {
          grades =  GetStudentGrades(); // This doesnt exist but lets pretend we got the array of grades somehow
          failed = did_a_student_fail(grades); // lets call another function and return a true or false from it
	  
          if(failed)
	  {
              IPrintLnBold("At least one student failed");
          }
	  else
	  {
              IPrintLnBold("No students failed");
	  }
      }
      
      function did_a_student_fail(grades)
      {
          for(i = 0; i < grades.size; i++) // this loop will execute the amount of times as there are elements in "grades"
          {
              if(grades[i] < 70)
              {
                  return true; // A student did fail
              }
          }
	  
          return false; // This will never execute if any student failed, but if noone failed it will
      }
```

My style takes more typing and uses more space but it looks better to me :)

---

## Conclusion

This concludes the very basic scripting syntaxes you will come across in GSC. I recommend that at this point you try reading some of the provided scripts in BO3. Pick a script that you can remember how it works in games, such as the dog round script, and read through it. You should be able to make sense of what is happening at this point. If it is still confusing refer back to this wiki or pop in chat to ask some more experienced modders. **In order to understand you must study the work of others**. Best of luck studying. Keep a lookout for additional sections of the wiki on Modme.

---

_Contributers:_
- NateSmithZombies
- Holofya
