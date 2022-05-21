# What Is FIDO2

__Category: Security__

FIDO2 (Fast Identity Online) extends FIDO U2F to provide support for passwordless and multi-factor authentication.

It combines the capabilities of Web Authentication (WebAuthn) with Client-To-Authenticator-Protocol (CTAP) to bring FIDO2 to devices and browsers. 

FIDO2 enables authentication methods to be verified by a physical security key such as a [Yubikey](https://www.yubico.com/products/security-key/) or using built-in platform authenticators such a fingerprint readers and web cameras.

Implementations and supported platforms include:

* [Windows Hello](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/windows-hello) - provides support for authentication using fingerprints or facial recognition.
* [iOS 13.3 and above](https://support.apple.com/en-us/HT210393#133) - adds support for NFC, USB, and Lightning FIDO2-compliant security keys in Safari.
* [Android](https://developers.google.com/identity/fido/android/native-apps) - native apps.
* [Browsers](https://caniuse.com/u2f) - includes Edge, Firefox, Chrome, Safari and Opera.

See [FIDO Alliance and FIDO2](https://fidoalliance.org/fido2/) for more details.
