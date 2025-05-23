# Battle system

If you want to create to create a RPG, you may need a battle system. Here, we will see all the features linked to the battle implementation.

![](../.gitbook/assets/battle-demo.gif)

_Note: if you want to do an action RPG (battles directly on maps), you can do it through object & events_

## Battle system datas <a href="#battle-system-datas" id="battle-system-datas"></a>

A lot of battle system datas can be found in `Systems Manager > Battle System:`

![](<../.gitbook/assets/battle-system (1).png>)

## Elements <a href="#elements" id="elements"></a>

![](../.gitbook/assets/elements.png)

You can manage here all the elements that you want to have in your game for influencing your damages effects.

* `Name`: Name displayed in game UI.
* `Icon`: Icon displayed in game UI.
* **Efficiency**: You can edit here how efficient is the current element against all the other existing elements. This is pretty usefull when the element is assigned to a class. By default, it's x1.0 (normal effect).

## Common statistics <a href="#common-statistics" id="common-statistics"></a>

![](../.gitbook/assets/battle-statistic.png)

You can manage here all the statistics that you want to have in your game for influencing your battles (HPs, lvl, strength, etc.).

* `Name`: Name displayed in game UI.
* `Script abbreviation`: Choose here an abbreviation. This will be used for game scripts, choose something without capital letter if possible.
* **Properties**:
  * `Fix`: If checked, this statistic would be a fix value (not a bar).
  * `Bar`: If checked, this statistic would be a bar value (an actual value + max value).

## Common battle commands <a href="#common-battle-commands" id="common-battle-commands"></a>

![](../.gitbook/assets/battle-commands.png)

Choose which battle commands you want to have after selecting a hero to do something.

* `Skill`: Choose the corresponding skill.

Render in game:

![](../.gitbook/assets/battle-commands-preview.png)

## Common equipment <a href="#common-equipment" id="common-equipment"></a>

Choose the name of common equipment so you will be able to equip weapons / armors on these equipment slots.

## Weapons / Armors kind <a href="#weapons-armors-kind" id="weapons-armors-kind"></a>

![](../.gitbook/assets/battle-weapon-armor-kind.png)

Create a weapon / armor kind and also choose on which equipment you can assign it.

* `Name`: Name for this kind of weapon / armor.
* Selection of equipment you can assign.

## Battle maps <a href="#battle-maps" id="battle-maps"></a>

![](../.gitbook/assets/battle-maps.png)

Battle maps are in fact maps associated with a specific position (representing the center point of the battle). Select a map (by default in the `Battle Maps` folder in the map selector) and a position to add a new battle map.

## Statistics associations <a href="#statistics-associations" id="statistics-associations"></a>

* `Statistic associated to level`: Choose one of your fix statistic to associate with level. Level is a statistic that is increasing for the character evolution: leveling up will increase other statistics.
* `Statistic associated to exp`: Choose one of your bar statistic to associate with experience. Experience is something earned generally after finishing a battle. Once experience goes to its maximum value, the character is leveling up and the map experience bar increases too.

## Formulas <a href="#formulas" id="formulas"></a>

* `Is dead`: Formula in JavaScript defining conditions to consider that a character is dead. `u` corresponds to the character.
* `Critical influence`: Formula in JavaScript defining the new damages value after having a critical hit. `damage` corresponds to the damages done without critical influence.
* `Heroes battlers center offset:` Formula in JavaScript defining the position of heroes battlers according to the center of the map battle.
* `Heroes battlers offset:` Formula in JavaScript defining the position of heroes battlers according to other heroes position (where `i` is the hero index).
* `Troops battlers center offset:` Formula in JavaScript defining the position of troops battlers according to the center of the map battle.
* `Troops battlers offset:` Formula in JavaScript defining the position of troops battlers according to other enemies position (where `i` is the enemy index).

## Battle musics <a href="#battle-musics" id="battle-musics"></a>

