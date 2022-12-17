---
description: Frequently Asked Questions
---

# FAQ

## Can I make my character sprite object bigger? <a href="#are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have" id="are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have"></a>

## Are there similar features found in mainstream RPG Makers? <a href="#are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have" id="are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have"></a>

\*Because this engine is still in development, some classic features are currently missing. However as time goes on you can expect to see most of what you need\*

Yes. The engine automatically cut the picture so you can make it any size. Just make the picture be multiple of the square size (16px).

## Are there all features from RPG Maker? <a href="#are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have" id="are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have"></a>

Yes, but with a twist.&#x20;

Where it counts, instead of giving you limited, exact replica features - this engine gives you a framework that allows full customization and creation of old features along with some new ones. Some features are of course replicas, because you can't always improve what works.&#x20;

Many commands allow use of variables in place of static numbers. You can create a database of hitboxes, fonts, camera angles, etc; and then reference them in event commands for easy access.&#x20;

You will find familiar database windows and layouts. Familiar 'Move Hero' and 'Change Variable' commands. All slightly enhanced.&#x20;



## What are the supported pictures formats? <a href="#whats-the-picture-size-format-support" id="whats-the-picture-size-format-support"></a>

It can take a bit of time to get used to, but this type of framework allows you to make gameplay systems in a fraction of the time and code. And it's close enough to mainstream editors to reduce the learning curve.&#x20;

.png, .jpg.

## How large of a game can I create? <a href="#whats-the-scale-or-game-world-size-support-in-this-game" id="whats-the-scale-or-game-world-size-support-in-this-game"></a>

For now the max map size is 1000 x 1000 squares. But there will be a feature for connecting large maps to create really huge maps, like open world games.

## Is 4K resolution supported? <a href="#are-there-4k-resolution-support" id="are-there-4k-resolution-support"></a>

No. The engine can support up to 1080p.&#x20;

## Is there a built-in image editor? <a href="#are-there-in-appsoftware-drawingtexture-tool-where-you-can-edit-draw-textures" id="are-there-in-appsoftware-drawingtexture-tool-where-you-can-edit-draw-textures"></a>

Not at this time. You will have to use external programs then import the resources.&#x20;

## Can you use GIF files for animations?  <a href="#can-you-use-gif-animations-or-parsed-series-of-images-that-app-can-use-into-animation" id="can-you-use-gif-animations-or-parsed-series-of-images-that-app-can-use-into-animation"></a>

GIFs are not supported at this time. You will have to use standard methods like any RPG Maker.&#x20;

## Is it possible to make real time battles? <a href="#is-that-possible-to-make-real-time-battles-or-just-turn-based" id="is-that-possible-to-make-real-time-battles-or-just-turn-based"></a>

For the default battle system, turn based is the only option at this time. Other types of combat systems are planned, such as tactical battle system.&#x20;

There are enough commands to create a custom battle system to mimic most games, from Pokemon to Star Ocean. But with more planned commands this will become even easier.&#x20;

## What is the tile size? <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>

By default the value is 16x16, but you can change it to any value. Your resources should match, being multiples of whatever you set the tile size to. (32x32, 48x48, etc)

## Questions from Discord <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>

\---Q---\
How to create footstep sound effects?\
\---A---\
This depends on how your hero moves. By default this movement is in the "Hero" model, in the code for pressing the keys for each direction. It moves you by 1 step. If you add a sound effect here, it will play too fast.&#x20;

You could change the movement from step to square, moving in one full tile. If made to wait until complete, you can put the sound effect after the move and it plays with the correct timing. However this causes bugs with collision(try walking up slopes).&#x20;

\---Q---\
How to import a custom file?\
\---A---

One possible solution for step movement is that every time you take a step it turns on a switch. This switch is contained in a conditional branch that checks itself to be OFF, so it can only run one at a time. \
Another event is turned on by the switch and plays the sound effect. It waits the proper amount of time, around .4 seconds, and turns OFF the switch. This allows your next step to trigger another sound effect. If you have stopped moving, no further sounds. \
\
\
\---Q---\
How to create item drops? (I assume in an ABS style game)\
\---A---\
For repeat drops, use the "Create object in map" command. This will allow you to spawn as many copies of the same thing as you want. \
Start by creating a new Model. Name it and assign the graphic. Add the code. \
Now go to the map object that spawns the item drop. Set up the trigger for dropping. \
Add the "Create object" command and choose your item drop model. \
A drop will be spawned out of thin air using the graphic and code set up in the model. \
Using this method you will need to manually keep track of IDs if you want to do anything other than spawn them. Despawn, move around, change, all require an ID to be assigned.&#x20;

When you make a new project you determine the folder path. To find your project's resource folders navigate to that folder and open /resources/app/Content/ and you will see all the subfolders for each type of resource. Start by adding your files here.&#x20;

Let's say we're talking about killing an enemy and it drops an item. You can use states to simply change the graphic and code without adding any new objects. This means both can't be displayed at once(the coin laying next to the dead body).&#x20;

In the editor some of these resources will be ready to use right away. Some have their own lists and you need to add the resources to this list.&#x20;

