# View Browser Network Requests

__Category: HTML__

Network requests sent by a browser can be analysed using developer tools. This TIL assumes the use of Firefox.

Using Firefix, open Tools -> Web Developer -> Network. 

When you start interacting with a website you will see information on network requests being logged. In the status bar for network, the number of requests, kilobytes transferred and duration is shown.

You can filter on requests for a domain by using the `domain:` prefix, for example `domain:google.com`. 

To refine this for certain types of request in a domain enter: `method:GET domain:google.com` in the input field.

See [Network request list in Firefox](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor/request_list#Filtering_by_properties) for more details.
