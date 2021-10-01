# Send Message From The Command Line

__Category: Mac__

You can send a message to an iPhone or Apple Watch from the command line with the following (where in this example, 555551234 is the phone number of the recipient):

```shell
osascript -e 'tell application "Messages" to send "This is a test message" to buddy "555551234"'
```