Another method is to create an object in advance and make it invisible. When activated it is moved to any place on the map it is needed. This has the benefit of having preset IDs that can be organized in advance.&#x20;

You can drag files into these folders while the engine is open. You may need to need to save, open a database window, or reload the project for changes to appear. Most things are safe to add. If a resource has been added to one of the lists, make sure you update the list before removing the resource from the folder to avoid problems.&#x20;

\---Q---\
How to zoom out the camera, or do anything with the camera? first person view\
\---A---\
One method is to make multiple copies of the same Camera Property and change the zoom level in each. Then use the "Change Map Properties..." command to switch between Camera Properties of varying levels of zoom. A variable can keep track of the current zoom level and the code to change map properties also changes this variable. This might be useful in a game that otherwise limits how much you can turn the camera. It can carry between maps with some extra code.

\---Q---\
How to create footstep sound effects?\
\---A---

The straightforward method is to use the "Move Camera..." command. However each time you teleport to a new map these changes will be lost. \
When using the equals operation, any box with a 0 will change the camera. So use plus or minus so it only alters the fields we use.\
Put a number only in the Distance field. This is the distance between the target object and the camera. A larger number moves the camera farther away. 0.5 is first person view and 600+ is a bird's eye view. The default number is 300.&#x20;

This depends on how your hero moves. By default this movement is in the "Hero" model, in the code for pressing the keys for each direction. It moves you by 1 step. If you add a sound effect here, it will play too fast.&#x20;

The default camera is whichever Camera Property is set to the Map Properties of the starting map. Under Systems/Camera Properties is where you can create different presets. Each map is assigned one and it can be changed by command.&#x20;

You could change the movement from step to square, moving in one full tile. If made to wait until complete, you can put the sound effect after the move and it plays with the correct timing. However this causes bugs with collision(try walking up slopes).&#x20;

Moving the camera in every other way with the "Move Camera" command can be complicated. You should learn some of the basics and figure out what is needed for each situation.&#x20;

One possible solution for step movement is that every time you take a step it turns on a switch. This switch is contained in a conditional branch that checks itself to be OFF, so it can only run one at a time. \
Another event is turned on by the switch and plays the sound effect. It waits the proper amount of time, around .4 seconds, and turns OFF the switch. This allows your next step to trigger another sound effect. If you have stopped moving, no further sounds.&#x20;

\*Link to a detailed guide for moving the camera around\*

\---Q---\
How to create item drops? (ABS game style)\
\---A---\
For repeat drops, use the "Create object in map" command. This will allow you to spawn as many copies of the same thing as you want. \
Start by creating a new Model. Name it and assign the graphic. Add the code. \
Now go to the map object that spawns the item drop. Set up the trigger for dropping. \
Add the "Create object" command and choose your item drop model. \
A drop will be spawned out of thin air using the graphic and code set up in the model. \
Using this method you will need to manually keep track of IDs if you want to do anything other than spawn them. Despawn, move around, change, all require an ID to be assigned.&#x20;

\---Q---\
How to import a resource file?\
\---A---\
When you make a new project you determine the folder path. To find your project's resource folders navigate to that folder and open /resources/app/Content/ and you will see all the subfolders for each type of resource. Start by adding your files here.&#x20;

Let's say we're talking about killing an enemy and it drops an item. You can use states to simply change the graphic and code without adding any new objects. This means both can't be displayed at once(the coin laying next to the dead body).&#x20;

In the editor some of these resources will be ready to use right away. Some have their own lists and you need to add the resources to this list.&#x20;

Another method is to create an object in advance and make it invisible. When activated it is moved to any place on the map it is needed. This has the benefit of having preset IDs that can be organized in advance.&#x20;

\*Show video of new in-engine pop up hints\*

You can drag files into these folders while the engine is open. You may need to need to save, open a database window, or reload the project for changes to appear. Most things are safe to add. If a resource has been added to one of the lists, make sure you update the list before removing the resource from the folder to avoid problems. \


\---Q---\
How to set variables/run code right away when starting a new game?\
\---A---\
There are 2 possible locations where the first lines of code can be run. The starting map is going to be which ever map the object marked as hero starts on. On this map you can use the Map Properties or a map object. \
\*Show examples\*\
Needs testing, but in the past having both of these run at the same time caused a problem and it wasn't consistently picking the same one to run first. So you should only have one to avoid conflict. \
\
\---Q---\
How to speed up various animations?\
\---A---\
In Systems, you will find a group of settings called Frames. This applies to most animations in the game. Some other animations have their own settings that override these.&#x20;

The first box is "Map frame duration". By setting this to a number you are making it static throughout the whole game. By setting it as a variable, you can adjust in game before displaying a certain animation to possibly get varied speeds. Needs testing.&#x20;

The "Animation frames" applies to all charsets. They all have to match.&#x20;

The remaining settings apply to each labeled area. \
\
\*There should be more detailed information somewhere else\*\
\
\---Q---\
How to do line of sight and proximity detection?\
\---A---\
Proximity detection is the easy part. There is a built in command called "Send event". You can create hitboxes of any size, summon them, and see if any objects are hit by them. By creating a circle hitbox and summoning it on the player, it will detect anything within that range. Followed by any code for a reaction.&#x20;

