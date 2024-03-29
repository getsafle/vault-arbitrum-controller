### 1.0.0 (2023-6-13)

##### Initial commit

- Implemented Keyring functionality to enable account generation, export keys and signing methods
- Added importWallet() to import account using privateKey.
- Added getBalance() to fetch the balance in native currency.
- Added sign() to sign a message or transaction and get signature along with v,r,s.
- Added method to sign a transaction

### 1.0.1 (2023-6-21)

- updated changelog

### 1.0.2 (2023-06-21)

- update import wallet to accept private key with or without '0x’ prefixed

### 1.0.3 (2023-6-26)

- Added cicd to push npm package

### 1.0.4 (2023-07-2)

- NPM and node version fixes

### 1.0.5 (2023-07-04)

- Added test suite for Arbitrum controller

### 1.0.6 (2023-07-04)

- Updated CI for test cases
- Added coverage report for the test cases
- Added nyc dependency for the coverage report
- Adding badges for readme.md

### 1.0.7 (2023-07-05)

- cleaned package structure

### 1.0.8  (2023-11-30)

- Updated gasFee() method for type 1 transactions and added its test.
- Changed license to MIT.