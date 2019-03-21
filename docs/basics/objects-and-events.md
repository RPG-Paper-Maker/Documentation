# Objects & Events

You know how to create beautiful maps, but you want to make it be alive by adding NPCs, treasures, etc. These elements are called `objects`. These objects will also react to `events` (hero action, chronometer, attack, etc.). Objects and events are here to galvanize your maps and create your game stories!

## Events

**/!\ Events in RPG Paper Maker are a different notion than in RM classic series.**

You can access to events in `Systems manager > Events / States`.

![Screenshot](img/event-states.png)

Events represent the fact that something important just happened and the objects in the map can react or not to it. An event can be for example the fact that your hero pressed the action button, or even the fact that a rain tempest just started. These events are sent to objects by other objects. There are two types of events:

* **System events** (time, keyboard pressure, etc.) that are not sent by objects in the map, but by the game system itself.
* **User events** (quest completed, sword hit) that you can be created by yourself and sent thanks to local objects.

An event also takes some `parameters`. For example, if you want to play a sound each three seconds in the background, you can use the time event with the parameter time = 3000 (milliseconds) and repeat = ON. Imagine such amazing things you can do with parameters (a sword hit event taking a power parameter for example). You can choose the default value of a parameter when editing parameters of an event.

**/!\ Don't confuse physics and events. You should not use events for wind animations or gravity, etc.**

## Reactions

Reactions are a tree of commands that will be executed one by one. For example a command can be to display text on screen or to move specific objects in the map. Here is an example of reaction:

![Screenshot](img/example-reaction.png)

This reaction will check if the variable myValue is equal to 2. If it's OK, this will display the message "It's OK!". If not, this will display the message "Go back later.".

To edit / add a new command in a reaction, `Double click` on a corresponding node. This will open this window containing a large list of commands:

![Screenshot](img/event-commands.png)

We will see later all these commands details one by one.

You can also copy / paste / delete by `Right-clicking` on the corresponding command node.

## Common reactions

If you see that you are often copying the same set of commands a lot of time maybe you should consider creating a common reaction. You can access to these in `Systems manager > Common reactions`.

![Screenshot](img/common-reactions.png)

This way you will be able to call this common reaction instead of always copying it. It's even taking parameters if you have some variations in your reaction.

* `Blocking hero`: If checked, the hero will not be able to move until the reaction is finished.

## Objects

An object is something that can move or/and react to some events in a map. So basically a tree is not an object (except if you can cut it so it would have a reaction to an axe hit) but only a static element. It can be a NPC, a monster, or anything else. Note that your hero is an object itself so you can perfectly program its reactions.

To add an object in a map, select the `Object` map editor section. Point on a map square and `Double click` or press `Enter` after clicking on the square. This will open a new window.

![Screenshot](img/object-map.png)

* `Name`: Choose a name for your objects. This can help later if you want to execute actions on this object externally.
* `Model`: Choose a model for this object. We will see later how to configure models.

### Events

You can configure which event the object can react to in the `Events` section. `Double click` on a node:

![Screenshot](img/event.png)

You can select if you want a user or system event and change parameters value:

![Screenshot](img/event-parameters.png)

System events are the following:

* `Time`: Event sent when time interval is cleared.
	* **Interval** (default: 0): Time to wait in milliseconds.
	* **Repeat** (default: ON): Send the event after each interval or once.
* `Chronometer`: *Not available yet.*
* `KeyPress`: Event sent when pressing a key on keyboard.
	* **ID** (default: anything): The ID of the key.
	* **Repeat** (default: OFF): If ON, this event will be sent as long as you press the key with a small offset at the first pressure.
	* **Immediate repeat** (default: OFF): If ON, this event will be sent as long as you press the key without any offset.
* `KeyRelease`: Event sent when releasing a key on keyboard.
	* **ID** (default: anything): The ID of the key.

### States

An object has a set of `States`. For example, the hero can be in a normal state, or poisoned / vulnerable. Note that an object can be in several states at the same time. 

![Screenshot](img/object-state-second.png)

For each state, you have to choose different reactions to specific events. You can copy / paste reactions through states by using `Copy reaction` and `Paste reaction` buttons. These different options are also available for each state:

* `Graphics`: Select the object graphics here (character picture). Choose below the kind of element (Sprite etc.).
* `Moving`: *(not available yet)* Options linked to the object moves.
* `Move animation`: If checked, all the frames of the character will be drawn for move animation. If not, this will only draw the first frame of the character animation.
* `Stop animation`: *(not available yet)* If checked, all the frames of the character will be drawn for stopped animation. If not, this will only draw the first frame of the character animation.
* `Climb animation`: *(not available yet)* If checked, all the frames of the character will be drawn for climbing animation. If not, this will only draw the first frame of the character animation.
* `Direction fix`: *(not available yet)* If checked, the graphics will not change direction to look at the hero. If not, it will look at the hero.
* `Set with camera`: If checked, the graphics will update orientation according to the camera orientation. If not, the camera orientation changes nothing.
* `Pixel offset`: If checked, the move animation will go 1px down after two frames. This adds an interesting effect.
* `Keep position`: *(not available yet)* If checked, the object always keep its position after moving, even after loading save or changing map. If not, the object position is reinitialized after loading save or changing map.

### Properties

*Not available yet.*

The object also has a set of properties. It can be HPs, age, gender, etc. It all depends on what you need and your type of game.

## Example: create a chest

Here is a simple way to produce a chest:

* Be sure to have a state for the chest in the systems manager when it is opened:

![Screenshot](img/states-opened.png)

* Complete reactions for each state and don't forget to replace state at the end of the normal state:

![Screenshot](img/state-1.png)
![Screenshot](img/state-2.png)

## Edit / Copy / Paste / Delete an existing object

You can open a context menu by `Right clicking` on an object:

![Screenshot](img/object-context-menu.png)

## Models

Models are objects that can be commonly used. You can have models list in `Systems manager > Models`.

![Screenshot](img/object-hero.png)

For example, if you want to add flowers that can be picked in your maps, you can create a model "Flower", and use this model for an empty object in your map:

* Create model:

![Screenshot](img/model-flower.png)

* Use model flower for a map object:

![Screenshot](img/object-model-flower.png)

### Default model

The model with ID 1 is the default model when you create a new object. You can change here the default informations to have in an object creation.

### Hero model

The hero is also an object and reacts to a lot of systems events:

* `KeyPress > Up, Down, Left, Right Hero`: Move the object hero to the pressed directions thanks to move object command.
* `KeyPress > Left, Right Camera`: Change the camera orientation thanks to move camera command.
* `KeyPress > Action`: Send the custom event `HeroAction` to the facing square objects thanks to the send event command.
* `KeyPress > MainMenu`: Open the main menu thanks to the open main menu command.

### Inheritance

If an object uses a model but also has content, this new content will replace some of the model content. Models themselves can have models.

* **State**: If there is a state with the same ID, the model reactions for this state ID will be replaced by the current content.
* **Property**: If there is a property with the same name, the model reactions for this property name will be replaced by the current content.
* **Event**: This has no influence.