A simple form of line of sight can be done with the above method, plus some code to track which direction the object is facing. The object has to be facing the target(likely the hero) in order for the reaction to trigger. This won't allow walls to block sight.&#x20;

A method that does allow walls and certain objects to block the line of sight is more complicated. This will likely have to be a built in feature for future release, or added via script/plugin. It might be possible with event commands, if someone was motivated enough. \
\
\---Q---\
How to heal characters?\
\---A---\
This one works a little different from most engines. There is no specific command to heal because HP is altered the same as every other stat. You use the "Change a statistic" command as needed.&#x20;

\
\---Q---\
How to disable camera movement in certain rooms only?\
\---A---\
This will depend on how you handle camera movement. By default it's found on the "Hero" model. \
\
The easiest way would be to put a conditional branch around the code for moving the camera so you can disable it all with a switch. When you enter a map where the camera should be disabled you simply turn ON the switch. However using conditional branches on models in this way causes a bug, so we can't do that.&#x20;

You can use another state on the "Hero" model that is a duplicate of the normal model except the code for moving the camera is removed. Don't forget to switch it back. If you use many states for other things in your game this can become very complicated.&#x20;

If you want to change the default way, you can move the code to another object. Then you can do more with it. One example is that on the model when you press the key to turn the camera, it doesn't contain any code. Only a call out to another object that does contain the code, where using conditional branches should work. Needs testing.&#x20;

\
\---Q---\
How to change what hero the player controls?\
\---A---\
This is going to depend on a few things.&#x20;

Remember, the object you control at the start of a new game is something you designate. On this first map that object will have it's normal ID. However when you teleport to any other map, the ID changes. If it was 10, and you teleport into a new map that also has a 10, there would be a conflict. So the hero object becomes ID 0 and each new map retains it's normal ID. This need confirming.

The reason this matters is because several other commands reference "Hero", like "Move object" and "Send event". Which is this special object you are teleporting around the maps. If you want to change the object you are controlling, it will change how certain things interact.&#x20;

You can use the "Move object" command to simply change the sprite used and all the other code will remain the same.&#x20;

The main way you will change what the hero sprite looks like is to change the state on the Hero object/model. If you make a new state it will not contain any code for moving. So you always want to copy the state and change the graphic. Then remove any code that doesn't apply.

You can create other objects to use as placeholder for the other members of your party when switching. The Hero object state is changed and it's teleported to another spot, where one of the placeholders was standing.&#x20;

\*I created a test project where 4 different objects are used for 4 heroes and the player can switch between them. In my experience if you plan to use this method, abandon the object designated as Hero and do not use "Hero" in the target drop down for anything. You have to create a system that uses variables to determine the target. \*\
\
\---Q---\
Why can't I move the hero?\
\---A---\
I'm going to assume it was already working and suddenly stopped working. If you are new to the engine and your first play test has a non-moving hero - check out \*some guide for making a new project TBD\*

Did you change anything related to hero movement? \
Have you been tweaking the code for key inputs or the hero model? \
Check your code and undo the changes if possible. Consult a default project to see how the hero model works.&#x20;

A common problem is that a different object on the map has the 'Block hero when reaction' option enabled, and it's running all the time. Meaning the hero is frozen while that object is processing. Check all recent objects you added. If it's enabled by mistake go ahead fix it, otherwise you will have to change how that object is coded.&#x20;

There could also be another object that is trying to move the hero. Perhaps a cutscene triggering when it shouldn't. Check any objects/common reactions that alter the hero in any way; move hero command, changing the state, etc. &#x20;

\-If this only happens on a certain map, and this map allowed walking on that spot before, but now it doesn't- \
Make sure there are tiles actually painted there and they can be walked on.\
Make sure you painted the correct tile where the hero is getting stuck. Some tilesets can have duplicate tiles that can't be walked on. \
Make sure there are no layered tiles on top that can't be walked on. You can try to erase and redraw, ensuring the correct layer is chosen.  \
Check the database/tilesets section to ensure the tiles are correctly configured.\
\
Check the collisions for hero and map objects.\
\
If you still can't move, report it. It could be a bug. \


&#x20;\
\---Q---\
What size are the resources? make templates for all resource types and list sizes\
\---A---\
For most of your resources there are no set sizes. The size will be determined by tile size, image size, frames, etc. There is no simple list like some other RPG Makers.&#x20;

The most relevent factor is tile size. All your resources should be divisible by the tile size. In the editor when you work with various elements like tilesets, hitboxes, collisions; your selection box size is determined by the tile size. If your graphics aren't divisible you won't be able to select whole pieces.&#x20;

There are many reasons to change the tile size but I recommend using the tileset as the base value. Drawing maps is pretty important and you need to be able to draw a single tile of the smallest size by default. For larger sprites, they occupy multiple tiles on the tileset and you simply draw them in a group. For most of the other resources the tile size doesn't matter. You simply create a canvas in multiples of the tile size and draw images of any size within them.&#x20;

This allows you to draw maps with tiles of 16x16 and make characters of any size.&#x20;

The effects of making a larger tile size need testing. \
\
WIP&#x20;

