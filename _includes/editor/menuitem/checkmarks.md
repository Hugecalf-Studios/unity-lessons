![Unity's Edit/Graphics Tier menu with checkmarks/ticks](unity-checkmarks.png)

The next feature of menu items is the ability to show a checkmark or a tick next to a menu item. This can be helpful, for example, to indicate if a certain setting is enabled or disabled.

In order to add checkmarks to menu items, we make use of the very same Validation Function from the previous section. As this method is called *before* Unity displays the menu to us, we can make use it to add or remove the checkmark to the menu item.

To add or remove the checkmark, we use the method `Menu.SetChecked`. The first parameter is the path to the menu item. Once again, this is why we store the menu path in the const field because we end up using it so much! The second argument is a `boolean` representing whether we have a checkmark or not.

![Custom menu with checkmark](checkmark.png)

We can achieve a very simply toggling action with the following code.

```
private static bool IsSettingEnabled;
		
[MenuItem(SettingMenuPath, priority = 1)]
private static void Setting() {
    IsSettingEnabled = !IsSettingEnabled;
}

[MenuItem(SettingMenuPath, true)]
private static bool SettingValidate() {
    Menu.SetChecked(SettingMenuPath, IsSettingEnabled);
    return true;
}
```

Once again, you can have some fun with this...
```
[MenuItem(SettingMenuPath, priority = 1)]
private static void Setting() {
}

[MenuItem(SettingMenuPath, true)]
private static bool SettingValidate() {
    Menu.SetChecked(SettingMenuPath, Random.Range(0, 2) == 0);
    return true;
}
```

### BONUS!
If you want the setting to persist between Unity editor sessions (which the above example will not) you can simply modify the above example to use EditorPrefs as shown below. The only modification changing IsSettingEnabled to a property which implements EditorPrefs.

```
private const string SettingPrefKey = "Setting";
private static bool IsSettingEnabled {
    get => EditorPrefs.GetBool(SettingPrefKey);
    set => EditorPrefs.SetBool(SettingPrefKey, value);
}

[MenuItem(SettingMenuPath, priority = 1)]
private static void Setting() {
    IsSettingEnabled = !IsSettingEnabled;
}

[MenuItem(SettingMenuPath, true)]
private static bool SettingValidate() {
    Menu.SetChecked(SettingMenuPath, IsSettingEnabled);
    return true;
}
```