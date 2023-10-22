# Reset User Defaults For An Application

__Category: Mac__

__Note: You must know the name of the bundle identifier for the application before performing this task. Proceed  with caution.__

The `UserDefaults` class provides a programmatic interface for interacting with the defaults system. Defaults are stored on a per-user basis for each application on macOS.

There may be situations where you need to delete these settings if developing applications on macOS.

Navigate to `~/Library/Preferences/`

To remove the `plist` file in the above directory:

```shell
rm com.yourcompany.yourapp.plist
```

Since User Defaults are cached, you will need to kill the preferences service (which will restart automatically):

```shell
killall cfprefsd
```

When the application is restarted, it will create a new UserDefaults plist file with default configuration settings.
