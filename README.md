---
description: This is the initial page of RPG Paper Maker documentation.
---

# Getting started

Welcome to RPG Paper Maker documentation! You will find here all what you need to be a pro Paper Maker!

## Installation <a id="installation"></a>

Go to the [download section](http://rpg-paper-maker.com/index.php/downloads#content) from the official website and download the installer according to your system.

### Windows <a id="windows"></a>

Run `RPG Paper Maker installer.exe`. This will install the program on your computer and run `RPG Paper Maker.exe`. This will ask you for downloading the latest version of RPG Paper Maker. Wait for the downloading to be finished.

### Linux <a id="linux"></a>

Extract the file. Check out the `README` instructions in the root of the folder. After running the last instruction \(`./run.sh`\), this will ask you for downloading the latest version of RPG Paper Maker. Wait for the downloading to be finished.

### MacOSX <a id="macosx"></a>

Extract the file. After running `RPG Paper Maker.app`, this will ask you for downloading the latest version of RPG Paper Maker. Wait for the downloading to be finished.

## Change theme <a id="change-theme"></a>

There actually are two different themes: `Dark` and `White`. If you want to change it, go to `Options > General options...`.

![](.gitbook/assets/themes-options.png)

## Create a new project <a id="create-a-new-project"></a>

You can create a new project by clicking here on the main toolbar:

![](.gitbook/assets/new-project.png)

You can also use `CTRL+N` or go to `File > New project...`.

![](.gitbook/assets/new-project-window.png)

You can choose here the `Project name` corresponding to your game's name. This will auto generate a folder name \(you can disable the option `auto-generate` if you want to customize your folder name\). And finally, choose the `location` of your project folder. By default, it will be on a freshly created `RPG Paper Maker Games` folder.

## Open an existing project <a id="open-an-existing-project"></a>

You can open an existing project by clicking here on the main toolbar:

![](.gitbook/assets/open-project.png)

You can also use `CTRL+O` or go to `File > Open project > Browse...`. Recent projects can also be opened on the first screen \(or go to `File > Open project`\).

## Change general game settings <a id="change-general-game-settings"></a>

A lot of options are available in the `Systems manager`. Click here on the main toolbar and go to the `System` tab:

![](.gitbook/assets/system-basic.png)

* `Game name`: Change the name of your game.
* `Game native resolution`: Change width / height resolution and also choose if you want a Window or Fullscreen display. `Display console` option is for programing debugging.
* `Display console`: _\(not available yet\)_ When testing your game, a console is displayed to print Javascript warnings/errors/logs.
* `Antialiasing`: _\(not available yet\)_ If checked, antialiasing will be applied in game.
* `Map properties`:
  * `Square size (in px)`: choose here the size \(in pixel\) of a square in your maps. You should adapt your textures after any change here.
  * `Ray portions (editor)`: _\(not available yet\)_ The map is separated into several portions \(16x16 squares\). You can change here the number of portions to display.
  * `Ray portions (ingame)`: _\(not available yet\)_ Same but for ingame.
  * `Mountain collision height limit (in px)`: The height considered for blocking the hero so the hero can go up blocks that are in inferior height value.
  * `Mountain collision angle limit (in degree)`: The angle considered for blocking the hero so the hero can go up mountains that are in inferior angle value.
  * `Animation frames`: Number of frames available in an animation \(walk, battlers, etc.\).
  * `Map frame duration`: Time in milliseconds for a frame of a map \(characters\).
* `Global sounds`:
  * `Cursor`: Sound to play when the cursor is moving in window choices.
  * `Confirmation`: Sound to play when the cursor is confirming in window choices.
  * `Cancel`: Sound to play when canceling something.
  * `Impossible`: Sound to play when a choice is impossible in window choices.
* `Other options`:
  * `Window skin`: The default windows skin used for designing windows UI.
  * `Max number of save slots`: _\(not available yet\)_ Change the max number of save slots available for the players.
  * `Price of sold item`: _\(not available yet\)_ Change the percent value of the original price of an item when you want to sell it in a shop.

## Change language <a id="update-keyboard-controls"></a>

You can change the engine language in `Options > Change language...`:

![](.gitbook/assets/change-language.png)

## Update keyboard controls <a id="update-keyboard-controls"></a>

You can change the engine and game keyboard controls in the keyboard manager by clicking on the main toolbar:

![](.gitbook/assets/keyboard-manager.png)

For engine:

* `CursorUp`, `CursorDown`, `CursorLeft`, `CursorRight`: The cursor directions in map editor.

For Game:

* `UpHero`, `DownHero`, `LeftHero`, `RightHero`: The hero directions in map.
* `UpMenu`, `DownMenu`, `LeftMenu`, `RightMenu`: The directions in menus.
* `LeftCamera`, `RightCamera`: Turn the camera.
* `Action`: Hero action in map.
* `Cancel`: Cancel in menus.
* `Main menu`: Open / Close main menu.

Select the corresponding system menus controls: `Action`, `Cancel`, `Up`, `Down`, `Left`, `Right`. You can add as much keys as possbile.

When adding / editing a key:

* `Abbreviation`: Name used for JavaScript use \(for programers\).
* `Description`: Will be displayed ingame for the keyboard settings menu.
* `Shortcut`: Change the shortcut here. Press the corresponding shortcut thanks to `Change...` button. You can have several shortcuts for one action \(separated with `|` symbol\) and also several keys for one shortcut \(separated with `+` symbol\).
  * `Remove last`: Remove the last shortcut \(on the right\).
  * `Remove all`: Remove all the entered shortcuts.

## Update general colors <a id="update-general-colors"></a>

Go to the `Systems manager > System` and take a look on the `Colors` box:

![](.gitbook/assets/colors.png)

## Update general font sizes and font names <a id="update-general-font-sizes-and-font-names"></a>

Go to the `Systems manager > System` and take a look on the `Font size` and `Font name` box:

![](.gitbook/assets/deepinscreenshot_select-area_20200323082522.png)

## Change game name <a id="change-game-name"></a>

Go to the `Systems manager > System` and take a look on the `Game name` box:

![](.gitbook/assets/game-name.png)

This will affect the window title when you are launching the game.

## Change game screen resolution <a id="change-game-screen-resolution"></a>

Go to the `Systems manager > System` and take a look on the `Game native resolution` box:

![](.gitbook/assets/game-resolution.png)

* `Width`: The native width of your game window.
* `Height`: The native height of your game window.
* `Window`: Choose a window mode.
* `Full screen`: choose full screen mode. Note that `Width` and `Height` have no effect with this option.

## Test your game <a id="test-your-game"></a>

You can test your opened project by clicking here on the main toolbar:

![](.gitbook/assets/play.png)

## Deploy your game <a id="deploy-your-game"></a>

If you want to publish your game \(share your game without any need for players to have RPG Paper Maker installed\) you have to go to `File > Export standalone...`.

![](.gitbook/assets/deploy.png)

* `Location`: The location of the standalone folder that you want to create. The name of this folder will be `yourGameName{OS}`.
* `Type of export`: Choose export options here.
  * `Deploy a desktop application`: Choose here to deploy your game as a desktop application \(choose the `OS` in options: Windows, Linux, or Mac\).
  * `Deploy for web browser`: _\(not available yet\)_ Choose here to deploy your game as a web application. This will generate an `index.html` page and other files.
* `Version`: Choose you game version. Having 1 for `major` and 0 for `minor` will create a 1.0 version.

## Enable / Disable Updater <a id="enable-disable-updater"></a>

Go on `Help > Auto display updater` to enable or disable the auto check of updater that will check if a new version is available or not.

![](.gitbook/assets/autoupdater.png)

