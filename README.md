# MazeGame
A Java dungeons themed maze game where players must overcome obstacles and achieve specific goals. There are 10 different levels, and was designed using Object Oriented Programming, utilising the Strategy Pattern for enemy movement, State Pattern for collectable objects, Observer Pattern for inventory updates and Composite Pattern for goals. Testing was done through JUnit Tests. For this project, I was in charge of dungeon, level and instructions page design (unfortunately in the gif demonstration the text isn't aligned correctly) for frontend and logic for picking up items, storing them in an inventory and using them (e.g. opening doors, destorying enemies) for backend. 

## How To Play

The client desires an application that lets the user move a player around a dungeon and try to overcome various challenges in order to "complete" the dungeon by reaching some goal. The simplest form of such a puzzle is a maze, where the player must find their way from the starting point to the exit.

Dungeon layout

To be specific, the layout of each dungeon is defined by a grid of squares, each of which may contain one or more entities. The different types of entities are as follows:

**Player** : Can be moved up, down, left, and right into adjacent squares, provided another entity doesn't stop them (e.g. a wall).

**Wall** : Blocks the movement of the player, enemies and boulders.

**Exit** : If the player goes through it the puzzle is complete.

**Treasure**: Can be collected by the player.

**Door** : Exists in conjunction with a single key that can open it. If the player holds the key, they can open the door by moving through it. Once open it remains so. The client will be satisfied if dungeons can be made with up to 3 doors.

**Key** : Can be picked up by the player when they move into the square containing it. The player can carry only one key at a time, and only one door has a lock that fits the key. It disappears once it is used to open its corresponding door.

**Boulder** : Acts like a wall in most cases. The only difference being that it can be pushed by the player into adjacent squares. The player is only strong enough to push one boulder at a time.

**Floor switch** : Switches behave like empty squares, so other entities can appear on top of them. When a boulder is pushed onto a floor switch, it is triggered. Pushing a boulder off the floor switch untriggers it.

**Portal** : Teleports entities to a corresponding portal.

**Enemy** : Constantly moves toward the player, stopping if it cannot move any closer. The player dies upon collision with an enemy.

**Sword** : This can be picked up the player and used to kill enemies. Only one sword can be carried at once. Each sword is only capable of 5 hits and disappears after that. One hit of the sword is sufficient to destroy any enemy.

**Invincibility potion** : If the player picks this up they become invincible to enemies. Colliding with an enemy should result in their immediate destruction. Because of this, all enemies will run away from the player when they are invincible. The effect of the potion only lasts a limited time.

**Slime** : Follows the player as they move (not time based) so it prevents players from stepping on a square they already traversed through 

**Fire** : Blocks paths 

**Fireproof Jacket** : When this is in the player's inventory, they are able to walk through fire. However the jacket can be only used once and disappears when it has been used. 

### Goals

In addition to its layout, each dungeon also has a goal that defines what must be achieved by the player for the dungeon to be considered complete. Basic goals are:


1. Getting to an exit.
2. Destroying all enemies.
3. Having a boulder on all floor switches.
4. Collecting all treasure.


More complex goals can be built by logically composing basic goals. For example,


Destroying all enemies AND getting to an exit
Collecting all treasure OR having a boulder on all floor switches
Getting to an exit AND (destroying all enemies OR collecting all treasure)


If getting to an exit is one of a conjunction of conditions, it must be done last. For example, if the condition is to destroy all enemies AND get to an exit, the player must destroy the enemies then get to the exit.

## Instructions
1. Download the repository
2. Open the repository using a Java IDE, Eg: Eclipse
3. Open the DungeonApplication.Java file and run it
