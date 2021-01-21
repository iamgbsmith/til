# Record iOS Simulator

You can record video in an iOS simulator from the command line.

List all devices:
 
`xcrun simctl list devices`

```
$ xcrun simctl list devices
== Devices ==
-- iOS 13.4 --
    iPhone 8 (3BCDF13E-71C9-4EA6-966A-C44CB199BFBC) (Shutdown) 
    iPhone 8 Plus (79244BCD-D2FF-4214-B4D0-987892E3AF33) (Shutdown) 
    iPhone 11 (AC207EDA-3D10-4FFF-86E1-9DEC2FA11DCB) (Shutdown) 
    iPhone 11 Pro (2B14D31B-528A-40BD-A5CF-947072349F87) (Shutdown) 
    iPhone 11 Pro Max (86B90ADD-BE5C-4AB3-AB5C-49C7D41B83FF) (Shutdown) 
    iPhone SE (2nd generation) (11E6FB8F-1EA4-4D48-8AE9-452B9D5A1C1C) (Shutdown) 
    iPad Pro (9.7-inch) (090F2632-9936-47E4-BA51-A890DFBEF575) (Shutdown) 
    iPad (7th generation) (A5D28EF7-ADD3-4715-92B1-4072B747A8F6) (Shutdown) 
    iPad Pro (11-inch) (2nd generation) (3BB6E8CA-51E9-466F-86D4-B4D9819F355B) (Shutdown) 
    iPad Pro (12.9-inch) (4th generation) (F73A1051-74F4-4C62-AA50-05B5187F8CB2) (Shutdown) 
    iPad Air (3rd generation) (B242CC4E-2C34-414F-A03F-4C55B3AC171A) (Shutdown) 
-- tvOS 13.4 --
    Apple TV (D2936C08-B27F-439A-BE0B-01AB49A9E610) (Shutdown) 
    Apple TV 4K (17B161A0-E811-4238-9B87-48F4FCA5B1D0) (Shutdown) 
    Apple TV 4K (at 1080p) (6848CFC3-7E0F-469C-AF22-B3CB500CFF3A) (Shutdown) 
-- watchOS 6.2 --
    Apple Watch Series 4 - 40mm (F50CB6BD-8523-4291-B7D6-0DDC4647E905) (Shutdown) 
    Apple Watch Series 4 - 44mm (04F5B662-B9A1-4F2E-B63A-E3773758A18E) (Shutdown) 
    Apple Watch Series 5 - 40mm (CB7E8006-6FD9-4E8E-AA84-C9E203076087) (Shutdown) 
    Apple Watch Series 5 - 44mm (26929880-BEFB-4E23-849B-0EFA756409C7) (Shutdown) 
```
 
Start the simulator using the specific device id:
 
`xcrun simctl boot 86B90ADD-BE5C-4AB3-AB5C-49C7D41B83FF`
 
Launch the device:
 
`open /Applications/Xcode.app/Contents/Developer/Applications/Simulator.app/`

Once you have deployed your application to the simulator device you can record it from the command line:

`xcrun simctl io booted recordVideo myapp.mov`

 See [simctl: Control iOS Simulators from Command Line](https://medium.com/xcblog/simctl-control-ios-simulators-from-command-line-78b9006a20dc) for more details.