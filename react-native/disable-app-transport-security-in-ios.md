# Disable App Transport Security In iOS

__Category: React Native__

_This TIL also applies to applications developed using Swift._

For security reasons, Apple iOS applications use App Transport Security (ATS) which requires the use of HTTPS instead of HTTP for calls to remote endpoints. By default, calls over HTTP will fail. 

When developing apps, you may need to enable HTTP transport in iOS when working with locally deployed REST endpoints.

### Disable ATS for calls to all endpoints

For developing against endpoints which are accessed using plain HTTP, an entry must be added to `Info.plist` as follows:

```xml
<key>NSAppTransportSecurity</key>
<dict>
  <key>NSAllowsArbitraryLoads</key>
  <true/>
</dict>
```

### Disable ATS for endpoints at a specific domain

It is possible to disable ATS for a specific domain (in this example `yourdomain.com`) as follows:

```xml
<key>NSAppTransportSecurity</key>
<dict>
  <key>NSAllowsArbitraryLoads</key>
  <false/>
  <key>NSExceptionDomains</key>
  <dict>
    <key>yourdomain.com</key>
    <dict>
      <key>NSIncludesSubdomains</key>
      <true/>
      <key>NSExceptionAllowsInsecureHTTPLoads</key>
      <true/>
    </dict>
  </dict>
</dict>
```

__Do not disable ATS for production deployments. For security reasons, you must ensure that all calls are made over HTTPS. Disabling ATS may result in your application being rejected during the App Store approval process.__

See [NSAllowsArbitraryLoads](https://developer.apple.com/documentation/bundleresources/information_property_list/nsapptransportsecurity/nsallowsarbitraryloads) for more details.