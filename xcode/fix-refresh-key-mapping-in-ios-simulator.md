# Fix Refresh Key Mapping In iOS Simulator

__Category: Xcode__

Xcode 12.5 has taken the refresh (`command + R`) keyboard mapping for the iOS Simulator meaning it will start recording a video instead of reloading the app. Changing this mapping is useful for when developing React Native applications.

Re-map the refresh command to record videos using a new keyboard shortcut as follows:

Open System Preferences -> Keyboard

Select Shortcuts -> App Shortcuts

Click the `+` button

Select "Other"

Press `shift + command + g`

Enter `/Applications/Xcode.app/Contents/Developer/Applications/`

Select "Simulator App"

Specify a value of "Record Screen" for the Menu Title

Click in the keyboard shortcut box and press the desired key shortcut (for example, `option + command + v`)

Click "Add"
