![A simple customised menu](./simple.png)

To add a new menu item to Unity's menu bar, you simply need a `static void` method in any class in your project and decorate it with the `MenuItem` attribute. The method must be `static`, but can be `private`. The following example will give you the new menu `My Custom Menu`, with the menu item `Hello World!`. Clicking on this will reveal the classic greating in the console.

```
[MenuItem("My Custom Menu/Hello World!")]
private static void HelloWorld() {
	Debug.Log("Hello World!");
}
```

> Note: Import the UnityEditor namespace to access MenuItem `using UnityEditor`

> Watch Out! The MenuItem Attribute is in the UnityEditor namespace! Make sure you use it in an editor-only script, or ensure this code is wrapped in `#if UNITY_EDITOR` and `#endif`. Otherwise, your builds will fail!