* `Battle`: Battle music used during the battle.
* `Level up`: Sound used when a hero is leveling up.
* `Victory`: Music used during the victory end battle phase.

## Currencies <a href="#currencies" id="currencies"></a>

Go to `Systems Manager > System`.

![](<../.gitbook/assets/currencies (1).png>)

Currencies can be used in the game for trading with NPCs or any other way.

* `Name`: Name of the currency.
* `Icon`: Icon associated with the currency.

## Skills / Items / Weapons / Armors <a href="#skills-items-weapons-armors" id="skills-items-weapons-armors"></a>

Go to `Datas Manager`.

In `Skills` tab:

![](<../.gitbook/assets/skills (2).png>)

In `Items` tab:

![](../.gitbook/assets/items.png)

In `Weapons` tab:

![](../.gitbook/assets/weapons.png)

In `Armors` tab:

![](../.gitbook/assets/armors.png)

These four data have common properties:

* `Name`: Name of the data.
* `Type`: Select the type of item / armor / weapon.
* `Consumable`: If checked, the data will disappear after using the data.
* `One hand`: _Not available yet._
* `Icon`: Icon associated with the data.
* `Description`: Description of the data that will be displayed in game.
* `Conditions formula`: The conditions to be able to equip or use the skill / item / weapon / armor
* `Target`: Target for applying associated effects.
  * `None`: No target selection.
  * `The user`: Select the user only.
  * `An enemy`: Only select one ennemy.
  * `An ally`: Only select one ally.
  * `All enemies`: Select all enemies.
  * `All allies`: Select all allies.
* `Target conditions formula`: The conditions to be able to use the skill / item / weapon / armor according to the target
* `Available`: Available kind of the data.
  * `Battle only`: The data can be used only in battle.
  * `Main menu only`: The data can be used only in main menu.
  * `Always`: The data can be used in battle and main menu.
  * `Never`: The data can never be used.
* `Sound (main menu)`: The sound to play when using it in the main menu.
* `User animation ID`: The animation ID to display on the user before attacking.
* `Target animation ID`: The animation ID to display on the target(s) when attacking.
* `Can be sold`: Indicate if the item can be sold in a shop
* `Battle message`: The message to display on the top bar when using a skill or item. `[item]` will display the item name, and `[skill]` will display the skill name.
* `Price`: Price of the data when it can be bought / sold in a shop menu.

There also are three more common properties that can be listed: `Costs`, `Effects`, and `Caracteristics`.

## Costs <a href="#costs" id="costs"></a>

![](../.gitbook/assets/battle-costs.png)

Choose the cost of using a skill. This is generally used for HP, MP, and TP statistic. A character will not be able to use a skill if he doesn't have enough for the use cost.

* `Apply cost on`: Select which data will be influenced after using the skill. It can be a `statistic`, a `currency`, or a `variable`.
  * `with value`: Select the value required for the selected data.

## Effects <a href="#effects" id="effects"></a>

![](../.gitbook/assets/effects.png)

Choose the effects done for the target(s) data.

* `Damages on`: Select which data will be damaged. It can be a `statistic`, a `currency`, or a `variable`.
  * `with formula`: Select the value damage for the selected data.
  * `Minimum`: Minimum value that can have final damages.
  * `Maximum`: Maximum value that can have final damages
  * `Element ID`: Element applied for these damages.
  * `Variance`: The variance damages in percent. This adds random on your damages. For example, if you choose 20% variance, your damages range would be : \[damage - (20 \* damage / 100) | damage + (20 \* damage / 100)]. If not checked, there is no variance (= 0).
  * `Critical`: The critical hit chance in percent. If not checked, there is no chance to do critical hit (= 0).
  * `Precision`: The precision hit in percent. If not checked, you have 100% chance to hit.
  * `Stock value in`: You can stock the damages value in a variable. This can for example be used for a next effect.
