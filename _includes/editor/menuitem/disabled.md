![Unity's Assets menu with disabled/greyed out items](unity-disabled.png)

It is very simple to disable the use of a certain menu item, yet the Unity docs are not clear. To disable a menu item, we must make use of what Unity called a Validation Function. A Validation Function is a `static bool` method which gets executed *before* Unity displays your custom menu to you. To make a disabled menu item, simply return false from this method. Conversely, returning true (or not having a Validation Function) will cause the menu item to be enabled.

The confusion comes in by assigning the Validation Function. To do so, you must use the exact same `MenuItem` attribute as before, with the exact same path given as the first parameter. This tells Unity which menu item to apply this Validation Function to. You must then give `true` as the second parameter, which tells Unity that this is a Validation Function.

![Custom menu with disabled item](disabled.png)

The above is made with the following code. Note how Item1 has a Validation Function assigned which returns false. This will mean Item1 is always disabled. Also note that Item2 has no Validation Function, which acts the same as a Validation Function which returns true, meaning Item2 is always enabled.
```c#
[MenuItem(Item1MenuPath, priority = 1)]
private static void Item1() {
    Debug.Log("Item 1!");
}

[MenuItem(Item1MenuPath, true)]
private static bool Item1Validate() {
    return false;
}

[MenuItem(Item2MenuPath, priority = 2)]
private static void Item2() {
    Debug.Log("Item 2!");
}
```

You can have some fun with this...
```c#
[MenuItem(RandomMenuPath, true)]
private static bool RandomItemValidate() {
    return Random.Range(0, 2) == 0;
}
```