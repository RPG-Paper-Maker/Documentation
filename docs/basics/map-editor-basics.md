# Map editor basics

After opening a project, you should have this view:

![Screenshot](img/map-editor.png)

## Manage maps

Take a look at the map selector **(1)**. You can add, edit, remove, copy, and paste folders or maps here. We recommend that you use folders to sort your maps for each zones of your game. By default, there's also a `Battle maps` folder that you can use to put all the maps that you will use for battle backgrounds. It is not required to put these maps into this specific folder. Clicking on a map will load this one on the map editor **(5)**. `Right clicking` will open this context menu:

![Screenshot](img/new-map.png)

If you want to create / edit a map, you will get this window:

![Screenshot](img/map-properties.png)

* `Name`: The map name.
* `Tileset`: A tileset represents a lot of information applied on a specific set of textures (collisions, dynamic textures,...). We will see how to configure it in a next chapter.
* `Length`: The map length number of squares (X axe).
* `Width`: The map width number of squares (Z axe).
* `Height`: The map height number of squares (Y axe > 0).
* `Depth`: The map depth number of squares (Y axe < 0).
* `Music`: The music that is played in the background when entering the map.
* `Background sound`: The background that is played in the background with the music. This can be wind, rain, etc.
* `Camera prop. ID`: The camera property ID used when entering the map.
* `Sky color`: The color used for the sky.
* `Map startup reactions`: You can configure here particular things happening when entering the map. We will se later how to do that thanks to objects.
* `Battles`: **(not implemented yet)**

## Move cursor / grid / camera

The camera is always looking at the following cursor:

![Screenshot](img/cursor.png)

Here are some actions possible with the cursor:

* Move on `X` and `Z` axis by using `QWSD` on keyboard.
* Move on `Y` axis: 
	* Move by square: use `CTRL + Arrow Up/Down` or `CTRL + mouse wheel`
	* Move by pixel: use `CTRL + SHIFT + Arrow Up/Down` or `CTRL + SHIFT + mouse wheel`

![Screenshot](img/y-axis.png)

* Teleport the cursor on the pointed element square by using `CTRL + Left click`.

To move the camera position, press the `mouse wheel` and move the mouse in the direction you want:

![Screenshot](img/camera-turn.gif)

## Place / Remove elements

The map element selection portion **(3)** allows you to select kind of element to place in the map (lands, sprites, objects, reliefs, etc.). You can add or remove something in a specific square by clicking left or right.

For example with a floor:

![Screenshot](img/map-editor-add-remove.png)

## Undo / Redo

You can go back / after a change in each map. Press `CTRL+Z` for undo and `CTRL+Y` for redo.

## Save changes

To save your map editor changes, you can use these shortcuts in the toolbar:

![Screenshot](img/save.png)

* `Save`: Save the changes on the current opened map.
* `All`: Save the changes on all the modified maps. A map has been changed when you see a `*` after its name:

![Screenshot](img/map-save.png)

## Show / Hide some UI details

* `G`: Show / Hide grid
* `I`: Show / Hide information about the pointed square:

![Screenshot](img/square-infos.png)

## Change paint mode

Here are the different paint mode **(4)** for drawing your elements in the map:

![Screenshot](img/paint.png)

* `Pencil`: Draw squares one by one.
* `Rectangle`: Draw squares after tracing a rectangle **(not available yet)**.
* `Pin of paint`: Fill squares with the same texture as the one pointed.

## Lands

Here are the possible lands to place:

![Screenshot](img/lands.png)

## Floors

The texture selector **(2)** allows you to select a rectangle for a texture. After selecting a rectangle, place your mouse on a square of your map to place your floor.

![Screenshot](img/add-floor.png)

## Autotiles

Autotiles are dynamic floors. This will have borders with automatic changing according to the neighbor squares:

![Screenshot](img/autotiles-preview.png)

In the texture selector **(2)**, you just have to select a square:

![Screenshot](img/autotile-texture.png)

## Animated autotiles

*Not available yet.*

## Sprites

![Screenshot](img/sprites.png)

