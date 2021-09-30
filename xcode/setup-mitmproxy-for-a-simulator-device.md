# Setup MITMProxy For A Simulator Device

__Category: Xcode__

This TIL assumes you need to intercept HTTPS traffic running on iOS Simulator using [mitmproxy](https://mitmproxy.org/)
 
You will need to install the MITM Proxy Certificate Authority on each simulator device that you want to sniff HTTPS traffic on.
 
1. Launch Safari on the simulator and go to http://mitm.it
 
2. Install the certificate into the simulator device by selecting the link "Get mitmproxy-ca-cert.cer" for iOS.
 
3. On the simulator, go to Settings -> General -> Device Management.
 
4. Select the option "mitmproxy" as the Downloaded Profile, then continue to click "Install" until you see the "Profile Installed" dialog.
 
5. Click "Done".
 
6. Next, enable the SSL certificate by going to Settings -> General -> About -> Certificate Trust Settings.
 
7. In the list, enable full trust for the "mitmproxy" root certificate.
 
You should then be able to open any site that uses HTTPS being proxied through mitmproxy and inspect traffic on the proxy host.
