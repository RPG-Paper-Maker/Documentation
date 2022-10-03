---
description: Frequently Asked Questions
---

# FAQ

## Can I make my character sprite object bigger? <a href="#are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have" id="are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have"></a>

Yes. The engine automatically cut the picture so you can make it any size. Just make the picture be multiple of the square size (16px).

## Are there all features from RPG Maker? <a href="#are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have" id="are-there-all-same-features-commandsfunctions-avaible-that-normal-rpg-maker-have"></a>

Almost all the RPG Maker commands and features are available.

## Can I use my own pictures / musics / 3D objects? <a href="#can-you-upload-in-this-app-your-own-textures" id="can-you-upload-in-this-app-your-own-textures"></a>

Yes.

## What's the max picture size? <a href="#whats-the-picture-size-format-support" id="whats-the-picture-size-format-support"></a>

4096x4096 pixels.



## What are the supported pictures formats? <a href="#whats-the-picture-size-format-support" id="whats-the-picture-size-format-support"></a>

.png, .jpg.

## What's the max size of a map? <a href="#whats-the-scale-or-game-world-size-support-in-this-game" id="whats-the-scale-or-game-world-size-support-in-this-game"></a>

For now the max map size is 1000 x 1000 squares. But there will be a feature for connecting large maps to create really huge maps like open worlds.

## Are there 4K resolution support? <a href="#are-there-4k-resolution-support" id="are-there-4k-resolution-support"></a>

No 4K for now but at least 1080p without problem.

## Can you directly edit pictures in the engine? <a href="#are-there-in-appsoftware-drawingtexture-tool-where-you-can-edit-draw-textures" id="are-there-in-appsoftware-drawingtexture-tool-where-you-can-edit-draw-textures"></a>

No.

## Can you set camera into "first person view"? <a href="#can-you-set-camera-into-first-person-view" id="can-you-set-camera-into-first-person-view"></a>

Yes. In map properties, change camera properties to FPS.

## Can you use gif animations? <a href="#can-you-use-gif-animations-or-parsed-series-of-images-that-app-can-use-into-animation" id="can-you-use-gif-animations-or-parsed-series-of-images-that-app-can-use-into-animation"></a>

GIF are not supported yet.

## Is that possible to make real time battles? <a href="#is-that-possible-to-make-real-time-battles-or-just-turn-based" id="is-that-possible-to-make-real-time-battles-or-just-turn-based"></a>

Now it's only turn based, but plugins will be available to implement different kind of battle.

## What are the tile size (squares size) ? <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>

Default are 16x16 pixels, but you can change to any value!

Questions from Discord\
 <a href="#what-are-the-tile-size-squares-size" id="what-are-the-tile-size-squares-size"></a>
---------------------------------------------------------------------------------------------

\---Q---\
How to import a custom file?\
\---A---

When you make a new project you determine the folder path. To find your project's resource folders navigate to that folder and open /resources/app/Content/ and you will see all the subfolders for each type of resource. Start by adding your files here.&#x20;

In the editor some of these resources will be ready to use right away. Some have their own lists and you need to add the resources to this list.&#x20;

You can drag files into these folders while the engine is open. You may need to need to save, open a database window, or reload the project for changes to appear. Most things are safe to add. If a resource has been added to one of the lists, make sure you update the list before removing the resource from the folder to avoid problems.&#x20;

\---Q---\
How to create footstep sound effects?\
\---A---

This depends on how your hero moves. By default this movement is in the "Hero" model, in the code for pressing the keys for each direction. It moves you by 1 step. If you add a sound effect here, it will play too fast.&#x20;

You could change the movement from step to square, moving in one full tile. If made to wait until complete, you can put the sound effect after the move and it plays with the correct timing. However this causes bugs with collision(try walking up slopes).&#x20;

One possible solution for step movement is that every time you take a step it turns on a switch. This switch is contained in a conditional branch that checks itself to be OFF, so it can only run one at a time. \
Another event is turned on by the switch and plays the sound effect. It waits the proper amount of time, around .4 seconds, and turns OFF the switch. This allows your next step to trigger another sound effect. If you have stopped moving, no further sounds.&#x20;

\---Q---\
How to create item drops? (ABS game style)\
\---A---\
For repeat drops, use the "Create object in map" command. This will allow you to spawn as many copies of the same thing as you want. \
Start by creating a new Model. Name it and assign the graphic. Add the code. \
Now go to the map object that spawns the item drop. Set up the trigger for dropping. \
Add the "Create object" command and choose your item drop model. \
A drop will be spawned out of thin air using the graphic and code set up in the model. \
Using this method you will need to manually keep track of IDs if you want to do anything other than spawn them. Despawn, move around, change, all require an ID to be assigned.&#x20;

Let's say we're talking about killing an enemy and it drops an item. You can use states to simply change the graphic and code without adding any new objects. This means both can't be displayed at once(the coin laying next to the dead body).&#x20;

Another method is to create an object in advance and make it invisible. When activated it is moved to any place on the map it is needed. This has the benefit of having preset IDs that can be organized in advance.&#x20;

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


What file types can be used for music?\
Why can't I move the hero?\
What size are the resources? make templates for all resource types and list sizes\
How to use battle formulas?\
How to see sprites during top down view?\
How large can a sprite be?\
How to create a clock/timer?\
Where are the default resources located?\
How do I make the enemies bigger in battle?\
How do I place objects in the air?\
How do I change the font?\
How do I connect 2 maps?\
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
How to make events move on long complicated routes?\
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
