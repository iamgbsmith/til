# What Is Web3js

__Category: Blockchain__

`web3.js` is a JavaScript API for interacting with the Ethereum blockchain via local or remote nodes. Connectivity is over HTTP, IPC, or WebSocket.

Add web3.js to your project:

```shell
yarn add web3
```

Most calls to web3.js are asynchronous with responses being handled using a callback or async/await block.

For example:

```javascript
// Get an array of addresses controlled by a node
const addresses = await web3.eth.getAccounts();
```

Because the Etheruem blockchain has different levels of finality, web3.js can return multiple stages of an action using a "PromiEvent". This allows smart contracts or functions, for example, the method `web3.eth.sendTransaction`, to subscribe to confirmations, errors, and the transaction hash.

See [web3.js - Ethereum JavaScript API](https://web3js.readthedocs.io/) for more details.
