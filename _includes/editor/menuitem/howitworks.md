When Unity recompiles your scripts, it searches through all the scripts in your project and looks for methods which are decorated with the `MenuItem` attribute. When it finds one, it creates a new menu item with the given path and executes the code in the method when you click that menu item.