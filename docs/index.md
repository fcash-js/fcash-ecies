# ECIES
Fcash implements [Elliptic Curve Integrated Encryption Scheme (ECIES)](http://en.wikipedia.org/wiki/Integrated_Encryption_Scheme), which is a public key encryption system that performs bulk encryption on data using a symmetric cipher and a random key.

For more information refer to the [fcash-ecies](https://github.com/fcash-project/fcash-ecies) github repo.

## Installation
ECIES is implemented as a separate module and you must add it to your dependencies:

For node projects:

```bash
npm install fcash-ecies --save
```

For client-side projects:

```bash
bower install fcash-ecies --save
```

## Example

```javascript
var fcore = require('fcash-lib');
var ECIES = require('fcash-ecies');

var alicePrivateKey = new fcore.PrivateKey();
var bobPrivateKey = new fcore.PrivateKey();

var data = new Buffer('The is a raw data example');

// Encrypt data
var cypher1 = ECIES.privateKey(alicePrivateKey).publicKey(bobPrivateKey.publicKey);
var encrypted = cypher1.encrypt(data);

// Decrypt data
var cypher2 = ECIES.privateKey(bobPrivateKey).publicKey(alicePrivateKey.publicKey);
var decrypted = cypher2.decrypt(encrypted);

assert(data.toString(), decrypted.toString());
```
