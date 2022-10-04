---
description: An overview about event command
---

# Event commands list

Now that you are a pro for objects and event, you can have here a description of ALL the possible event commands. If there's a command or an option that you don't understand, you can go back here and search for a description.

## Show text <a href="#show-text" id="show-text"></a>

![](<../.gitbook/assets/command-show-text (1).png>)

Displays a text in a dialog box with the current dialog box options.

* `Interlocutor`: This will display a text inside a small box on top of the text box for indicating the interlocutor's name. If empty, this will not show the box.
* `Faceset`: The faceset to display inside the dialog box on the left.
* `Message`:
  * <img src="../.gitbook/assets/bold.png" alt="" data-size="line"> : Apply bold effect on the selected text.
  * <img src="../.gitbook/assets/italic.png" alt="" data-size="line"> : Apply italic effect on the selected text.
  * <img src="../.gitbook/assets/text-left.png" alt="" data-size="line"> : Apply left align effect on the selected text.
  * <img src="../.gitbook/assets/text-center.png" alt="" data-size="line"> : Apply center align effect on the selected text.
  * <img src="../.gitbook/assets/text-right.png" alt="" data-size="line"> : Apply right align effect on the selected text.
  * `Font size`: Apply the selected font size on the selected text.
  * `Font name`: Apply the selected font name on the selected text.
  * `Text color`: Apply the selected text color on the selected text.
  * `Back color`: Apply the selected back color on the selected text.
  * `Outline color`: Apply the selected outline color on the selected text.
  * `Variable`: Display the value of the current selected variable.
  * `Parameter`: Display the value of the current selected parameter.
  * `Property`: Display the value of the current selected property.
  * `Hero name`: Display the name of the selected hero instance ID.
  * `Icon`: Display the selected icon.

Render in game:

![](../.gitbook/assets/render-hello-world.png)

## Display a choice <a href="#display-a-choice" id="display-a-choice"></a>

![](../.gitbook/assets/command-display-choice.png)

* `Choices`: The list of choices texts.
* `Options`:
  * `Cancel auto index`: The choice index to select when pressing cancel button.

Using adapted show text command:

![](../.gitbook/assets/commands-display-choice.png)

![](../.gitbook/assets/render-command-display-choice.png)

Using without show text command before:

![](../.gitbook/assets/commands-display-choice-without-text.png)

![](../.gitbook/assets/render-command-display-choice-without-text.png)

## Input number <a href="#input-number" id="input-number"></a>

![](../.gitbook/assets/event-command-input-number.png)

Display spinboxes so the player can choose a number. Like Display a choice command, you can have a Show Text command before it so you have the text box and input number in the same time.

* `Stock value in variable ID`: The variable ID where the entered number will be stocked
* `Digits`: The number of digits for the number

Render in game:

![](../.gitbook/assets/render-input-number.png)

## Set dialog box options <a href="#set-dialog-box-options" id="set-dialog-box-options"></a>

![](../.gitbook/assets/command-dialog-box-options.png)

Set all the dialog box options.

* `Window skin ID`: The window skin ID to display.
* `Transform`:
  * `X`: The x position of the window.
  * `Y`: The y position of the window.
  * `Width`: The width of the window.
  * `Height`: The height of the window.
* `Padding`:
  * `Left`: The left padding of the window.
  * `Top`: The top padding of the window.
  * `Right`: The right padding of the window.
  * `Bottom`: The bottom padding of the window.
* `Faceset`:
  * `Position`: The position of the faceset. You can choose if it's behind or above the window.
  * `X`: The additional x position of the faceset.
  * `Y`: The additional y position of the faceset.
* `Text`:
  * `Outline`: Select if texts should have outlines.
  * `Color ID`:
    * `Text`: The color ID to use for texts.
    * `Outline`: The color ID to use for outlines.
    * `Background`: The color ID to use for backgrounds.
  * `Size ID`: The size ID to use for texts.
  * `Font ID`: The font ID to use for texts.

## Change screen tone <a href="#change-screen-tone" id="change-screen-tone"></a>

![](../.gitbook/assets/command-change-screen-tone.png)

