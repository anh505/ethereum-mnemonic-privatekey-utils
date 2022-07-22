ethereum-mnemonic-privatekey-utils
===

A Helper For Generating Private Key With Mnemonic Words.

Useful When Develop With Ethereum, Generate Private Key For `eth`/`geth` Private Chain Client.

## Installation

Download Source Code:

`git clone https://github.com/justinchou/ethereum-mnemonic-privatekey-utils.git`

Enter Source Folder And Then Install Dependencies:

`npm install` OR `yarn install`

## Quick Start

```js
const pkutils = require('./index');

// close debug mode
pkutils.debug = false;

const mnemonic = '12 seed phrases';
const password = 'this is a totally long password';
const privateKey = '0x10ee83e438abf443cee0b3f808dd339308823fa3ef84f3c932b1a67e968f039a';
const address = '0x8ab7edcd19d92170528cd5d8a7d25dc6ffb75c39';
const checkBalance = 'https://debank.com/profile/0x8ab7edcd19d92170528cd5d8a7d25dc6ffb75c39';

console.log('mnemonic:        %s', mnemonic);
console.log('password:        %s', password);
console.log('privateKey:        %s', privateKey);
console.log('address:        %s', address);
console.log('checkBalance:        %s', checkBalance);

const privateKeyGen = pkutils.getPrivateKeyFromMnemonic(mnemonic);
console.log('private key:     %s', privateKeyGen);
console.log('compare private key:     %s', privateKey);

const keystore = pkutils.getKeystoreFromPrivateKey(privateKeyGen, password);
console.log('key store:       %j', keystore);

const privateKeyParsed = pkutils.getPrivateKeyFromKeystore(keystore, password);
console.log('private key:     %s', privateKeyParsed);
console.log('compare private key:     %s', privateKey);

const account = keystore.address;
console.log('account address: %s', account);
console.log('compare with address: %s', address);

```
