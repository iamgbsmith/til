# Configure GPU Acceleration In New Teams

__Category: Office__

The new version of teams based on React does not provide a UI configuration item to disable or enable GPU acceleration. In some situations, you might need to disable GPU acceleration if Teams is freezing or the video and sound is choppy.

Perform the following to disable GPU acceleration.

1. Close the Teams application by right clicking on the icon in the taskbar overflow area and selecting "Quit".
2. Open `desktop-config.json` in C:\Users\\{username}\AppData\Roaming\Microsoft\Teams\ using a text editor.
3. Find the entry for `disableGpu` and change the value to `true`
4. Save the `desktop-config.json` file.
5. Restart Teams.

Change the above value to `false` and restart Teams to re-enable GPU acceleration.