Does it require more processing/cause lag? Make a test map and find out how large you can make the tile size/chars before a basic map shows signs of lag. Then change the tile size to 16, changing nothing else, does it still lag?\
\
If you make tilesets and characters really large, how does it affect other resources like battle animations?\
\
With larger tile size, do maps need to be made larger to compensate? \
Or is the map width tied to tile size? (Tested, and it is)\
\
Does it change how "move object" commands work? Perhaps more of a problem if tileset and characters have a large difference in size.\
\
Does it affect the camera? Perhaps just larger values needed to move the larger distance?\
\
/WIP\
\
Types of Resources

&#x20;       Tilesets\
A single tile is equal to the tile size setting. Your tileset resource file can be of any size in multiples of the tile size.&#x20;

To determine the width and height of your resource file consider the following:

&#x20;       How will it look in the editor?&#x20;

The display box for your tileset can be resized and you will have a scroll bar if it's too large for the display box. Since it's much easier to scroll up and down, you might want to consider a tall, skinny file. \
\
Find out how much map editor space you want to balance it with, and use that to determine how many tiles wide your file is. I like about 11 tiles wide, then infinitely expanding down. When I need more room I simply make a larger file by adding to the bottom.&#x20;

The height limit is unknown, but so far has reached 912px without any sign of a problem. That's a single tileset file with 627 tiles in it.&#x20;

&#x20;       How large of an object do I want to draw on the map?\
\
In a typical retro game your character is 16x16. A tree might be 16x16. You might see some larger things like mountains or buildings at 32x32. When you add these things to a tileset it's possible to highlight the entire sprite and paint it in the map with a single click, instead of drawing each individual tile. So you may want a very wide tileset to make room for all the large sprites you will be drawing.

Drawing in this way can be tricky when it comes to centering. If you selected a large section of the tileset, let's say it's a house, it will always be drawn flush with the ground. The door touching the ground. If it's an even number of tiles, it will fit to the grid. If it's an odd number of tiles, it will not align one side to the grid. It will place it centered within the grid. You may need to adjust the position on the tileset to get the result you need.&#x20;

\*Some large sprites are better placed as objects/character sheets, but some things are easier on the tileset. Find what works best for you.\*

&#x20;       Characters\
The first step in making a character resource file is to make a single frame. The minimum size of this frame is equal to the tile size.&#x20;

Draw your sprite. If the sprite needs to be larger than the minimum tile size, then increase the size of the frame by multiples of the tile size. This can be done in either direction, as long as it's divisible by the tile size.&#x20;

16 x 16, 16 x 32, 32 x 16, 32 x 32, etc.&#x20;

If you increase the size of the frame, make sure you center the sprite inside the new frame. If it's not flying, make sure the bottom of the sprite is at the bottom of the frame. \
\
Once you create this frame, all other frames in the resource file MUST be the same size. If the sprite inside one of the frames is smaller, it still needs the uniform frame size.&#x20;

Now that you have a single frame, you will copy and paste it multiple times for form a grid. Each row is a direction so there will always be 4 rows. The number columns depends on System/animation frames. By default it's 4. So for a default character sheet paste it enough times to form a 4x4 grid of frames. If it's animated you would update each frame as needed.\
\
The frame on the left is the starting frame. \
\
When the engine reads a character resource file it calculates all that in reverse to determine the size of a single frame and how to animate. It cuts it into 4 rows for direction, and divides by animation frames. That is why you can make a character of any size.&#x20;

When making characters in new sizes, test how a single frame looks in game. You might need to make adjustments to it's position within the frame and it's best to figure it out early in the process. \
\
&#x20;       Battle Sprites\
This works like Characters. Each row being a certain stance: idle, attacking, getting hit, etc. The number of columns depends on a different setting, Systems/battler frames. The main difference is that there is also an option for battler rows, allowing you to create more stances.&#x20;

There is no size limit. You can make large battlers by increasing the frame size to allow for larger sprites, just like above.&#x20;

&#x20;        Battle Animations\
There is no size limit, but any animation file has to be a grid of 5x5 frames. The frames can be any size and do not have to match the tile size. However if your game uses large tile size and large resources, you will need to scale up the size of animations. \
\
&#x20;         Pictures\
These can be any size up to 4096x4096 pixels. This is a hard limit.&#x20;

You can use .png and .jpg file types.&#x20;

WIP

list of other types\
\
bars\
facesets\
gameover\
icons\
titlescreen\
windows skins\
autotiles\
mountains\
3d objects\
particles\
skyboxes\
walls\
\
all these need further testing and information\
\
/WIP\


\---Q---\
How to see sprites during top down view?\
\---A---\
Not available at this time. There are planned features to alter how sprites are drawn relative to the camera so they are always visible. \
\
\---Q---\
How to create a clock/timer?\
\---A---\
To create a timer you have a few methods.&#x20;

There is a built in timer command, but it's limited in scope. You can set timers and then use events to set a trigger. Needs further information/testing. \
\
The other main method is to use waits and variables. Have an object run on a loop where the code is:

wait 1sec\
variable TIMER +1\
IF TIMER =10\
&#x20;   put your code here

