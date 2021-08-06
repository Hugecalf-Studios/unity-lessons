The above examples are great and get us going quickly. However, there is an immediate improvement we can make to make our lives easier going forward: storing the menu path in a `static const` field. This is an improvement because when we get onto more complex menu customisation we will need to repeat this path in multiple places in our code, and we definitely don't want the same string hardcoded several times! The following example has the exact same functionality as the first, but it is better!
```c#
private const string HelloWorldMenuPath = "My Custom Menu/Hello World!";
```
```c#
[MenuItem(HelloWorldMenuPath)]
private static void HelloWorld() {
	Debug.Log("Hello World!");
}
```
Anticipating that we will most likely add more than one menu item going forward, we can take our `static const` approach one step further to avoid string repitition - saving you time and errors later on!
```c#
private const string CustomMenuBasePath = "My Custom Menu/";
private const string HelloWorldMenuPath = CustomMenuBasePath + "Hello World!";
private const string GoodbyeWorldMenuPath = CustomMenuBasePath + "Goodbye World!";
```
```c#
[MenuItem(HelloWorldMenuPath)]
private static void HelloWorld() {
	Debug.Log("Hello World!");
}

[MenuItem(GoodbyeWorldMenuPath)]
private static void GoodbyeWorld() {
	Debug.Log("Goodbye World!");
}
```