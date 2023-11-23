# New Teams Freezes And Locks Up

__Category: Office__

In some situations, the new version of Teams may become unresponsive with frozen video or distorted sound. If this occurs, you should delete the contents of the Teams cache.

Perform the following to delete the contents of the Teams cache on Windows.

1. Close the Teams application by right-clicking on the Teams icon in the taskbar overflow area and selecting "Quit".
2. Navigate to C:\Users\\{username}\AppData\Roaming\Microsoft\Teams\Cache using Explorer.
3. Delete the `Cache_Data` directory.
5. Restart Teams.

__Note:__ Following this approach as opposed to completely deleting the contents of the Teams directory (as other suggestions make) will ensure your custom backgrounds and configuration settings are preserved.