Every second the variable increases by 1 and you use a conditional branch to check when the timer reaches a certain amount to trigger some code. You can decrease the wait to 0.1 for milliseconds, you then have to increase the IF to 100. Or 0.01 for more accurate time. This will depend on what it's used for. \
\
That is for a variable counting up. If you want a variable to count down: \
\
Object 1\
variable TIMER =10

Object 2\
wait 1sec\
variable TIMER -1\
IF TIMER =0\
&#x20;  put your code here\
\
You would set it to 10 somewhere that only triggers once, change the code to subtract instead, and a branch to tell when it reaches 0. Again, which method and accuracy you choose will depend on what you're trying to do. \
\
For a clock, perhaps a feature or script will be added in the future. \
\
Using basic commands, the variable counting method works well. Have a common reaction that always runs and simply has:

wait 1sec\
variable TIME +1

This will have a single variable keeping track of seconds. You might add exceptions so time doesn't count when in battle for example. Just put this inside a conditional branches that makes sure a certain Switch is OFF. Like battle. When you get into a battle turn the switch on so time doesn't continue. After battle turn the switch ON to resume time. You can also change the speed of time by increases the variable by a larger amount. You can increase the TIME variable by other variable, so the player has control of time. \
\
There might be a way to make a formula to divide by 60 and so on to turn seconds into a readable time like 3:28 PM. But I accomplish like so:

wait 1sec\
variable TIME +1\
branch - IF TIME equals 60\
&#x20;   variable MINS =1\
&#x20;   variable TIME =0\
\
Every 60 seconds a minute is counted and the seconds are reset. Then you add a branch to check if MINS =60 and add an HOUR. If HOUR equals 12, or 24, reset them all. You get the idea. \
\
To see the current time the most basic method is a Show Text command where you input variables instead of text:\
\[var=1] : \[var=2]   : \[var=3]

(hours  :  minutes : seconds)

You could create a complex system that shows pictures for each number. Hopefully future features will allow direct drawing of text or numbers on screen using variables so this can easily be drawn on the screen without any downsides.&#x20;

\---Q---\
Where are the default resources located?\
\---A---\
If you didn't change the install directory you can find them at:\
C:\Program Files (x86)\RPG Paper Maker\Engine\Content\BR\Content\\\
\
It's best not to edit these directly or remove them from this folder. You can copy them to your project folder and edit the duplicates.&#x20;

\---Q---\
How do I place objects in the air?\
\---A---\
In RPM the width and height of the map are the X and Z coordinates. The height of an object is the Y coordinate. In the editor you can hold CTRL and UP/DOWN ARROWS to change which plane you are drawing on. If enabled, you will see the grid move up and down. This will help you pick the right Y level. (You can also use CTRL + Scroll wheel).&#x20;

Make it a habit to reset the Y back to ground level after you draw something at a different height. It's not fun to draw a lot of tiles on the wrong level and have to redo it all.&#x20;

\---Q---\
How do I change the font?\
\---A---\
First make sure the font files are in your projects /Font folder. Don't put them in the engine folder.&#x20;

Then click the Fonts button along the top of the editor. Move the fonts from the right side to the middle. You can rename the files here, but you will also have a chance to give them names in another spot.&#x20;

Now go to System and you will see the 2 groups that deal with font. Size and Names.

It's a good idea to set the sizes early on. Some fonts won't look good in the default sizes because they are rather small. Be aware that this will affect menus and shops, so do some testing for your specific fonts.\
\
The first item in Font Names is your default font. Therefore this is where your title screen font is set. You can add many other fonts to the list and change them with commands. Double click or edit an item and give it a name. Basic allows you to name the font or use a variable. Font ID allows you to choose from a dropdown. \
\
When you use a "Show Text" command, one of the dropdowns here let's you choose the font. You can even use different fonts in the same text box. Any changes here are temporary and won't affect the menu or future show text commands.&#x20;

To change the font for good use the "Set dialog box options" command. You can change size and font by checking only those boxes and nothing else. Anything that shows words will use this new default value. \


\---Q---\
How do I connect 2 maps?\
\---A---\
The most common method is to use an object placed on the tile the player will step on to move to another map. It might be the edge of a map, a hole in the ground, or a door to a house.&#x20;

The type of object will determine how it's triggered. A door might require the event be "Hero Action". A typical map transition will use a "Hero touch" event.&#x20;

In the code you will have a "Teleport Object" command. At the top make sure the player object is selected(usually Hero but can be something else). You have multiple options to choose which map you end up on. Most of the time you will click the select button and pick a specific spot.&#x20;

Sometimes there may be many tiles that the player can touch to be teleported to another map. Maybe the entire edge of the map. You could make copies of the above event and paste them along the entire edge, but there is an easier way. If you are not already, track the player's coordinates. Have some object always running with the following code:

Variable(HEROX) = object HERO x square position\
Variable(HEROZ) = object HERO z square position\
wait 0.1 sec\
\
The size of that wait determines how accurate the coordinates are. A smaller values checks the coordinates more often, but can cause lag if it's checking too much. You can only move so fast anyways. Too high and you might move 2 tiles before it checks again. 0.1 is usually good for all purposes. To reduce lag you might try 0.2 and it will still be fairly ac