Change the screen tone (dominant color). The RGB color (0, 0, 0) changes nothing on the screen tone.

* `Red`: The red dominant color.
* `Green`: The green dominant color.
* `Blue`: The blue dominant color.
* `Grey`: The grey dominant color (saturation). If grey = 0, then no changes. If grey = 100, then the screen will only have grey colors.
* `Adding color ID`: You can combine the previous color with an existing color.
* `Wait the end of the change before the next command`: If checked, the command will end only after `Time` number.
* `Time`: Time to wait for changing the screen tone.

## Shake screen <a href="#shake-screen" id="shake-screen"></a>

![](../.gitbook/assets/command-shake-screen.png)

This is useful for staging your cinematics by simulating earthquakes, for example.

* `Offset`: The number of pixel offset for each shake.
* `Shake number`: The number of shakes per second.
* `Wait the end of the move before the next command`: If checked, the next command will be executed when the shakes ends.
* `Time`: Duration of the total shakes.

## Flash screen <a href="#flash-screen" id="flash-screen"></a>

![](../.gitbook/assets/command-flash-screen.png)

This will simply fill your screen with a color and linearly go back to normal screen color.

* `Color ID`: The color ID to display on screen.
* `Wait the end of the move before the next command`: If checked, the next command will be executed when the flash ends.
* `Time`: Duration of the flash.

## Change weather <a href="#change-meteo" id="change-meteo"></a>

![](../.gitbook/assets/command-change-weather.png)

Change the current map weather by adding particles.

