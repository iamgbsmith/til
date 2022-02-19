# Get An Ethereum Account Balance

__Category: Blockchain__

Account balances can be obtained from an Ethereum address using `web3.js`. 

The following code will query a Ganache server running __locally__  on port 7545 and convert the account balance for each address from the smallest unit of measure on the scale (wei), to ether.

```javascript
const Web3 = require('web3');

const web3 = new Web3(new Web3.providers.HttpProvider('http://localhost:7545'));

const getBalances() = async () => {
  if (web3) {
    // Get an array of addresses controlled by a node
    const addresses = await web3.eth.getAccounts();
    // Iterate the addresses and show the ETH balances
    for (const address of addresses) {
      const wei = await web3.eth.getBalance(address);
      if (wei) {
        // Convert balance from wei to ether
        var balance = web3.utils.fromWei(wei, 'ether');
        console.log(`Address ${address} has a balance of ${balance} ETH`)
      }
    }
  } 
}
```