The top left corner of the map is 0,0. The X coordinate is the first number and it runs from left to right. The Z coordinate is next and runs from top to bottom. Lets assume a map of 20x20. All the tiles along the right side of the map will have a X value of 0. So at any point if the hero coordinates have 0 as a value for X, that means the player is touching the left edge. So you would put in the code for teleporting to that map. And a single object is covering the entire edge.&#x20;

Where you end up is going to be a problem. You probably want it to match the same area on the next map. For that you need to use the "Map ID" section of the teleport command. You will need the number value of the map you're going to. The X value is going to be the right edge of the new map, so you will need to look that up. (remember the first tile is 0, so the 20th tile will be X=19). You can then plug in the Z variable, which was part of the tracking, to place the hero on the same Z tile as the previous map. This creates a system similar to early Zelda games. \
\
There is mention of a future feature for linking maps that might be easier than the above.&#x20;

It's also possible to not use objects at all and instead put multiple branch checks after each coordinate update. If X = 12 AND Z = 4, then you know the hero is stepping on a doorway and you put the teleport code here. That way you can keep all teleport related code in a single object, although it becomes a little abstract. Add comments that say which teleport each branch is, like "enter hero house", or "fall in well". It also allows you to reduce the number of objects on a map, which in some cases can cause lag on large maps if you have too many objs.   \


\---Q---\
\
\---A---

\---Q---\
\
\---A---

\
\
\
\
\
\
I got an error message, how can I report it?\
How do I stop X from walking through Y?\
How do I put things on walls?\
How do I change the default player sprite?\
How to make quick time events?\
How to make puzzles, mini-games?\
How to make custom menus?\
How to make custom battle system?\
How to make caterpillar system/visible teammates?\
How to make skill system/level up system?\
How to make item crafting?\
How to make ammunition for gun type weapon in battle?\
How to make quest/journal system?\
How to make options for volume, etc?\
How does TP work?\
How to make team/combo attack?\
How to make summon magic?\
How to make weather?\
How to make projectiles?\
How to make party switching menu?\
How to display a variable on screen?\
How to track hit detection?\
How to display a map / minimap?\
How to make events move on long complicated routes?

What file types can be used for music?\
How to use battle formulas?\
How large can a sprite be?\
How do I make the enemies bigger in battle?\
\
How to do actions like:\
Jump\
Push\
Pull\
Pick Up\
Throw\
Slide\
Climb\
Swim\
\
How to make a:\
Chest\
Door\
House\
Bridge\
Stairs\
\


## List of YouTube tutorials <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>

Wood\
\
This is a tutorial based on Paper Maker 1.6.1 and the game I made with it, Goblin Quest. Download the game and the assets used with it in #projects [https://drive.google.com/file/d/1jwdLfHUBIpbazcFTrcSwXz42D9QyA7BU/view?usp=sharing](https://drive.google.com/file/d/1jwdLfHUBIpbazcFTrcSwXz42D9QyA7BU/view?usp=sharing)Google Docs[RPG Paper Maker Tutorial #1 - Goblin Quest.pdf](https://drive.google.com/file/d/1jwdLfHUBIpbazcFTrcSwXz42D9QyA7BU/view?usp=sharing)\
&#x20;

!Marc🦈:&#x20;

