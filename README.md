---
description: This is the initial page of RPG Paper Maker documentation.
---

# Початок роботи

![](.gitbook/assets/splash.png)

Вітаємо в документації RPG Paper Maker! Тут міститься все необхідне, щоб стати професіоналом з RPG Paper Maker!

## Встановлення <a id="installation"></a>

Перейдіть в [розділ Download](http://rpg-paper-maker.com/index.php/downloads#content) на офіційному сайті та завантажте пакет установки для вашої системи. 

### Windows <a id="windows"></a>

Запустіть `RPG Paper Maker installer.exe`. Це встановить програму на вашому комп'ютері, після чого запустіть `RPG Paper Maker.exe`. 

### Linux <a id="linux"></a>

Розпакуйте файл. Виконайте інструкції з файла `README` в кореневій директорії \(останньою інструкцією буде запуск `./run.sh`\). 

### MacOSX <a id="macosx"></a>

Розпакуйте файл. Запустіть `RPG Paper Maker.app.`

Програма встановлення дозволяє вибрати, яку версію завантажити. Рекомендується вибирати найновішу версію RPG Paper Maker. Програму буде запущено після завершення встановлення.



## Зміни теми <a id="change-theme"></a>

Доступні дві різних теми: `Темна` та `Біла`. 

Щоб змінити тему, використовуйте пункт меню`Налаштування > Загальні налаштування...`.

![](.gitbook/assets/themes-options.png)

## Створення нового проєкту <a id="create-a-new-project"></a>

Новий проєкт можна створити першою кнопкою на основній панелі інструментів:

![](.gitbook/assets/new-project.png)

Крім того, можна використовувати `CTRL+N` або пункт меню `Файл > Новий проєкт...`.

![](.gitbook/assets/new-project-window.png)

Тут можна вибрати, якою буде `Назва проєкту` , тобто назва вашої гри, яка буде використовуватися як її заголовок. Пункт  `Автоматично` дозволяє назвати директорію на диску на основі назви проєкту. Її також можна ввести вручну. Пункт `Місцезнаходження` вказує, де зберігатимуться директорії з проєктами. Якщо не міняти настройки, це буде новостворена директорія `RPG Paper Maker Games`. 

## Відкриття проєкту, створеного раніше <a id="open-an-existing-project"></a>

Можна відкрити існуючий проєкт, натиснувши на другу кнопку на основній панелі інструментів:

![](.gitbook/assets/open-project.png)

Також можна використовувати `CTRL+O` або `Файл > Відкрити проєкт > Огляд...`. 

Недавні проєкти також можна відкрити з початковом екрані \(а `Файл > Відкрити проєкт`\).

## Зміна загальних налаштувань гри <a id="change-general-game-settings"></a>

Багато налаштувань доступно у вікні `Керування системами.` Варто встановити деякі з цих налаштувань на початку роботи, особливо розмір екрана та розміри спрайтів. 

Натисніть тут на основній панелі інструментів та перейдіть до сторінки  `Система` :

![](.gitbook/assets/systems-manager.png)

* `Назва гри`: Вказує назву гри.
* `Базовий розмір графіки гри`: Вказує висоту та ширну гри в віконному режимі. Також можна перемкнутися поміж режимами Вікно та Повний екран.  
* `Antialiasing`: Якщо вибрати цю опцію, в грі буде використовуватися згладжування графіки.
* Властивості карти:
  * `Розмір клітини (в пікселях)`: це розмір \(в пікселях\) одної клітини вашох карти. Інша графіка мусить відповідати цьому значенню: спрайти більшого розміру мусять бути кратними основному розміру \(16, 32, 48 тощо\).
  * `Порції променя (в редакторі)`: Карта розбивається на декілька порцій \(по 16×16 квадратів\). Тут можна змінити кількість показуваних порцій.
  * `Порції променя (в грі)`: Те саме, але всередині гри.
  * `Ліміт висоти зіткнення для гір` \(в пікселях\): це налаштування визначає, наскільки високими мають бути гори для того, щоб вони блокували пересування гравця. Менші значення будуть вважатися сходинками, по яким можна пройти. 
  * `Ліміт куту зіткнення для гір` \(в градусах\): це значення визначає, наскільки пологим має бути схил, щоб гравець міг по ньому пройти. Якщо схил занадто крутий, по ньому неможливо піднятися або спуститися. 
* **Кадри**:

  * `Тривалість кадри карту`: Час в мілісекундах, за який перемальовується один кадр на карті. 

    \*деякі пункти нижче треба перевірити/розширити\*

    * Це впливає на: спрайти об'єктів, бойові анімації по-за межами битв тощо.
    * Це не вливає на: автотайли, битву \(?\). 

  * `Кадри анімації`: визначає кількість кадрів у одному циклі анімації. 
    * Це впливає на: спрайти об'єктів, тощо. 
    * Це не впливає на: анімацію бійців, автотайли. 
  * `Кадри бійців`: визначає кількість кадрів в одному циклі анімації бійця.
  * `Рядки бійців`: Кількість рядків, доступна в файлі графіки бійця.
  * `Кадри автотайлів`: визначає кількість кадрів у одному циклі анімованого автотайла.
  * `Тривалість кадра автотайла`: Час в мілісекундах на один кадр анімованого автотайла.

  
        \*Якщо ви збільшуєте кількість кадрів, вам необхідно буде збільшити ширину графічних файлів.   
        \*Якщо ви збільшуєте кількість рядків, вам необхідно буде збільшити висоту графічного файлу.   

* `Глобальні звуки`:
  * `Курсор`: Звук, який буде програватися при пересуванні курсору.
  * `Підтверждення`: Звук, який буде програватися при виборі пункту меню.
  * `Скасувати`: Звук, який буде програватися при скасуванні будь-чого.
  * `Неможливо`: Звук, який буде програватися, коли вибраний варіант неможливий.
* `Інші опції`:
  * `Стандартні налашування діалогового вікна`: Стандартне оформлення вікна, яке буде використовуватися для різних елементів вікон у графічному інтерфейсі. 
  * `Максимальна кількість записаних ігор`: Міняє максимальну кількість місць для запису гри, доступних гравцям/гравчиням.
  * `Ціна продажу речі`: Вказує, який процент оригінальної ціни можна отримати, продаючи річ. Це значення можна читати зі змінної.
  * `Опції введення імені`:  Встановлює літери, які можна використовувати для введення імен під час гри.

## Зміна мови <a id="update-keyboard-controls"></a>

Мову рушія можна змінити пунктом меню `Налаштування > Змінити мову...`:

![](.gitbook/assets/change-language.png)

## Оновлення керівних клавіш <a id="update-keyboard-controls"></a>

Можна змінити керівні клавіші редактора або гри, використовуючи пункт меню Керування &gt; Керівні клавіші або ou can change the engine and game keyboard controls in the keyboard manager by clicking on the main toolbar:

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

Select the corresponding system menus controls: `Action`, `Cancel`, `Up`, `Down`, `Left`, `Right`. You can add as many keys as you want.

When adding / editing a key:

* `Abbreviation`: Name used for JavaScript use \(for programmmers\).
* `Description`: Will be displayed in-game in the keyboard settings menu.
* `Shortcut`: Choose the keyboard key here. To set a new key press `Change...`. You can have more than one key per action. They are separated with a `|` symbol. You can also use the `+` symbol for key combinations. 
  * `Remove last`: Remove the last shortcut \(from the right\).
  * `Remove all`: Remove all shortcuts.

## Update general colors <a id="update-general-colors"></a>

These are required for other events that need to be given a color to use, such as tint screen and fonts. You may want to enter the base rainbow of colors to match your other graphics' palette. 

Go to the `Systems manager > System` to find the `Colors` box:

![](.gitbook/assets/colors.png)

## Update general font sizes and font names <a id="update-general-font-sizes-and-font-names"></a>

When writing text messages you are given a dropdown menu of choices. This menu is where you determine what choices are available for some of them.

Size is in pixels and is a single number. 

Font names is where you choose the font file and name. Remember to include them in /"project folder"/content/font. 

Go to the `Systems manager > System` to locate the `Font size` and `Font name` boxes:

![](.gitbook/assets/deepinscreenshot_select-area_20200323082522.png)

## Change game name <a id="change-game-name"></a>

Go to the `Systems manager > System` to find the `Game name` box:

![](.gitbook/assets/game-name.png)

This will affect the window title when you are launching the game.

## Change game screen resolution <a id="change-game-screen-resolution"></a>

Go to the `Systems manager > System`to view the `Game native resolution` box:

![](.gitbook/assets/game-resolution.png)

* `Width`: The native width of your game window.
* `Height`: The native height of your game window.
* `Window`: Choose a window mode.
* `Full screen`: choose full screen mode. Note that `Width` and `Height` have no effect with this option.

## Test your game <a id="test-your-game"></a>

You can test your project by clicking here on the main toolbar:

![](.gitbook/assets/play.png)

## Deploy your game <a id="deploy-your-game"></a>

If you want to publish your game \(share your game without any need for players to have RPG Paper Maker installed\) you go to `File > Export standalone...`.

![](.gitbook/assets/deploy.png)

* `Location`: The location of the standalone folder that you want to create. The name of this folder will be `yourGameName{OS}`.
* `Type of export`: Choose export options here.
  * `Deploy a desktop application`: Choose here to deploy your game as a desktop application \(choose the `OS` in options: Windows, Linux, or Mac\).
  * `Protect data`: Enable this if you want to encrypt the files so they can't be accessed outside of the game. \*\*May not work\*\*
  * `Deploy for web browser`: _\(not available yet\)_ Choose here to deploy your game as a web application. This will generate an `index.html` page and other files.
* `Version`: Choose you game version. Having 1 for `major` and 0 for `minor` will create a 1.0 version.

## Enable / Disable Updater <a id="enable-disable-updater"></a>

Go to`Help > Auto display updater` to enable or disable the updater that will check if a new version is available or not.

![](.gitbook/assets/autoupdater.png)

