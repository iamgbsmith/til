# Get Current Ethereum Gas Price

__Category: Blockchain__

Transaction fees (also known as gas fees) in Ethereum are measured in Gwei. Gas prices can determined from the last few blocks median gas price.

The following code will query a Ganache server running __locally__ on port 7545 to obtain the current average gas price.

```javascript
const Web3 = require('web3');

const web3 = new Web3(new Web3.providers.HttpProvider('http://localhost:7545'));

const getGasPrice = async () => {
  if (web3) {
    web3.eth.getGasPrice(function(error: any, wei: number) {
      if (!error) {
        var gasPriceInGwei = web3.utils.fromWei(wei, 'gwei');
        console.log(`Current gas price is ${gasPriceInGwei} gwei`);
      }
    });
  }
}
```

You can obtain gas prices for Ethereum Mainnet by connecting to an API provider such as [Infura](https://infura.io) from Consensys.

__Note:__ 1,000,000,000 Gwei is equal to 1 Ether.