* `None`: Remove current map weather.
* `Custom`: Add a custom map weater.
* **Options**:
  * `Texture`: The weather particle texture.
    * `Color ID`
    * `Image`
  * `Number per portion`: Number of particles in each portion (16x16 squares)
  * `Ray portions`: Number of portions (16x16 squares) ray around the camera to display particles.
  * `Size`: The particles size (texture).
  * `dephTest`: [https://threejs.org/docs/#api/en/materials/Material.depthTest](https://threejs.org/docs/#api/en/materials/Material.depthTest)
  * `depthWrite`: [https://threejs.org/docs/#api/en/materials/Material.depthWrite](https://threejs.org/docs/#api/en/materials/Material.depthWrite)
  * `Initial velcity`: The initial velocity of the particle when it's created.
  * `Velocity addition`: Velocity addition after each frame.
  * `Initial Y rotation`: The initial Y rotation around the portion.
  * `Y rotation addition`: Y rotation addition after each frame.
* `Wait the end of the move before next comand`: Wait the end of the time before running next command if checked.
  * `Time`: Time (in seconds) to make the weather transition. There will be more and more particles appearing.

## Change map properties <a href="#change-map-properties" id="change-map-properties"></a>

![](../.gitbook/assets/command-change-map-properties.png)

Change some of a map properties.

* `Map ID`: The map ID that you want to change
* **Properties**:
  * `Tileset ID`
  * `Music`
  *
  * `Background sound`
  * `Camera properties ID`
  * `Sky`
    * `Color ID`
    * `Skybox ID`

## Wait <a href="#wait" id="wait"></a>

![](../.gitbook/assets/command-wait.png)

Wait during a specific time.

* `Time`: Time to wait in seconds.

## Change chronometer <a href="#change-chronometer" id="change-chronometer"></a>

![](../.gitbook/assets/command-change-chronometer1.png)

![](../.gitbook/assets/command-change-chronometer2.png)

Start, pause, continue, or stop a chronometer.&#x20;

If you choose to `start` a new chronometer:

* `Stock chronometer ID in variable ID`: The variable ID where you want to stock this new chronometer ID
* `Time`: The time count for this new chronometer
* `Display on screen`: If checked, display the chronometer on screen

If you choose to `pause`, `continue`, or `stop` an existing chronometer:

* `Chronometer ID`: The existing chronometer ID to edit
* `Stock current chronometer value in variable ID`: Stock the current value (in seconds) in the variable ID.

## Teleport object <a href="#teleport-object" id="teleport-object"></a>

![](<../.gitbook/assets/command-teleport-object (1).png>)

This will teleport an object on an existing map with a new position.

* `Object ID`: The object ID to teleport.
* **Position**:
  * `Select...`: Choose map and position thanks to a map previewer.
  * `ID map`, `X`, `Y`, `Y plus`, `Z`: Choose map ID an position to go manually.
  * `Object (ID)`: Choose an object to teleport on.
* **Transition**:
  * `Direction`: Select the direction of the object after teleportation
  * `Start / End`: Start / End type of transition:
    * `None`: Immediate transition.
    * `Fade in / out`: Transition on a color.
    * `Zoom in / out`: Transition by zooming in / out.

## Move object <a href="#move-object" id="move-object"></a>

![](<../.gitbook/assets/command-move-object (1).png>)

This will move an object in the current map with a specific route. You can also temporary change some properties linked to the object state.

* `Object ID`: The object ID to move.
* `Ignore if impossible`: If checked, the moves that can't be executed (example: a wall blocking the route) would be ignored. If not checked, this will try the impossible move as long as it become possible (example: use for NPCs moving).
* `Wait the end of moves`: If checked, the command would end only when all the moves are executed. If not, the command would end immediately (moves executed in parallel).
* `With camera orientation`: If checked, the direction moves (north, south, west, east) would take account of the camera orientation. If not, the direction moves would not take account of the camera orientation.
* **Step / square moves**:
  * `Square`: Change all the direction moves unit to square.
  * `Step`: Change all the direction moves unit to step.
  * `1 to North / South / West / East / North-West / North-East / South-West / South-East`: Move the object to 1 square / step in the selected direction.
  * `1 to random`: Move the object to 1 square / step in a random direction.
  * `1 to the hero`: Move the object to 1 square / step in the hero direction.
  * `1 opposite to the hero`: Move the object to 1 square / step in the opposite of the hero direction.
  * `1 in front`: Move the object to 1 square / step in front.
  * `1 back`: Move the object to 1 square / step back.
  * `Jump...`: Make the object jump:
    * **Final position offset**: The final position offset in the end of the jump
    * **Peak**: The peak Y values (offset)
    * `Time`: The time execution of the move
* **Change direction**:
  * `Turn North / South / West / East`: Turn the object in the selected direction
  * `Turn 90° left / right`: Turn the object 90° in the left or right
  * `Look at the hero`: Turn in the hero direction
  * `Look at hero opposite`: Turn in the opposite of the hero direction
* **Change object options**:
  * `ON / OFF`: For some options, you can use the option ON or OFF
  * `Permanent`: If checked, the object option will be conserved even after saving
  * `Change speed / frequency`: Change the speed or frequency value
  * `Move animation`: Change the move animation to ON or OFF
  * `Stop animation`: Change the stop animation to ON or OFF
  * `Climb animation`: Change the climb animation to ON or OFF
  * `Direction fix`: Change the direction fix to ON or OFF
  * `Through`: Change the through to ON or OFF
  * `Set with camera`: Change the set with camera to ON or OFF
  * `Pixel offset`: Change the pixel offset to ON or OFF
  * `Keep position`: Change the keep position to ON or OFF
  * `Change graphics`: Change the obejct graphics
  * `Wait / Play sound / Script`: Use the following commands

## Display an animation <a href="#display-an-animation" id="display-an-animation"></a>

![](../.gitbook/assets/command-display-an-animation.png)

Display an animation in the current map.

* `Object ID`: The object ID where the animation will be played.
* `Animation ID`: The animation ID to play.
* `Wait the end of the animation before next command`: If checked, the next command will be executed only after the animation end.

## Move camera <a href="#move-camera" id="move-camera"></a>

Check out the camera guide [here](camera-control.md).

## Reset camera <a href="#reset-camera" id="reset-camera"></a>

This command will simply reset the camera properties after using move camera command, but it won't change the current camera target.

## Create object in map <a href="#create-object-in-map" id="create-object-in-map"></a>

![](../.gitbook/assets/event-command-create-object-in-map.png)

Create an object in the map. Note that this object will be removed after changing map or quitting the game.

* `New object model ID`: The model ID for the object that will be created
* **Position**: Select the position of the new object
* `Stock ID in variable ID`: The variable ID where you will stock the new object generated ID

## Remove object from map <a href="#remove-object-from-map" id="remove-object-from-map"></a>

![](../.gitbook/assets/command-remove-object-from-map.png)

Remove an object from the map. This removing is effective as long as you don't change map or load the game in saves.

* `Object ID`: The object ID to remove in the map.

## Display a picture <a href="#display-a-picture" id="display-a-picture"></a>

![](../.gitbook/assets/command-display-picture.png)

Display a picture on top of the screen.

* `Image ID`: The image ID to display.
* `Index`: The index of the image to display. You can display several images in the same time if they have different index. The more the index is high, the more the image is displayed on top. If two images have the same index, then the ancient image will be removed.
* `Origin`:
  * `Top / Left`: The origin position will be (0, 0) (= top left of the screen).
  * `Center`: The origin position will be the center of the screen.
* `Coordinates`:
  * `X`: The x position according to the origin.
  * `Y`: The y position according to the origin.
* `Effects`:
  * `Zoom`: The % zooming of the image.
  * `Opacity`: The % opacity of the image.
  * `Angle`: The ° angle of the image.

## Set / Move / Turn a picture <a href="#set-move-turn-a-picture" id="set-move-turn-a-picture"></a>

![](../.gitbook/assets/command-set-move-turn-picture.png)

Set / Move / Turn a picture that is already displayed on top of the screen.

* `Image index`: Select the index of the image to set / move / turn.
* `Set`:
  * `Image ID`: Change the image ID to display.
  * `Zoom`: Change the % zooming of the image.
  * `Opacity`: Change the % zooming of the image.
* `Move`:
  * `X`: Change the x position according to the origin.
  * `Y`: CHange the y position according to the origin.
* `Turn`:
  * `Angle`: Change the ° angle of the image.
* `Wait the end of the actions before the next command`: If checked, the command will end only after `Time` number.
* `Time`: Time to wait for updating the picture.

## Remove a picture <a href="#remove-a-picture" id="remove-a-picture"></a>

![](../.gitbook/assets/command-remove-picture.png)

Remove a picture that is displayed on top of the screen.

* `Image index`: Select the index of the image to remove.

## Play a video <a href="#play-a-video" id="play-a-video"></a>

![](../.gitbook/assets/command-play-a-video.png)



Play, pause, or stop a video. The video will be displayed on top of the screen.

* `Video`: The video ID to play.
* **Operation**: The kind of operation to do: `Play`, `Pause`, or `Stop`.
* `Start`: If checked and using `Play` operation, the video will be played at the indicated value (in seconds).
* `Wait the end of the change before next command`: If checked, the next command will be executed only when the video is finished/paused/stopped.

## Start shop menu <a href="#start-shop" id="start-shop"></a>

![](../.gitbook/assets/event-command-shop-menu.png)

This will open a menu for a shop where the player can buy or sell items.

* `Buy only`: Indicate if you want to enable selling items or not
* `Shop ID`: Indicate the shop ID. This will be used only if you want to use command `Restock shop` later.
* `Items / Price / Stock`: Select the items to sell with their price and stock

![](../.gitbook/assets/event-command-shop-menu-item-price-stock.png)

* **Item**:
  * `Item ID`
  * `Weapon ID`
  * `Armor ID`
* **Price**:
  * `Default`: The default price indicated in the item datas
  * `Specific`: A specific price that you can indicate here
* **Stock**:
  * `Unlimited`: An unlimited stock
  * `Specific`: A spercific stock that can indicate here

Render in game:

![](../.gitbook/assets/event-command-shop-menu-render.png)

## _Restock_ shop <a href="#start-shop" id="start-shop"></a>

Mostly the same options than [Start shop menu command](event-commands.md#start-shop), but you can use this command to update the stock of a shop thanks to `shop ID`.

## Enter a name menu <a href="#enter-a-name" id="enter-a-name"></a>

![](../.gitbook/assets/event-command-enter-a-name-menu.png)

This will open a menu in order to change the name of a specific player.

* `The hero with instance ID`: Select the variable containing the player instance ID
* `Max characters`: The max number of characters that you can edit

Render in game:

![](../.gitbook/assets/render-enter-a-name-menu.png)

## Open main menu <a href="#open-main-menu" id="open-main-menu"></a>

This will open the main menu.

Render in game:

![](../.gitbook/assets/render-main-menu.png)

## Open saves menu <a href="#open-saves-menu" id="open-saves-menu"></a>

This will open the saves menu.

Render in game:

![](../.gitbook/assets/render-saves-menu.png)

## Title screen <a href="#title-screen" id="title-screen"></a>

Go to the title screen.

## Game over <a href="#game-over" id="game-over"></a>

Go to the game over screen.

## Play a music <a href="#play-a-music" id="play-a-music"></a>

![](../.gitbook/assets/command-play-music.png)

This will play a music on the current map.

* `Select song by ID`: Instead of using the left list, you can select by ID values.
* **Options**:
  * `Volume`: The music volume (in %).
  * `Start`: The beginning time of the music in seconds.
  * `End`: The end time of the music in seconds.

## Stop music <a href="#stop-music" id="stop-music"></a>

![](../.gitbook/assets/command-stop-music.png)

This will stop the music played in the current map.

* `Disappear with time`: Number of seconds for music played for disappearing.

## Play a background sound <a href="#play-a-background-sound" id="play-a-background-sound"></a>

This will play a background sound on top of the current music.

Check out the play music command [here](event-commands.md#play-a-music) that is similar.

## Stop background sound <a href="#stop-background-sound" id="stop-background-sound"></a>

This will stop the background sound played in the current map.

Check out the stop music command [here](event-commands.md#stop-music) that is similar.

## Play a sound <a href="#play-a-sound" id="play-a-sound"></a>

This will play a sound on top of all the songs.

Check out the play music command [here](event-commands.md#stop-music) that is similar.

## Play a music effect <a href="#play-a-music-effect" id="play-a-music-effect"></a>

This will play a music by pausing the current played music. When the music effect is finished the previously played music is unpaused.

Check out the play music command [here](event-commands.md#play-a-music) that is similar.

## Change battle music <a href="#change-battle-music" id="change-battle-music"></a>

Select a music to change the battle music for every next coming battles.

## Change victory music <a href="#change-victory-music" id="change-victory-music"></a>

Select a music to change the battle victory music for every next coming battles.

## Send event <a href="#send-event" id="send-event"></a>

![](<../.gitbook/assets/command-send-event (1).png>)

This will send an event to the selected target.

* **Target**:
  * `All`: Send the event to all the objects visible in the map
  * `Detection`: Send the event to a specific detection.
    * `Sender can't receive`: The detection is not applied to the sender.
    * `Only the closest`: If checked, this will only send event to the closest object detected. If not, this will send event to all the objects detected.
  * `Object`: Send the event to a specific object.
* **Event**:
  * `Event system`: Select a system event (events sent by the game system itself).
  * `Event user`: Select a user event (custom events sent by the map objects).
  * `Parameters values`: Select the event parameters values. You can keep the default value.

## Change state <a href="#change-state" id="change-state"></a>

![](../.gitbook/assets/command-change-state.png)

This will change the state of the current object. An object can have several states at the same time.

* **Object**:
  * `Map ID`: The map ID to change state.
  * `Object ID`: The object ID to change state.
* **Selection**:
  * `State ID`: The new state ID.
* **Operation**:
  * `Replace`: Remove all the current states of the object and add the new state.
  * `Add`: Only add the new state.
  * `Remove`: Remove the object state having this ID.

## Change property <a href="#change-property" id="change-property"></a>

![](../.gitbook/assets/command-change-property.png)

This will change a property value of the current object.

* **Selection**:
  * `property ID`: The property ID to change.
* **Operation**: The operation to use according to the current property value.
* **Value**:
  * `New value`: The new value to apply to the property with the corresponding operation.

## Modify currency <a href="#change-money" id="change-money"></a>

![](../.gitbook/assets/command-modify-currency.png)

Change the currency value.

* **Selection**:
  * `Currency ID`: The currency ID to change value.
* **Operation**: The operation to apply to the currency value.
* **Number**: The number value to apply to the currency.

## Modify inventory <a href="#modify-inventory" id="modify-inventory"></a>

![](../.gitbook/assets/command-modify-inventory.png)

This will update inventory containing. You can for example add items to it.

* **Selection**:
  * `Item ID`: An item to select.
  * `Weapon ID`: A weapon to select.
  * `Armor ID`: An armor to select.
* **Operation**: The operation to use according to the current number of the selection in the inventory.
* **Number**: The value to use for updating the selection number.

## Modify team <a href="#modify-team" id="modify-team"></a>

![](<../.gitbook/assets/command-modify-team (1).png>)

This will update team organization.

* `Create new instance with level ... in team / reserve / hidden of`: Create a new instance of a hero or monster in team, reserve, or hidden.
  * `Stock instance ID in`: Choose a variable where you want to stock the instance ID. This can be useful to move or remove characters in team.
* `Add enemy with instance ID ... in team / reserve / hidden`: Add an enemy that is in a current battle in team, reserve, or hidden
* `Modify`: Move or remove a character with instance ID

## Allow / Forbid saves <a href="#allow-forbid-saves" id="allow-forbid-saves"></a>

![](../.gitbook/assets/command-allow-forbid-saves.png)

* `Allow`: If checked, the saves menu will be allowed.

## Allow / Forbid main menu <a href="#allow-forbid-main-menu" id="allow-forbid-main-menu"></a>

![](../.gitbook/assets/command-allow-forbid-main-menu.png)

* `Allow`: If checked, the main menu will be allowed.

## Change general options <a href="#change-general-options" id="change-general-options"></a>

_Not available yet._

## Start a battle <a href="#start-a-battle" id="start-a-battle"></a>

![](../.gitbook/assets/command-start-battle.png)

This will start a battle with your team against a troop (group of monsters).

* **Troop's ID**:
  * `ID`: Fix troop ID.
  * `Random (in map property)`: Random ID indicated in map property window.
* **Battle map**:
  * `ID`: Fix battle map ID.
  * `Select...`: Choose battle map and position thanks to a map previewer.
  * `ID map`, `X`, `Y`, `Y plus`, `Z`: Choose battle map ID and position to go manually.
* **Options**:
  * `Allow escape`: If checked, it would be possible to use battle command `Escape` in this battle.
  * `Defeat causes Game Over`: If checked, losing in this battle will automatically direct to game over. If not checked, there will be two commands container : one for the winning state, and the second for the losing state.
* **Transition**:
  * `Start / End`: Start / End type of transition:
    * `None`: Immediate transition.
    * `Fade in / out`: Transition on a color.
    * `Zoom in / out`: Transition by zooming in / out.

## Display / Hide enemy <a href="#display-hide-enemy" id="display-hide-enemy"></a>

_Not available yet._

## Force an action <a href="#force-an-action" id="force-an-action"></a>

![](../.gitbook/assets/command-force-an-action.png)

During a battle, this will force an hero or enemy to execute an action on a target.

* **Battler**: The battler that should execute the action
  * `Enemy`: Select an enemy of the current troop
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable
* **Action**: The action to execute
  * `Use skill ID:` Select a skill with a specific ID
  * `Use item ID:` Select an item with a specific ID
  * `Do nothing`
* **Target**:
  * `Random`: A random target
  * `Last target`: The last target that the battler selected
  * `Custom`:
    * `Enemy`: Select an enemy of the current troop
    * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable

## End battle <a href="#end-battle" id="end-battle"></a>

You can use the end battle command in troops reactions to force a defeat.

## Change battle music <a href="#change-battle-music_1" id="change-battle-music_1"></a>

You can select a battle music for the next battles.

## Change victory music <a href="#change-victory-music_1" id="change-victory-music_1"></a>

You can select a victory music for the next battles.

## Change a statistic <a href="#change-a-statistic" id="change-a-statistic"></a>

![](../.gitbook/assets/command-change-a-statistic.png)

You can here change a statistic value to one or several characters (heroes or enemies).

* `Statistic ID`: The statistic ID to change value.
* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable.
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`.
* **Operation**: Select the operation to apply to the current statistic value.
* **Value**:
  * `Number`: Choose a dynamic number value.
  * `Formula`: Enter a formula as a value.
  * `Maximum statistic value`: Take the maximum value of a statistic (used to heal maximum HP, for example)
  * `Can go above maximum value`: If checked, the given value can be superior to maximum value of the statistic.

## Change experience curve <a href="#change-experience-curve" id="change-experience-curve"></a>

![](../.gitbook/assets/command-change-experience-curve.png)

Change the experience curve table of one or several players.

* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`
* **Level**:
  * `Range`: The level range to apply the experience curve changes
* **Operation**: The operation to use according to the current experience value
* `Total experience`:  The total experience to change in the table

## Change status <a href="#change-status" id="change-status"></a>

![](../.gitbook/assets/event-command-change-status.png)

Add or remove a player status.

* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable.
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`.
* **Operation**: Choose to add or remove the status
* **Status**:
  * `Status ID`: The status ID

## Change a skill <a href="#change-a-skill" id="change-a-skill"></a>

![](../.gitbook/assets/command-change-a-skill.png)

Choose if you want a character to learn or forget a specific skill.

* `Skill ID`: The skill ID to learn or forget.
* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable.
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`.
* **Operation**: Choose here if you want to learn or forget the selected skill.

## Change name <a href="#change-name" id="change-name"></a>

![](../.gitbook/assets/command-change-name.png)

Choose a character you want to change the name. This isn't like the command enter hero name, this doesn't open any HUD so the player can enter a name.

* `Name`: The new character name.
* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`

## Change class <a href="#change-class" id="change-class"></a>

![](../.gitbook/assets/command-change-class.png)

Change one or several players class. This will apply changes on statistics and learned skills.

* `Class ID`: The new class ID to apply
* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`

## Change equipment <a href="#change-equipment" id="change-equipment"></a>

![](../.gitbook/assets/command-change-equipment.png)

You can force a character to equip a weapon or an armor.

* `Equipment ID`: The equipment slot ID to force equip.
* `with Weapon ID / Armor ID`: The weapon or armor ID to force equip (according to equipment ID).
* **Selection**:
  * `Hero / Enemy instance ID`: Select the instance ID of a character. They are mainly stocked into a variable.
  * `The entire`: Select a group, this can be the `team`, `reserve`, or `hidden`.
* `Apply only if in inventory`: If checked, the equipment is not equiped if not in inventory. If not checked, the item will be added to inventory and then equiped.

## Condition <a href="#condition" id="condition"></a>

Create a container for commands that will be executed only if the indicated condition is true.

* `Add "else" when conditions do not apply`: Create another container for commands that will be executed only if the indicated condition is false.
* **Variables / Param / Prop**:

![](../.gitbook/assets/command-conditions.png)

* `This`: Compare a variable or a parameter or a property with any other type of value.
* **Heroes**:

![](../.gitbook/assets/command-condition-heroes.png)

* `Hero(es)`: Select `all the heroes` or `none of the heroes` or `at least one hero` or `the hero with instance ID`. in `team` or `reserve` or `hidden`.
  * `Are named`: Check if the selection have this name.
  * `Are in`: Check if the selection is in the `team` or `reserve` or `hidden`.
  * `Are able to use the skill ID`: Check if the selection is able to use the selected skill ID.
  * `Are equiped with`:
    * `weapon ID`: Check if the selection is equipped with the selected weapon ID.
    * `armor ID`: Check if the selection is equipped with the selected armor ID.
  * `Are under effect of status ID`: _Not available yet._
  * `Have the statistic ID`: Compare a selected statistic of the selection with any other type of value.
* **Possessions**:

![](../.gitbook/assets/command-condition-possessions.png)

* `Currency ID`: Compare a selected currency number with any other type of value.
* `Item ID`: Compare a selected item number in inventory with any other type of value.
* `Weapon ID`: Compare a selected weapon number in inventory with any other type of value.
  * `Check weapons equiped too`: If checked, the equipped weapons will be included in the number of weapons.
* `Armor ID`: Compare a selected armor number in inventory with any other type of value.
  * `Check armors equiped too`: If checked, the equipped armors will be included in the number of armors.
* **Others**:

![](../.gitbook/assets/command-condition-others.png)

* `Key ID`: Check if selected key is ON or OFF.
* `Escaped last battle`: Check if the player escaped last battle (using escape battle command).
* `Script`: Check according to the script return value (for programmers).

## Loop <a href="#loop" id="loop"></a>

Create a container for commands that will be executed on a loop.

## Break loop <a href="#break-loop" id="break-loop"></a>

If inside a loop container, this will go out of the loop and go to the next command after the loop.

## Label <a href="#label" id="label"></a>

![](../.gitbook/assets/command-label.png)

Add label to your reaction, you will combine it with jump to label command. You can choose any name you want.

## Jump to label <a href="#jump-to-label" id="jump-to-label"></a>

![](../.gitbook/assets/command-jump-label.png)

Combined with label command, you can choose to move to the named label. Here is a nexample that will create a loop:

![](../.gitbook/assets/example-label.png)

The commands will be executed like this:

Condition ? > No > End if >Jump to label loop > Label loop > End if > Jump to label loop > Label loop > ...

## Stop the reaction <a href="#stop-the-reaction" id="stop-the-reaction"></a>

Stop the current reaction.

## Comment <a href="#comment" id="comment"></a>

![](../.gitbook/assets/command-comment.png)

Comments won't be interpreted in game, it's only here for you. You can leave a comment in specific places to remember why you used specific commands.

![](../.gitbook/assets/example-command-comment.png)

## Call a common reaction <a href="#call-a-common-reaction" id="call-a-common-reaction"></a>

![](../.gitbook/assets/command-call-common-reaction.png)

This will call a common reaction with the corresponding parameters.

* `Common reaction`: The common reaction to call.
* **Parameters values**: The parameters to apply with the common reaction.

## Change variables <a href="#change-variables" id="change-variables"></a>

![](<../.gitbook/assets/command-change-variables (1).png>)

This will change one or several variable(s) value.

* **Selection**:
  * `One variable`: The unique variable to change
  * `Range`: The range of variables IDs to change
* **Operation**: The operation to use according to the current variable(s) value
* **Value**:
  * `Number`: A simple number
  * `Random`: A random number between two selected values
  * `Message`: A simple message
  * `Switch`: A simple switch
  * `Number of ... in inventory`: The number of item / weapon / armor that are currently in the inventory
  * `Total currency ... with ID`: The total number of a specific currency (owned, earned, or used)
  * `Hero / Enemy instance ID ... statistic ID`: Get a statistic value according to a player instance ID
  * `An object in the map ... characteristic`: The selected object characteristic:
    * `X square position`: The x square position of the selected object.
    * `Y square position`: The y square position of the selected object.
    * `Z square position`: The z square position of the selected object.
    * `X square position`: The x pixel position of the selected object.
    * `Y square position`: The y pixel position of the selected object.
    * `Z square position`: The z pixel position of the selected object.
    * `Orientation`: The orientation of the selected object.
  * `Enemy ... instance ID`: The selected enemy instance ID
  * `Other characteristics`:
    * `Current map ID`: The current map ID
    * `Number in team`: Number of players in team
    * `Number in hidden`: Number of hidden players
    * `Number in reserve`: Number of players in reserve
    * `Total number of steps`: Number of steps made by the hero
    * `Total number of seconds`: Number of seconds playtime
    * `Total number of saves done`: Number of saves done since starting the game
    * `Total number of battles`: Number of started battles
    * `Camera X position`: The camera X position
    * `Camera Y position`: The camera Y position
    * `Camera Z position`: The camera Z position
    * `Total seconds played of the current music`: The total number of seconds played of the current music
    * `Total seconds played of the current background music`: The total number of seconds played of the current background music

## Script <a href="#script" id="script"></a>

![](<../.gitbook/assets/command-script (1).png>)

Execute a script code (for advanced programmers). Note that you can use `$object` local variable to get the Core.MapObject current object!&#x20;

* `Use dynamic`: Non-static code (in variable, or parameter, or property).
