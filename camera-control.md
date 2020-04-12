---
description: Being director of your game.
---

# Camera control

In your 2D games, you are limited to screen moves for adding dynamism to your important scenes. A 3D camera offers a lot of opportunities for your scenes \(moves, rotations, zooms...\) and you need to know some easy basics to use it correctly.

![Camera control sample](https://rpg-paper-maker.github.io/basics/img/camera-example.gif)

## The camera <a id="the-camera"></a>

First, you should know what is a camera. Just imagine that you are a cameraman for a great movie. The first two things required for filming a scene are:

* **The camera position**
* **The target position** \(= where the camera is looking at\)

Thanks to the scripts, these two positions are always calculated thanks to algorithms. These positions will be calculated according to:

* The **target position** and a potential **offset**
* The **distance** between the camera and the target
* The **horizontal angle** between the camera and the target
* The **vertical angle** between the camera and the target

## The distance <a id="the-distance"></a>

![](https://rpg-paper-maker.github.io/basics/img/camera-distance.png)

The distance is simply a positive value indicating the distance between the camera and the target. This should take account of the three axis. This will be used for zooms. The default value is 125.

## The horizontal angle <a id="the-horizontal-angle"></a>

![](https://rpg-paper-maker.github.io/basics/img/camera-h.png)

The horizontal angle is only applied to the X and Z axis. For example, if you want to turn around your target horizontally, you will have to change this value. The default value is -90°.

## The vertical angle <a id="the-vertical-angle"></a>

![](https://rpg-paper-maker.github.io/basics/img/camera-v.png)

Same as the vertical angle but only applied to the Y axis. For example, if you want to turn around your target vertically, you will have to change this value \(to go down you have to increment the value, and to go up you have to decrease the value\). The default value is 55°.

## The move camera command <a id="the-move-camera-command"></a>

Here we are, now that you know a bit more about the camera properties we can see how to dynamically move it. The Move Camera event command is here for it!

![Move camera Command](https://rpg-paper-maker.github.io/basics/img/command-move-camera.png)

* **Camera target**: By default, the camera is always looking at the hero.
  * `Unchanged`: Keep the current camera target.
  * `Object ID`: _\(not available yet\)_ If you are selecting a new object ID to focus, the camera will move to its position and will consider it as the new target after it.
* **Operation**: You can select here the kind of operation you want to apply to the modified values. For example, if you choose \(+\) and you set distance to 5, if the previous distance value was 125 it will become 125 + 5 = 130.
* **Move**: You can modify here the camera position on the three axis \(you can choose squares by squares or pixel by pixel\).

  * `Target offset`: if this option is checked, you will move the camera and the target offset positions at the same time. In 2D games, it's like if you only wanted to move the screen and ignore the hero position.

  _Moving X+10 squares with target offset OFF:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-move-off.gif)

  _Moving X+10 squares with target offset ON:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-move-on.gif)

  * `Take account of camera orientation`: _\(not available yet\)_ This is simply considering that the axis are modified according to the camera position \(see the same option for [Move Object command](event-commands.md#move-object)\).

* **Rotation**: You can here modify the horizontal and the vertical angle of the camera in order to apply rotations.

  * `Target offset`: Same as for moves. This time, the target will turn around the camera.

  _Adding 360° to the horizontal angle with target offset OFF:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-h-r-off.gif)

  _Adding 360° to the horizontal angle with target offset ON:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-h-r-on.gif)

  _Adding 360° to the vertical angle with target offset ON:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-v-r-off.gif)

  _Adding 360° to the vertical angle with target offset ON:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-v-r-on.gif)

* **Zoom**: You can set the distance between the camera and the target to create a zoom effect.

  * `Distance`: The distance to update in pixels.

  _Adding -100 pixels to the distance:_

  ![Screenshot](https://rpg-paper-maker.github.io/basics/img/camera-zoom.gif)

* `Wait the end of the move before the next command`: Wait the end of the move before the next command \(same as for the [move object command](event-commands.md#move-object)\). It can be used to execute commands while the camera is moving \(display texts, sounds...\).
* `Time`: Indicate here the time in seconds for the camera to move to its final position. If 0, the move will be immediate.

## Camera properties <a id="camera-properties"></a>

You can control the default properties of the camera when you are going into a new map. You can set the camera ID in `map properties`. You also have access to the camera properties list in `Systems manager > System`:

![Camera properties](https://rpg-paper-maker.github.io/basics/img/camera-properties.png)

* `Name`: The name of the camera properties.
* `Distance`: The distance between the camera and the hero.
* `Horizontal angle`: The horizontal angle between the camera and the hero.
* `Vertical angle`: The vertical angle between the camera and the hero.
* `Target offset`: A position on every axes for adding an offset to the target position.
* `Field of fiew`: The angle used to determine the angle vision limit of the camera. We recommend to keep the default value.
* `Near`: Min distance between camera and elements for being drawn. We recommend to keep the default value.
* `Far`: Max distance between camera and elements for being drawn. We recommend to keep the default value.