Sprites are vertical planes that can be used to simulate a "paper" world. Here are the different types of sprites:

![Screenshot](img/sprites-preview.png)

* `Face Sprite`: A sprite that is always facing the camera on the X / Y axe.
* `Fix Sprite`: A flat sprite. 
* `Double Sprite`: Two crossing flat sprites.
* `Quadra Sprite`: four crossing flat sprites.

Another kind of sprites are `Walls Sprite` that are dynamic (such as autotiles).

![Screenshot](img/walls-preview.png)

In the texture selector **(2)**, you just have to select a wall:

![Screenshot](img/walls-texture.png)

## Mountains

You can add some reliefs to your map thanks to mountains!

![Screenshot](img/mountains-preview.png)

In the texture selector **(2)**, you have several possible options for designing your mountains:

![Screenshot](img/mountains-texture.png)

* `Top floor`: The floor that whill be automatically added on top of the mountains. This floor depends on the tileset texture. Click on the `...` button to edit the top floor.
* `Border width`: If the border width is equal to zero, this will be a 90° mountain. You can adjust here the width of the borders of the mountains (this will create small slopes).
	* `Square(s)`: Select the number of squares.
	* `Pixel(s)`: Select the number of pixels added.
* `Height`: The total height of the mountain.
	* `Square(s)`: Select the number of squares.
	* `Pixel(s)`: Select the number of pixels added.

Note that you can se the angle value bellow these options so you can refer to this for angle collisions in `Systems manager > System`.

## 3D Objects

There are not only sprites, but also 3D objects available for your maps! 

![Screenshot](img/objects-3d-preview.png)

In the texture selector **(2)**, you just have to select an object:

![Screenshot](img/objects-3d-texture.png)

## Objects

All the previous elements were static (it doesn't move). There are objects in order to add some life on your map. This can be NPCs, chests, etc.

![Screenshot](img/objects.png)

We will see later how to manage it because this is one of the biggest topics of the engine.

## The hero

To define where the game should start, you have to define who is the hero in one of your maps. When you create a new project, the hero is the character at the center of the first map. If you want to change it:

* Create a new object (`Double click` on a square)
* Remove all the states and events from the lists (by using `Del` on keyboard) and choose `Hero` as model in the combo box. You can name it "Hero" if you want. You should have something like this:

![Screenshot](img/model-hero.png)

* Click on `OK`. `Right click` on your object, and choose `Define as Hero`.

![Screenshot](img/define-hero.png)

That's it! You will understand later why we are using an object and why this will open a lot of opportunities for customizing your games!

*Note:* You can see who is the hero with a "S" symbol under it.

![Screenshot](img/hero.png)

## Transformations

In 3D, transformations are these 3 different action:

### Translation

*Not available yet.*

### Rotation

Apply rotation to sprites or 3D objects only.

![Screenshot](img/rotate.png)

If you left / right click a map element, this will select the object and apply the current configured transformation. You can choose the axis `X`, `Y`, or `Z` to apply the rotation on by selecting the corresponding tab.

![Screenshot](img/rotation-panel.png)

* `[Selected object]`: Display information about the current selected object bellow. New transformations will be applied to this selected object.
* `+ / =`: The operation to apply on transformation (add or apply).
* `Angle`: The angle to add or apply to the selected object.
* `Apply on left / right click`: If checked, you will apply the transformation each time you click on a selected object. If `+` operation is activated, right click will in fact be a `-` operation. If not checked, updating `angle` will immediately update the selected object.
* `Define as default X/Y/Z rotation`: Save current `angle` input in engine settings so you get this value in the `angle` input each time you restart the engine.
* `Reset to default X/Y/Z rotation`: Fill current `angle` input with the saved default rotation value.

### Scaling

*Not available yet.*

## Layers options

You can choose here if you want to be on layer mode or not here:

![Screenshot](img/layers.png)

* `No layer`: Replace the selected square by a new one.
* `Layer`: Add a new square on top of the selected one. There is no limit.

Example of layers used with walls:

![Screenshot](img/walls-layers.png)