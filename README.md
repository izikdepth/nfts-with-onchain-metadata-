NFTs with onchain metadata deployed on mumbai, polygon testnet -- ALCHEMY LESSON

clone repo ``git clone https://github.com/izikdepth/nfts-with-onchain-metadata-.git``

make a directory and call it "chainbattles" with command ``mkdir ChainBattles``

if you encounter any errors, ask consult your favourite AI tool such as chatgpt, phind.com 

install hardhat ``yarn add hardhat``
initialize hardhat  ``npx hardhat init``
select option:
    "Create a JavaScript project" and agree to all t&c.

check if hardhat is running properly ``npx hardhat test``

install openzeppelin to your project cos we'll be using it here ``yarn add @openzeppelin/contracts``

create a .env file with command ``npm install dotenv`` then ``touch .env`` , then enter the following in your .env file
``TESTNET_RPC="register an account on alchemy.com and create a new app, call it anything and select polygon then testnet(mumbai)  ,then click view keys and copy your rpc url then paste it here"
PRIVATE_KEY="click on the 3 dots in your metamask then click on view private key"
POLYGONSCAN_API_KEY="create an account on https://polygonscan.com/ , create a new api and copy , paste it here"
``

compile with ``npx hardhat compile``
deploy to mumbai ``npx hardhat run scripts/deploy.js --network mumbai``
verify your smart contract with hardhat directly from vscode ``npx hardhat verify --network mumbai YOUR_SMARTCONTRACT_ADDRESS`` note that you may encounter some errors, copy the error on the terminal with ctrl + insert on windows(vscode) or ctrl+c on  system's terminal. if it shows json errors, try again in an hour or so it'll work.

go to https://mumbai.polygonscan.com/ and paste your sc address to view it , after your nft contract is verified you can mint directly from https://mumbai.polygonscan.com/ or use a mint script.
view your nft here : https://testnets.opensea.io/


NOTES:  you can deploy this on any evm compatible chain, but keep in mind that it might be an expensive task especially on it because  of dataspace. 

few commands that may be useful for trouble shooting:

``npx hardhat compile
Error HH801: Plugin @nomicfoundation/hardhat-toolbox requires the following dependencies to be installed: @nomicfoundation/hardhat-network-helpers, @nomicfoundation/hardhat-chai-matchers, @nomicfoundation/hardhat-ethers, @nomicfoundation/hardhat-verify, @types/chai, @types/mocha, @typechain/ethers-v6, @typechain/hardhat, chai, hardhat-gas-reporter, solidity-coverage, ts-node, typechain, typescript.
Please run: npm install --save-dev "@nomicfoundation/hardhat-network-helpers@^1.0.0" "@nomicfoundation/hardhat-chai-matchers@^2.0.0" "@nomicfoundation/hardhat-ethers@^3.0.0" "@nomicfoundation/hardhat-verify@^1.0.0" "@types/chai@^4.2.0" "@types/mocha@>=9.1.0" "@typechain/ethers-v6@^0.4.0" "@typechain/hardhat@^8.0.0" "chai@^4.2.0" "hardhat-gas-reporter@^1.0.8" "solidity-coverage@^0.8.1" "ts-node@>=8.0.0" "typechain@^8.2.0" "typescript@>=4.5.0"

For more info go to https://hardhat.org/HH801 or run Hardhat with --show-stack-traces`` 

Install those dependencies with ``npm install --save-dev "@nomicfoundation/hardhat-network-helpers@^1.0.0" "@nomicfoundation/hardhat-chai-matchers@^2.0.0" "@nomicfoundation/hardhat-ethers@^3.0.0" "@nomicfoundation/hardhat-verify@^1.0.0" "@types/chai@^4.2.0" "@types/mocha@>=9.1.0" "@typechain/ethers-v6@^0.4.0" "@typechain/hardhat@^8.0.0" "chai@^4.2.0" "hardhat-gas-reporter@^1.0.8" "solidity-coverage@^0.8.1" "ts-node@>=8.0.0" "typechain@^8.2.0" "typescript@>=4.5.0"
``

```
ERROR
The error message indicates that the @nomiclabs/hardhat-waffle module is missing from your project. This could be because it is not installed or not correctly required in your hardhat.config.js file.```

fix by installing with ```npm install --save-dev @nomiclabs/hardhat-waffle ethereum-waffle
```

ps: always consult your ai buddy or ask questions on https://ethereum.stackexchange.com/
# nfts-with-onchain-metadata-