* `Status Add / Remove`: Add or remove a status to the target
* `Skill Add / Remove`: Add or remove a skill to the target (learn or forget)
* `Perform skill`: Execute another skill to the target
* `Call common reaction`: Call a common reaction
* `Special action`: Execute one of the following special actions:
  * `Apply weapon(s) effects and properties`: This will use all the effects of the currently equipped weapon. If the is no weapon equipped, this will apply the next effects following this one.
  * `Open skills choice`: Open the skills choice for battle command.
  * `Open items choice`: Open the items choice for battle command.
  * `Escape`: Escape from the battel.
  * `End turn`: End the team turn.
* `Script`: Execute a script
* `Temporarily change target`: You can temporarily change the target for this effect only. You have to return an array of battlers. Example: `[u.battler]` will be the user of the item/skill/weapon.

## Characteristics <a href="#characteristics" id="characteristics"></a>

Choose the characteristics added to the character when equipped.

![](../.gitbook/assets/battle-characteristic-buff.png)

*   `Buff increase / decrease`: Select which data will be influenced. This can be:

    * `Statistic value`: Select a statistic. If bar statistic, this will increase the max value.
    * `Element resistance`: Select an element to apply resistance on it.
    * `Status resistance`: Select a status to apply resistance on it.
    * `Experience gain`: Change experience gain after each battle.
    * `Currency gain`: Change currency gain after each battle.
    * `Skill cost`: Select a skill to apply skill cost change.

    After selecting the data influence, you can choose how this is influenced according to the base value:

    * `* / +`: Choose operation by multiplying by or adding a value.
    * `% / Fix`: Choose unit value.

![](../.gitbook/assets/battle-characteristic-character-specific.png)

* `Equip`: Choose to allow or forbid a weapon or armor to be equipped
* `Change equipment`: Choose to allow or forbid an equipment slot to be editable
* `Begin equipment`:  Choose a begin equipment (when the player is instancied)

![](../.gitbook/assets/battle-caracteristics-other.png)

* `Script`: Execute a script

## Classes <a href="#classes" id="classes"></a>

![](../.gitbook/assets/battle-classes.png)

Each character has a class. The class defines a lot of attributes that a character can have.

* **Experience**: Define experience progression according to level. Note that you can edit the experience column manually by `double clicking` on the cell.
  * `To next level`: The table indicates the number of experience to gain for going to the next level.
  * `Total`: The table indicates the total number of experience that should be accumulated for going to the next level.
  * `Initial level`: The initial level possible.
  * `Max level`: The maximum level possible.
  * `Base`: The number of experience to have at initial level.
  * `Inflation`: Inflation value changing experience progression according to base and level.
  * `Reset`: Reset to default values.
* **Statistics progression**: Change the statistics progression for level ups.
  * **Informations**:
    * `Statistic`: Select one of the system statistic.
    * `Maximum value`: The maximum possible value. This doesn't always corresponds to the final value because items could add bonus values.
  * **Fix**:
    * `Initial value`: The initial value at initial level.
    * `Final value`: The final value at max level.
    * `Slider progression`:
      * `Slow`: The experience increases slowly at the begining and increase faster at te end.
      * `Linear`: The experience increases constantly.
      * `Fast`: The experience increases fast at the begining and increase slowly at te end.
    * `Random variation`: The variance applied on the progression function. Note that this will always lead to the max value.
  * **Formula**: Use a formula to define the value. `u` corresponds to the character.
* **Characteristics**: Defines the class characteristics
* **Skills to learn**: Defines the list of skills that can be learned according to levels.
  * `Skill`: The corresponding skill to learn.
  * `Level`: The level for learning this skill.

## Heroes <a href="#heroes" id="heroes"></a>

![](../.gitbook/assets/heroes.png)

* `Class`: Select an existing class.
* `Description`: A description that will be displayed in the state menu ingame.
* `Faceset`: Select a faceset for battles.
* `Battler`: Select a battler for battles.

All the other properties inherits from the class properties. For `Experience`, the values by default are the class values. The `Set to class values` button updates the values to the class values. For `Statistics progression` list, you can add additional progressions. If the statistic already existed, the progression would be replaced. For `Skills to learn` list, you can add additional skills to learn. If the skill already existed, the level would be replaced.

