# README #

## Group Information ##

**Team Members**
+ Student 1
+ Student 2
+ Student 3

**Group Number:** Your Group Number

**Period:**	Your Period

**Game Title:** Your Title (can always change it later)

## Game Proposal ##

Write a paragraph here describing the game you want to make.  Describe how it is played and which features
you want to include in your game.  Remember, any simple game can be scaled up with features and any complex
game can be scaled down.

**Game Controls:**

+ edit here

**Game Elements:**

+ edit here

**How to Win:**

+ edit here

## Link Examples ##
Provide links to examples of your game idea.  This can be a playable online game, screenshots, YouTube videos of gameplay, etc.

+ [Example Link](http://www.freewebarcade.com/game/tiny-empire/)

## Teacher Response ##

Your teacher can add comments and suggestions here

## Class Design and Brainstorm ##

Put all your brainstorm ideas, strategy approaches, and class outlines here


***
***

# Example (Delete after you've read the example) #

## Group Information ##

**Team Members**
+ Happy Sparky
+ Justin Case
+ Cody Gamester

**Group Number:** 3

**Period:**	1

**Game Title:** Bomb Squad

## Game Proposal ##

We want to make an Angry Birds clone where the player shoots different powerup items at targets.  Instead of a
physics engine, we will have a simple gravity world with elements such as trampolines, lava, fog, fans, etc,
that modify the shot path.  We will also have different enemies and friendly characters you shouldn't hit.

**Game controls:**

+ Mouse and buttons control your shot speed and direction
+ Arrow keys control which powerup you will launch

**Game elements:**

+ Simple falling physics in a gravity world
+ Friendly characters you must avoid hitting
	+ Some stay put where they are
	+ Others walk back and forth so you must time your shot
+ Armored enemies take two shots to kill (they drop their armor when hit first time)
+ 3 Levels followed by a Boss level
+ Elements you hit don't tumble like in Angry Birds but they all do something fun.
  + Trampolines - Your shot bounces off and continues farther
  + Lava - kills your shot instantly (no rolling)
  + Fog - your shot drops faster due to dense air
  + Fans - adds wind and modifies the direction of your shot
+ You must clear levels using a limited amount of shots

**How to win:**

+ Clear all levels using your limited bomb supply
+ We might have a star scoring system so player can try for a perfect score of 3 stars.

## Link Examples ##
Provide links to examples of your game idea.  This can be a playable online game, screenshots, YouTube videos of gameplay, etc.

+ [Angry Birds](https://www.youtube.com/watch?v=aiiQ8btusrs) My original inspiration
+ [Tiny Empire](http://www.freewebarcade.com/game/tiny-empire/) I love this!  I want to make something like this version!

## Teacher Response ##

I love your game plan!  Unless your boss level is truly awesome, it would be better to focus on having more
levels that add progressive game play twists, just like the real Angry Birds game has.  Maybe introduce a
new game element with each level and then have a few levels that take some thinking and replaying to beat.

Also, you haven't addressed how you'll hit multiple enemies.  Is it one shot per enemy or can a single shot
hit multiple enemies?  If so, how would that work?

## Class Design and Brainstorm ##

+ **GravityWorld** - extends World and defines a static gravity value all falling actors will use.  Also keeps track of the level and initializes the Scene to match the level you're on.
+ **GravityActor** - extends Actor and adds dx, dy to handle falling with gravity.  Any Actor than can fall due to gravity must be an extension of this class.
+ **FriendlyActor** - extends GravityActor.  These are friendly characters you should not hit.  If you do, you lose points/power.
+ **Enemy** - extends GravityActor and defines a basic enemy
+ **ArmoredEnemy** - extends Enemy and adds armor you must destroy before the enemy takes damage
+ **Armor** - Defines the properties and methods of Armor, which is an attribute held by each ArmoredEnemy.
+ **Destroyable** - an interface that defines what it means to be destroyable.  Objects that are destroyable must have onHit() and onDestroy() methods.
                    These handle what happens when you hit and finally destroy an object.  All Enemies and FriendlyActors implement this interface.
+ **Obstacle** - Defines any kind of obstacle/barrier that can't be destroyed but that shots bounce off of.
+ **DestroyableObstacle** - Defines any kind of obstacle or scene object that can be destroyed.
+ **Trampoline, Lava, Fog, Fan** - These are all extensions of Actor that modify the path of the shot when hit or nearby.
