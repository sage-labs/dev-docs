# StackOS Documentation

![StackOS](https://cdn-images-1.medium.com/max/544/1*1U2bGZGGBTjS1qLPuHU_Cg@2x.png)

Documentation around different use cases for using [Hardhat](https://hardhat.org/)

## Initializing a Hardhat Project

1. `cd` to root of project folder where /sites and other top level directories live.
2. `mkdir hardhat`
3. `npm init --yes`
4. `npm install --save-dev hardhat`
5. `npx hardhat`
6. `npm install --save-dev @nomiclabs/hardhat-ethers ethers @nomiclabs/hardhat-waffle ethereum-waffle chai @openzeppelin/contracts`
7. Open up your hardhat.config.js file and code snippet below.
```
/**
 * @type import('hardhat/config').HardhatUserConfig
 */
module.exports = {
  solidity: {
    version: "0.8.9",
    settings: {
      optimizer: {
        enabled: true,
        runs: 10000
      }
    }
  },
};
```

## Deploying from WSL or Linux CLI

Ref: https://hardhat.org/tutorial/deploying-to-a-live-network.html

1. `npx hardhat run scripts/deploy.js optional[--network rinkeby]`

## Verifying contract from WSL or Linux CLI

Ref: https://hardhat.org/plugins/nomiclabs-hardhat-etherscan.html

1. `cd` into hardhat directory
2. `npm install --save-dev @nomiclabs/hardhat-etherscan`
3. Add this to top of hardhat.config.js or .ts file
    1. `import "@nomiclabs/hardhat-etherscan";`
4. Add your Etherscan API Key to hardhat.config.js or .ts
```
  etherscan: {
    apiKey: "YOUR_ETHERSCAN_API_KEY"
  }
```
5. Create a .js file with your constructor arguments
```
module.exports = [
  arg1,
  arg2,
  "Types don’t matter",
  [
    "Can use arrays",
    "And objects also",
  ],
  [1, 1],
];
```
6. Substitute the appropriate variables into this command
    1. `npx hardhat verify optional[--contract contracts/RND.sol:RND]  --network MY_NETWORK --constructor-args ARGUEMENTS_IN_JS_FILE DEPLOYED_CONTRACT_ADDRESS`
    2. Example: `npx hardhat verify --contract contracts/RND.sol:RND  --network rinkeby --constructor-args scripts/arguments.js 1x101101010101010111`