## Monsters <a href="#monsters" id="monsters"></a>

![](../.gitbook/assets/battle-monsters.png)

Monsters are exactly like heroes but with extra information for battles:

* **Rewards**:

![](../.gitbook/assets/battle-monsters-rewards.png)

* `Experience`: Choose experience progression that your team can get at the end of a battle.
* `Currencies`: Choose currencies progression that your team can get at the end of a battle.
*   `Loots`: The loots that your team can get at the end of a battle.

    * `Number`: The number of items to loot.
    * `Probability`: The probability to loot.
    * `Level between`: Choose range level of loot availability.
    * `Loot`: Select `Item`, `Weapon`, and `Armor`.


* **Actions**:

You can manage your monster's AI here. You can specify monster actions with these following options:

![](../.gitbook/assets/monster-action.png)

* `Priority`: The priority of the action. You can see `Probability` below that will give you the percent chance of the actions according to all the other actions priorities. Warning: Il you put a priority as a variable a `?` will be displayed.
* `Target`:
  * `Random`: Will attack on random target without any AI.
  * `Weak enemies`: Will attack targets with lower HPs. Warning: do not remove or change hp abbreviation in common statistics to have this working.
* **Action**:
  * `Use skill ID`: The monster will use the selected skill.
  * `Use item ID`: The monster will use the selected item.
  * `Number max`: The number max of item that can be used by the monster. If < 0, will be infinite.
  * `Do nothing`: The monster will do nothing.
* **Conditions**:
  * `Turn value`: This action can be done according to the current value of turns in the battle.
  * `Statistic ID`: This action can be done according to the specified statistic percentage. Note: this should be only bars (with max value).
  * `Variable`: This action can be done according to the current value of a variable.
  * `Is under effect of status ID`: Not available yet.
  * `Script`: This action can be done according to the script return.

## Troops <a href="#troops" id="troops"></a>

![](../.gitbook/assets/troops.png)

Troops correspond to a monsters group and some states with reactions.

* **Test button**: You can test a troop battle at any moment with the test button. It will open a small window when you can choose a team fighting this troop. When it's done, just press ok and it will open a game battle with the selected troop.

![](../.gitbook/assets/troop-test.png)

* **Monsters list**:
  * `Monster`: The monster in the group.
  * `Level`: The level of the monster.
* **Reactions:** a list of reactions to trigger in this battle troop
  * `Name`: The reaction name (only to help for ordering everything)
  * `Conditions`: The condition(s) to validate to trigger the reaction:

![](../.gitbook/assets/troops-reactions.png)

*
  * `Number of turns + x` : The turn number. The first turn is turn 1. The (`+`) turn is the fix base turn, and the (`x`) is the number of time it's trigerred. `1 + 2 x` will for example be triggered in turn 1, 3, 5... etc.
  *   `The heroes/monsters all players/none of the players/at least one player/the player with instance ID`:

      * `Are under effect of status ID`: Check if the status is applied
      * `Have the statistic ID`: Compare a statistic value


* `Frequency`: The frequency of trigerring
  * `One time`: Only triggered one time in the beginning of the first turn
  * `Each turn (begin)`: Triggered in the beggining of each turn
  * `Each turn (end)`: Triggered in the end of each turn
  * `Always`: Triggered in each frames

## Status <a href="#status" id="status"></a>

![](../.gitbook/assets/status.png)

Status can be applied after using particular skills or items. This can be KO, poisonned, paralized, etc.

* `Animation ID`: Select an animation to display with a loop when the player is affected by this status. Since you can't display more than one animation on a player if there is several status, the `priority` will decide which one to display.
* `Restrictions`: You can add restrictions for the player when it is affected by the status. It can be:
  * `Can't do anything`: The player will pass their turn everytime
  * `Can't use skills`: The player won't be able to open skills menu
  * `Can't use items`: The player won't be able to open items menu
  * `Can't escape`: The player won't be able to escape
  * `Attack random target`: The player will use a random attack to attack a random target (ally or enemy)
  * `Attack random ally`: The player will use a random attack to attack a random ally
  * `Attack random enemy`: The player will use a random attack to attack a random enemy
