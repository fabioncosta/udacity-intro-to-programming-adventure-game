# udacity-intro-to-programming-adventure-game
To run adventure_game.py open a console, navigate to the directory where
adventure_game.py was saved and type "python3 adventure_game.py".
- - - - -
Udacity instructions:

In this project, you'll make a simple version of an old-fashioned text-based
adventure game. You can find an example in the workspace below. Try it out to
get a feeling for how the game works!

As you can see, this is only a very short game with a couple of choices available
to the player. We did that on purpose, to keep it simple. If we were making a
complete game, we would expand it a great deal, and probably give the player a
whole world to explore. But for this project, the idea is to focus on some key
things that we need if want to make a working game:

- The game gives players a description of what's happening, and then asks them
to make a choice.
- Something different happens depending on the choice the player made.
- The game also includes some random factors, so that it's a little different each
time.
- The game has conditions for winning and losing.
- When the game is over, it asks if the player wants to play again.
  
These are the key features that your project will need to have in order to make it
into a playable game. We'll go over each of them in more detail below.

As long as your program does all of the things listed below, you are free to be as
creative as you like!

Print descriptions of what's happening for the player

One thing the game will need to do is to print messages for the player to describe what
is happening. Such as:

You find yourself in a dark dungeon.
In front of you are two passageways.

This is a very small step, but a good way to get started!

Now, one thing you might have noticed is that when you have multiple print statements, they
get displayed in the terminal so fast that it looks like they all just show up at the same
time. That's no good.

If you look at the example game, there's a short delay after each line is printed.
You may remember that earlier in the course, we briefly introduced the time module and the
time.sleep function:

import time
print("Hello")
time.sleep(2)
print("world!")

This will cause a 2-second delay after the first print statement. Give it a try with the messages
in your code!

Give the player some choices

Another important element of any good adventure game is choice. To do this, you'll need to get some
input from the player, and then change what happens depending on what that input is. In the example
game, that looked like this:

Enter 1 to knock on the door of the house.
Enter 2 to peer into the cave.

Make sure the player gives valid input

Another thing to notice in the example game is that if the player enters something other than 1 or 2,
the game keeps asking them for a 1 or 2. We don't want the game to accept invalid input, like 75 or
foo!

(Please enter 1 or 2.)
75
(Please enter 1 or 2.)
foo
(Please enter 1 or 2.)

If the player tries to respond with something invalid, your program should ask them to try again—and
it should keep asking them to try again until they give valid input.

Add functions and refactor your code

By now, you may have noticed that some of your code is getting pretty messy, and some parts may be kind
of repetitive. If you haven't already, this would be a good time to consider defining some functions, and
moving some of your code into those functions.

For example, you probably have a lot of code that looks like this:

print("You find yourself in a dark dungeon.")
time.sleep(2)
print("There are two passageways in front of you.")
time.sleep(2)
print("Which way do you want to go?")
time.sleep(2)

This is quite repetitive—we are using print, sleep, print, sleep, print, sleep, over and over ...

One improvement that you can make is to define your own function so that it will both print and sleep—you
might call it the print_pause function.

With such a function, you could simply pass it a message to print, and it would take care of the pausing:

print_pause("You find yourself in a dark dungeon.")
print_pause("There are two passageways in front of you.")
print_pause("Which way do you want to go?")

Here's another way you can use functions in a game like this—you can define a function for each place the
player can go. In the example game, the code looks something like this:

def house():
    # Things that happen to the player in the house

def cave():
    # Things that happen to the player in the cave

def field():
    # Things that happen to the player in the field

That way, when the player chooses to go to one of these places, you can simply call the function that
displays the information and choices for that place. This is especially good if you want the player to
be able to go back to the same place repeatedly, from different locations in the code. In the example game,
the player can get back to the field from both the house and the cave, and having the field function makes
this much easier.

These are just a few examples of how you can use functions in your project. You'll probably find other ways
you can clean up the code and reduce repetitiveness by defining (and calling) functions. (In fact, it's possible
to do this project with almost every line of code being placed inside a function definition!)

Use randomness in your game

Another key feature of most games is randomness or chance. If everything always happens exactly the same way,
it can become boring and predictable.

There are all sorts of ways you could use randomness in your game. Here are just a few possibilities:

- In the example game, the enemy creature is selected randomly each time they play. Sometimes it's a pirate,
  sometimes it's a troll, and so on.
- You could do something similar to randomize which weapons or magical items the player encounters.
- You could include a combat simulation in which the player and enemy deal random amounts of damage to one
  another (you may remember that we did something like this earlier in the course).

All of these can be done using Python's random module and the random.choice and random.randint functions that
we learned about earlier.

There are countless other possible ways to use randomness in your game—feel free to be creative here.

Create win and lose conditions

Eventually, the game should come to an end—and tell the player that they won or lost.
The end result of the game should be influenced by the player's choices (and possibly some degree of randomness
as well). Generally, it's a good idea to use randomness to only partially influence the outcome. If what happens
to the player is completely random, the player will feel out of control and probably won't enjoy it. 

Check if the player wants to play again

When Python gets to the end of your script, it will exit back to the terminal. But that's not a good player
experience. Instead, it would be better if the game asked the player whether they want to play again:

GAME OVER

Would you like to play again? (y/n)

Just like with other choices you've asked the player to make, this will need to get the player's input and then
check if the input is valid.

If the player indicates that yes, they want to play again, then the game should start over. Depending on what
you added to your game, there may be some things that need to be reset. For example, if your player has a health
score or they picked up magical items, these should go back to the way they were when the game starts over.

Check your style with pycodestyle

When you're all done with your program, be sure to check it using the pycodestyle tool—and then fix any issues
it raises.

pycodestyle adventure_game.py

When you're all done, running pycodestyle on your program should give no results (no news is good news!).

Test your code
Before submitting your project, be sure to test it. Play through a few times, checking to make sure that the
different choices all work, and that invalid input doesn't cause the program the crash.

If you've done everything on this page, your code should be in good shape for a review! But if you'd like to
be extra thorough, you can check out the rubric your reviewer will be using to grade your submission.
- - - - -
