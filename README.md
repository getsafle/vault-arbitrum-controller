# Vault-arbitrum-controller <code><a href="https://www.docker.com/" target="_blank"><img height="50" src="https://assets.coingecko.com/coins/images/16547/small/photo_2023-03-29_21.47.00.jpeg?1680097630"></a></code>

<img alt="Static Badge" src="https://img.shields.io/badge/version-v1.0.6-blue">  <img alt="Static Badge" src="https://img.shields.io/badge/nvm-v6.0.6-red">  <img alt="Static Badge" src="https://img.shields.io/badge/License-MIT-green">   [![Discussions][discussions-badge]][discussions-link]
 <img alt="Static Badge" src="https://img.shields.io/badge/Arbitrum_controller-documentation-purple">   

A module written in javascript for managing various keyrings of Arbitrum accounts, encrypting them, and using them.

- [Installation](#installation)
- [Initialize the Arbitrum Controller class](#initialize-the-arbitrum-controller-class)
- [Methods](#methods)
  - [Generate Keyring with 1 account and encrypt](#generate-keyring-with-1-account-and-encrypt)
  - [Restore a keyring with the first account using a mnemonic](#restore-a-keyring-with-the-first-account-using-a-mnemonic)
  - [Add a new account to the keyring object](#add-a-new-account-to-the-keyring-object)
  - [Export the private key of an address present in the keyring](#export-the-private-key-of-an-address-present-in-the-keyring)
  - [Sign a transaction](#sign-a-transaction)
  - [Sign a message](#sign-a-message)
  - [Get balance](#get-balance)


## Installation
```
npm install --save @getsafle/vault-arbitrum-controller
```
## Initialize the Arbitrum Controller class

```
const { KeyringController, getBalance } = require('@getsafle/vault-arbitrum-controller');

const arbitrumController = new KeyringController({
  encryptor: {
    // An optional object for defining encryption schemes:
    // Defaults to Browser-native SubtleCrypto.
    encrypt(password, object) {
      return new Promise('encrypted!');
    },
    decrypt(password, encryptedString) {
      return new Promise({ foo: 'bar' });
    },
  },
});
```

## Methods

### Generate Keyring with 1 account and encrypt

```
const keyringState = await arbitrumController.createNewVaultAndKeychain(password);
```

### Restore a keyring with the first account using a mnemonic

```
const keyringState = await arbitrumController.createNewVaultAndRestore(password, mnemonic);
```

### Add a new account to the keyring object

```
const keyringState = await arbitrumController.addNewAccount(keyringObject);
```

### Export the private key of an address present in the keyring

```
const privateKey = await arbitrumController.exportAccount(address);
```

### Sign a transaction

```
const signedTx = await arbitrumController.signTransaction(arbitrumTx, _fromAddress);
```

### Sign a message

```
const signedMsg = await arbitrumController.signMessage(msgParams);
```

### Sign a message

```
const signedObj = await arbitrumController.sign(msgParams, pvtKey, web3Obj);
```

### Sign Typed Data (EIP-712)

```
const signedData = await arbitrumController.signTypedMessage(msgParams);
```

### Get balance

```
const balance = await getBalance(address, web3);
```
[discussions-badge]: https://img.shields.io/badge/Code_Quality-passing-rgba
[discussions-link]: https://github.com/getsafle/vault-arbitrum-controller/actions
