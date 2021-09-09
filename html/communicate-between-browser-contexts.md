# Communicate Between Browser Contexts

__Category: HTML__

The Broadcast Channel API allows basic communication between browser contexts on the same machine such as windows, tabs, frames, or iFrames and workers on the same origin using a `BroadcastChannel` object. It provides an event bus capability for browser applications.

### Why would use the broadcast channel API?

Situations where this feature is useful: 

* Storing session related information
* Sharing state across browser contexts
* Subscribing to specific channels for events you are interested in
* Detecting actions in another tab (for example, when a user logs out)

After creating a `BroadcastChannel` object you can receive any messages that are posted to it using a data format of your chosing. 

It is not necessary to maintain a reference to the frames or workers you wish to communicate with. Subscribing to a specific channel by constructing a BroadcastChannel with the same name will facilitate bi-directional communication across different browser contexts on the same origin.

### Usage Examples

Connect to a channel:

```javascript
const bc = new BroadcastChannel('my_broadcast_channel');
```

Send a message to a channel:

```javascript
bc.postMessage('Some message which will go to channel subscribers');
```

Process an incoming message:

```javascript
bc.onmessage = function(ev) { 
  console.log(ev); 
}
```

Disconnect from a channel:

```javascript
bc.close();
```

### Limitations

If the hosts, ports, and schemes are different the broadcast channel API will not work.

Different hosts will not allow communication across contexts:

https://alligator.io

https://www.alligator.io

Different ports will not allow communication across contexts:

https://alligator.io

https://alligator.io:8080

Different schemes will not allow communication across contexts. Note that this is effectively similar to using different ports since HTTP and HTTPS are typically served on port 80 port 443 respectively.

http://alligator.io

https://alligator.io

See [Broadcast Channel API](https://developer.mozilla.org/en-US/docs/Web/API/Broadcast_Channel_API) for more details.
