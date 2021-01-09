# Run Unsigned Applications

__Category: Mac__

Security in macOS Catalina has tightened controls on whether applications downloaded from the internet can be run. If you try to open an appliction that isn’t registered with Apple by an identified developer you will get a warning dialog. There are two ways around this.

__Caveat:__ Ensure that you have verified the authenticity of the application you are about to run before proceeding. __Do not run any application that looks untrustworthy.__

### Remove the quarantine flag

Run the following command to remove the quarantine flag specifying the path to a binary or directory:

```
sudo xattr -d com.apple.quarantine /path/to/application
```

### Grant an exception in the security preferences

From the Apple menu  > System Preferences, click Security & Privacy, then click General. For the application you have tried to launch, grant an exception for a blocked appliction by clicking the Open Anyway button. 

This button is available for about an hour after you try to open the app.

See [Open a Mac app from an unidentified developer](https://support.apple.com/en-nz/guide/mac-help/mh40616/mac) for more details.
