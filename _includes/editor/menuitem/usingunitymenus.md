![Adding your own menu item to Unity's Edit menu](customiseeditmenu.png)

When providing your path to `MenuItem`, you don't have to use a custom path. You can hitch a ride off of one of Unity's existing menus. For example, you could add your own menu item to the File or Edit Menus. To do this, simply use the name of the menu you want to use in the path.

```
private const string MenuBasePath = "Edit/";
private const string HelloWorldMenuPath = MenuBasePath + "Hello World!";

[MenuItem(HelloWorldMenuPath, priority = 1)]
private static void HelloWorld() {
    Debug.Log("Hello World!");
}
```