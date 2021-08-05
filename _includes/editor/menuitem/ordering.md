Unless you want your menu items to randomly reorder themselves whenever they feel like it, you will definitely want to define an order in your `MenuItem` attributes. Without one, Unity will sometimes rearrange the menu items, which will wreak havok on your muscle menu that will develop when navigating the menu!

You specify the order by using the `priority` field. The menu items will be arranged with the smallest `priority` at the top and the largest `priority` at the bottom.

![A simple customised menu with simple ordering](ordered.png)

```
[MenuItem(Item1MenuPath, priority = 1)]
private static void Item1() {
    Debug.Log("Item 1!");
}
[MenuItem(Item2MenuPath, priority = 2)]
private static void Item2() {
    Debug.Log("Item 2!");
}
```