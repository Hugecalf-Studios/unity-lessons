![A simple customised menu with nesting](simple-nested.png)

To nest menu items, you can simply add a `/` in the menu path, and it will add another sub menu to you menu!
```c#
[MenuItem("My Custom Menu/Hello/Hello from a sub menu!")]
private static void HelloWorldNested() {
	Debug.Log("Hello SubMenu World!");
}
```
![A simple customised with deeper nesting](simple-nested-many-times.png)

I don't know what the limit is, but I haven't found it yet!

```c#
[MenuItem("My Custom Menu/Hello/From/A/Sub/Menu/Hello World!")]
private static void HelloWorldNestedManyLevels() {
	Debug.Log("Hello from deep down!");
}
```