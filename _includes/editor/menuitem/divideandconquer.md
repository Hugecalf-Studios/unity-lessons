![A simple customised menu with simple ordering and a divider](ordered-with-divider.png)

It is possible to add a dividing line, as shown above, by having a gap of more than 10 in their priorities. Note that Item3 has a priority of 3 and Item4 has a priority of 14. This is a gap of 11, which fufills the requirement of more than 10.
```
[MenuItem(Item3MenuPath, priority = 3)]
private static void Item3() {
    Debug.Log("Item 3!");
}

[MenuItem(Item4MenuPath, priority = 14)]
private static void Item4() {
    Debug.Log("Item 4!");
}
```