* `Priority`: Defines which `Animation ID` and `Battler position` to display. If you have several status, the one with higher priority will be displayed.
* `Battler position`: The column to display in Battler picture when the player is affected by the status
* **Release conditions**: Defines all the status release conditions
  * `Release at the end of battle`: The status will disappear after the end of a battle
  * `Release with X% chance after being attacked`: The status will disappear with X% chance after being attacked (receiving positive damages)
  * `Release at the start of turn`: The status will disappear at the start of a turn according to a list of conditions depending on a chance according to the turn number.
* **Messages**: Defines messages to display according to the status situation
  * `Ally affected`
  * `Enemy affected`
  * `Status healed`
  * `Status still affected`
* **Effects**: The effects to apply at the beginning of a turn if the player is still affected by the status
* **Characteristics**: The characteristics (buffs etc) to apply when the player is affected by the status

## Animations <a href="#animations" id="animations"></a>

![](../.gitbook/assets/battle-animations.png)

Animations are used for: weapons, skills, items, and event command display an animation. You can customize these 2D animations with several different options.

* `Picture`: The texture used for the entire animation.
* `Position`: Choose the origin position. You have an indicator of this position with the battler example drawn in the panel.
* **Frames**: List of different frames of the animation.
  * **Graphics**: You can add elements in the panel by left clicking:

![](../.gitbook/assets/widget-animation.png)

You can right-click and click on `Edit...` to edit properties of an element:

![](../.gitbook/assets/widget-animation-element-properties.png)

* `Index`: The index of the element. An element is always drawn on top of other elements that have lower index.
* `X`: The x position center of the element.
* `Y`: The y position center of the element.
* `Zoom`: The zoom % the element.
* `Angle`: The angle ° of the element.
* `Flip vertically`: If checked, the element will be flipped vertically.
*   `Opacity`: The opcaity % of the element.

    Before left clicking, you can choose the texture thanks to this selector:

![](../.gitbook/assets/widget-animation-texture.png)

*   **Options**:

    * `Change battler`: Change the battler to display in the panel.
    * `Copy frames...`: Copy frames with the following options.



    ![Screenshot](../.gitbook/assets/animation-copy-frames.png)



    * **Frames to copy**: Select all the frames to copy.
    * `Paste from frame`: Paste from this frame.
    * `Clear frames...`: Clear frames with the following options.



    ![Screenshot](../.gitbook/assets/animation-clear-frames.png)



    * `Create transition...`: Create a transition on several frames with the following options.



    ![Screenshot](../.gitbook/assets/animation-create-transition.png)



    * **Frames**: The frames begin and end transition.
    * **Elements index**: The elements index to apply transition.
    * `X`, `Y`, `Zoom`, `Angle`, `Opacity`: The optional values at the end of the transition. You can use the progress slider to choose how fast is the transition.
    * `Apply texture`: Apply the selected texture to the selected element.
    * `Play hit`: Test the animation when hit.
    * `Play miss`: Test the animation when miss.
    * `Play crit`: Test the animation when critical.
    * `Rows`: The number of rows to split the texture animation. Default value is 5.
    * `Columns`: The number of columns to split the texture animation. Default value is 5.
* **Sound effects / Flashs**: You can add a list of effects (sound effects or flashs) here:

![Screenshot](../.gitbook/assets/animation-effects.png)

* **Effect**:
  * `Sound effect`: Select a sound to play at this frame.
  * `Flash`: _Not available yet._
* `Condition`: Select a condition for playing this sound or displaying this flash:
  * `None`: No condition.
  * `Hit`: When hitting an attack.
  * `Miss`: When missing an attack.
  * `Critical`: When doing a critical attack.
