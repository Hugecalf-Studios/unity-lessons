![Unity's File menu with keyboard shortcuts](unity-shortcuts.png)

The final topic is assigning keyboard shortcuts to menu items. This is, once again, a simple thing to do, and can save you lots of time for commonly used menu items.

To add a keyboard shortcut to a menu item, you need to suffix a string which specifies the shortcut to the end of the menu item path. You must have a space between your menu item and the shortcut specifier.
```c#
private const string HelloWorldMenuPath = CustomMenuBasePath + "Hello World! <SHORTCUT_SPECIFIER>";
```

In order to make it as unclear as possible, Unity introduced some some symbols which represent the modifier keys Control/Command, Shift and Alt keys.

|Symbol|Keyboard Key|
|-|-|
|%|Ctrl/Command|
|#|Shift|
|&|Alt|
|_|None|

Combining these modifier keys with any the following key codes gives you a load of options to create keyboard shortcuts.

|Special Key|Keyboard Key|
|-|-|
|A-Z|Letters A-Z|
|LEFT, RIGHT, UP, DOWN|Arrow Keys|
|F1-F12|F1-F12|
|HOME|Home
|END|End
|PGUP|Page Up
|PGDN|Page Down

So, to assign the keyboard shortcut `Ctrl+Shft+I` to a menu item, you simply suffix the string `%#I` to the end of your menu item path. You must have a space between the end of your menu item name and the keyboard shortcut for it to register.

![Custom menu with keyboard shortcuts](shortcuts.png)

```c#
private const string HelloWorldMenuPath = CustomMenuBasePath + "Hello World! %#I";
private const string GoodbyeWorldMenuPath = CustomMenuBasePath + "Goodbye World! _I";
```

> Note that to assign a shortcut of a single key on its own, without any modifiers, you must use the underscore `_` symbol.