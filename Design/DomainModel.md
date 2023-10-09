##Domain Model

###Classes

####Menu
The menu is a GUI with buttons and information to give the user choices. It

helps with accessibility options and selecting the escape room you want to play.

####Settings
The settings class is another menu that allows the user to change the volume and 

screen size.

####HUD
The HUD is a display of information that is always available to the player

to help them keep track of their inventory, time, and objectives.

####Scenario
The scenario class describes the escape room story that the user will play through.

Scenarios are themed after distinct concepts related to the CME work field.

Scenarios contain multiple puzzles.

####State Manager
The state manager is what keeps track of the user's progress through a scenario.

It checks what the user has done so it can properly progress them.


####Puzzle
A puzzle is similar to a level in a video game. It is one room out of multiple

within a scenario. Puzzles are the rooms the user will play through.

####Objective
An objective is a goal within a puzzle. Puzzles have multiple goals.

Completing a goal can be a single event, such as using a key to open a box.

####Interactable
Interactables are the main mechanic of the game. These are various objects in the scene,

or puzzle, that you can click on. There are multiple types of interactables that can 

give you information, go in your inventory, or lead you to another room.






![CME_QUEST_ADVENTURES_DOMAIN_MODEL](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/70415471/f5728d45-a126-4367-bda4-b772eeab95b9)