[https://www.youtube.com/playlist?list=PLgifsmdb86qtMVTCW3J14dfWeNdPGGoeh](https://www.youtube.com/playlist?list=PLgifsmdb86qtMVTCW3J14dfWeNdPGGoeh) Useful tutorials by Cid. (Maybe still up to date?)(edited)YouTube[Cid's RPG Paper Maker Tutorials](https://www.youtube.com/playlist?list=PLgifsmdb86qtMVTCW3J14dfWeNdPGGoeh)Complete playlist of all my RPG Paper Maker tutorials.\


&#x20;Cid331:&#x20;

[https://youtu.be/56BeodBay60](https://youtu.be/56BeodBay60)[YouTube](https://www.youtube.com/)[Digital Container](https://www.youtube.com/channel/UCndVoWxj9WbMLBg0HM7KYdw)[RPG Paper Maker Tutorial - #013 Transportation](https://www.youtube.com/watch?v=56BeodBay60)\
\
terikumo:&#x20;

i messed up in the previous video, so i remade it [https://youtu.be/ynVupoA5ApU](https://youtu.be/ynVupoA5ApU)[YouTube](https://www.youtube.com/)[terikumo](https://www.youtube.com/channel/UCvd\_3bntrydnq5SOFfwdAHQ)[RPG Paper Maker Tutorial - Beginner: The Basics (#1)](https://www.youtube.com/watch?v=ynVupoA5ApU)\
\


## Placeholder <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>

## Tutorials from Discord <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>

\
\
\


```
RPG PAPER MAKER - how to have/make custom sprites. by Reptile
```

&#x20;So... Let we go to to `System menagement` (shortcut: 1) - and there we have `System` tab. On the very left, there is dialog options frame **MAP PROPERTIES** There you find `Square size (in px)`, this is where you say what is the size of your tiles (map elements). By default, it is 16x16 pixels. And as you take a look at the sample tileset, it goes like this

Every square of the tileset is 16x16. Your tileset file (PNG) it has to be made in similar way. 8 columns, and as rows as many as you wish. But here is the deal - if your tile in the map properties is set to example: `20` then remember, every element in the tileset it has to be 20x20 if you set 22, then 22x22 etc. **USUALLY!** Tilesets are 16x16, 20x20, 24x24, 48x48...

This is for tilesets, now let we talk about **CHARSETS** **CHARSETS** Again in the System management, System tab, below this **Map properties** there is another dialog box group option called **FRAMES** This is what you are interested in, if you want to change your characters frames etc.

[![](https://media.discordapp.net/attachments/565965228479610880/860018638757429289/unknown.png?width=238\&height=300)](https://cdn.discordapp.com/attachments/565965228479610880/860018638757429289/unknown.png)

`Map frame duration` - this is the speed animation rate for our charset, you can change the numbers to see the result. Usually I do not touch this since I am ok with it. Default: 150 `Animation Frames` - this decides for **how much frames** your charsets (all charsets!) in the game will have. Default: 4 Default charsets in RPM are using 4 frames.

[![](https://media.discordapp.net/attachments/565965228479610880/860019314332663808/bibi.png)](https://cdn.discordapp.com/attachments/565965228479610880/860019314332663808/bibi.png)

###

the animation it goes like: 1 - 2 - 3 - 4

Notice that frame 1 and 3 is the same.

Now if you wish to have MORE FRAMES of animation, you can insert there (in animation frames) `5` So the animation will be: 1-2-3-4-5 Charset while not moving - has frame #1 as idle.

###

> **CHARSET TEMPLATE**

The same rule as above for tilesets, user is deciding the size of the charset. It can be whatever you want. **BUT** there is one rule: EVERY FRAME it has to have the same size (width x height) As here in this template take a look:[![](https://media.discordapp.net/attachments/565965228479610880/860020136688877568/template.png)](https://cdn.discordapp.com/attachments/565965228479610880/860020136688877568/template.png)

Every square frame in this charset template has size: 32x32 if you would like to have taller charsets - hey, no problem, just you have to make first square bigger (example: 32x100), if you make like this, then remember - EVERY SQUARE HAS TO HAVE THE SAME SIZE (32x100)

> **EXAMPLE OF MAKING MORE FRAMES**

So let we give more frames to our characters...

In `animation frames` I set "5", so every charset will have 5 frames.

My charsets look like this:

[![](https://media.discordapp.net/attachments/565965228479610880/860021679338160138/testbox.png)](https://cdn.discordapp.com/attachments/565965228479610880/860021679338160138/testbox.png)

and this is also the animation, when it walks: it is 1-2-3-4-5 when it stands and wait, it is 1

[![](https://media.discordapp.net/attachments/565965228479610880/860021840096788480/suichartest.png)](https://cdn.discordapp.com/attachments/565965228479610880/860021840096788480/suichartest.png)

[![](https://media.discordapp.net/attachments/565965228479610880/860021842420039680/suichartest-2.png)](https://cdn.discordapp.com/attachments/565965228479610880/860021842420039680/suichartest-2.png)

of course this is just a test, as you can see I used a taller charset model (rip from suikoden) and I had change the last frame to standing green outfit. The animation is not good of course ![:wink:](https://discord.com/assets/2e41bfdeba797283ee9da9bb439c3ece.svg) but it works and you can use them for some tests.

> **BATTLERS**

[![](https://media.discordapp.net/attachments/565965228479610880/860022660657446912/kate.png)](https://cdn.discordapp.com/attachments/565965228479610880/860022660657446912/kate.png)

`Battler frames` - how many frames the battler should have. Default: 4 `Battlers rows` - how many rows, animations poses the battler should have Default: 9 As for animation, and size - rules are the same as for charsets. Animation play like: 1-2-3-4 As it goes for `Battler rows`, battler animation poses, notice that some states require this option. Take a look at Datas manager, `Status` tab. There is `Death` and notice the option Battler possition is set to 8

[![](https://media.discordapp.net/attachments/565965228479610880/860024174030094336/unknown.png?width=400\&height=232)](https://cdn.discordapp.com/attachments/565965228479610880/860024174030094336/unknown.png)

Why 8? Because take a look at the Kate.png battler - 8 is the last pose, and it is "death" or "KO"

> But in options there was 9, why 8?

Because I believe RPM is still in development, and battler poses it counts starting from "0"

> **BATTLER TEMPLATE**

[![](https://media.discordapp.net/attachments/565965228479610880/860024906897031168/template.png)](https://cdn.discordapp.com/attachments/565965228479610880/860024906897031168/template.png)

Take a note, it is the same rule as charset when it goes to size, and animation. Default frames are 32x32 - you want bigger battlers? No problem, set your 1st frame bigger (example: 50x50), and then also the rest of the frames also have to be 50x50. You want to have more animation frames? Chenge the option `Battle frames`, and in the file make more frames. Simple as that. Now last note, Battler rows, as for now I do not see more options for it. I mean you can use it in `State` (Death/KO), later on once there will be other states (Sleep/Dizzy/Poison etc) I believe it will be handy to set your own pose for that state. Maybe it would be also cool to have a feature to set your own animation (battler position) for skills! ![:slight\_smile:](https://discord.com/assets/da3651e59d6006dfa5fa07ec3102d1f3.svg) But we will see.

\* \* \* @Darkand - there you go, hope those infos were bit helpfull.

To the others moderators ( @Wano ![:smile:](https://discord.com/assets/626aaed496ac12bbdb68a86b46871a1f.svg) ) if you think this tip/notes are ok/useful, you can copy them and post on site, or pin them on discord or something.

\
\
\---

\
\
&#x20;MadToastCrunch:&#x20;

How would I make an entrance to a cave?

> **MadToastCrunch** How would I make an entrance to a cave?

&#x20;Draw a map, where you will see the entrance to the cave. On the entrance to the cave make a OBJECT (event) that looks like this: - no graphic - On the right you have **events** change that to `hero touch` - command: `Teleport object` - choose `Hero` - choose `CAVE MAP` - `Position select` and OK Done. Do not forget to make the same way EXIT from the cave.[![](https://media.discordapp.net/attachments/776751125629108224/860806836856946708/unknown.png?width=368\&height=300)](https://cdn.discordapp.com/attachments/776751125629108224/860806836856946708/unknown.png)

in my experience the teleport happens so fast that I add a small wait of around 0.4 after it, so the player doesn't accidentally walk back into the teleport if they are holding a movement direction. depending on where they end up on the other side\
\
\
\--------

\
SaltedSporks:&#x20;

Eyy I found out how to copy and paste between projects! [https://saltedsporks.itch.io/our-pigmented-bonds/devlog/241022/entry-9-dev-log-replace-copy-and-paste-maps-between-projects-tutorial-rpg-paper-maker](https://saltedsporks.itch.io/our-pigmented-bonds/devlog/241022/entry-9-dev-log-replace-copy-and-paste-maps-between-projects-tutorial-rpg-paper-maker)itch.io[Entry 9 - Dev log + Replace /Copy and Paste Maps Between Projects ...](https://saltedsporks.itch.io/our-pigmented-bonds/devlog/241022/entry-9-dev-log-replace-copy-and-paste-maps-between-projects-tutorial-rpg-paper-maker)There have been come major updates to the game. One of them gaining our new member to the team, Strange Sentinel! He's going to be helping me code some of the levels of the game. I've decided to find...[\
](https://img.itch.zone/aW1nLzQ5NzM4MjIuZ2lm/original/SS1sJe.gif)\
\
&#x20;SaltedSporks:&#x20;

Realized I made a tutorial about how I made rain in RPG paper maker, so I thought I'd share it! [https://saltedsporks.itch.io/our-pigmented-bonds/devlog/226687/entry-4-devlog](https://saltedsporks.itch.io/our-pigmented-bonds/devlog/226687/entry-4-devlog)\
\




KevinOfNine:



Using Weather

texture can be anything of course. it's actually possible to make it alternate between different texture by running another command with all the same values, but a different texture. however it needs to run in a loop for as long as it should be raining. you may want to use the wait and time feature, as needed. I made a test where it rains cats and dogs xD had to&#x20;

number of portions. simple, how many objects to have on the screen at one time, in one ray portion(explained below). dont make it too low, other wise you end up with big gaps(10 is too low for rain, imo).&#x20;

ray portion, is how much of the map gets the effect. or, how far out from the center it displays. when set to 1, it only rains on a small rectangle centered on the player. this is the default for rain. for snow it does 2 portions, therefore it draws snow further out from the player. you can kind of tell when it's swirling that it extend far out. I dont know the exact benefits of changing this, I suppose more gives depth but also would cause lag if too high. and you probably wouldnt see it all anyways&#x20;

size is the scale of the texture. you want to keep it small. but it depends, maybe you want it to rain down large rocks and lava from an erupting volcano.&#x20;

depthtest, this determines if it interacts with the map or if it shows the particles on top of everything. when ON, its a bit more laggy. I have a low end PC and when it's ON I get slight lag and if its OFF there is no lag. but when it's OFF, it looks TERRIBLE. when on, the particles will disappear when they touch part of your map&#x20;

depthwrite, not sure. probably a way of storing values of how far the textures are falling? probably not for the average user

Initial velocity - its default speed. negative values for falling. I suppose you could make bubbles and have them go up with a positive velocity, for an underwater map.&#x20;

velocity addition, better known as acceleration. by default this is a very very very small value with good reason. it will keep going and accelerate itself into a blur if allowed to go too high. if you adjust this, keep the numbers small initial&#x20;

y rotation. this determine how straight the textures fall. 0 is normal falling, like snow with 0 wind. as you increase it, it puts a spin on how it falls, like snow with some wind. although it appears to always move in a cyclone. again, use small values. 0.5 makes it rotate pretty hard&#x20;

y rotation addition, acceleration of this value. another one you want to keep very very small. I put something like 0.005 and it only took a few minutes for the slow cyclone to turn into a blur. probably not something to mess with, change the initial rotation and leave it be.

\
\
\
\
\
\
\
