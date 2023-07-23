# Hide MacOS Storyboard Window On Start

__Category: Swift__

If you create a storyboard for application which is an agent you may need to hide the initial window when the application launches.

To hide the main window, open the `Main` storyboard for the application.

From the component tree, expand "Window Controller Scene" and select "Window Controller".

In the Attributes Inspector, deselect the checkbox "Is Initial Controller".
