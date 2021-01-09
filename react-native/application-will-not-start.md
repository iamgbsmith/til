# Application Will Not Start

__Category: React Native__

If your application won't start on iOS when launching after being deployed to the device, it might be due to an invalid or expired code signing certificate.

Log into Xcode and confirm that the signing certificate for the application is valid. For a production applicaton, ensure this is managed on a yearly basis through the Apple Developer Program prior to the expiry of the subscription.
