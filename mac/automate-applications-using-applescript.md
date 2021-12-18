# Automate Applications Using AppleScript

__Category: Mac__

AppleScript is a language that can be used control Mac applications.

For example, the following script will launch Safari then navigate to a URL:

```shell
-- Obligatory script comment here
tell application "System Events" to tell process "Safari"
    set frontmost to true
    tell menu bar item "File" of menu bar 1
        click
        click menu item "New Tab" of menu 1
        open location "https://finance.yahoo.com"
        activate
    end tell
end tell
```

Execute the `oascript` command to run a script:

```shell
osascript /path/to/LaunchSafari.scpt
```
