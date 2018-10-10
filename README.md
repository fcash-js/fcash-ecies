<img src="http://www.fcash.cash/css/images/module-ecies.png" alt="fcore ecies" height="35">
# ECIES for fcore

[![NPM Package](https://img.shields.io/npm/v/fcash-ecies.svg?style=flat-square)](https://www.npmjs.org/package/fcash-ecies)
[![Build Status](https://img.shields.io/travis/fcash-project/fcash-ecies.svg?branch=master&style=flat-square)](https://travis-ci.org/fcash-project/fcash-ecies)
[![Coverage Status](https://img.shields.io/coveralls/fcash-project/fcash-ecies.svg?style=flat-square)](https://coveralls.io/r/fcash-project/fcash-ecies)

A module for [fcore][fcore] that implements the [Elliptic Curve Integrated Encryption Scheme (ECIES)][ECIES]. Uses ECIES symmetric key negotiation from public keys to encrypt arbitrarily long data streams.

See [the main fcore repo](https://github.com/fcash-project/fcore) or the [fcore guide on ECIES](http://www.fcash.cash/guide/module/ecies/index.html) for more information.

Credit to [@ryanxcharles][ryan] for the original implementation.

## Getting started

ECIES will allow to securely encrypt and decrypt messages using ECDSA key pairs (bitcoin cryptography).

```javascript
var alice = ECIES()
  .privateKey(aliceKey)
  .publicKey(bobKey.publicKey);

var message = 'some secret message';
var encrypted = alice.encrypt(message);

// encrypted will contain an encrypted buffer only Bob can decrypt

var bob = ECIES()
  .privateKey(bobKey)
  .publicKey(aliceKey.publicKey);
var decrypted = bob
  .decrypt(encrypted)
  .toString();
// decrypted will be 'some secret message'
```

## Contributing

See [CONTRIBUTING.md](https://github.com/fcash-project/fcore/blob/master/CONTRIBUTING.md) on the main fcore repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/fcash-project/fcore/blob/master/LICENSE).

Copyright 2013-2015 Fcash, Inc. Fcash is a trademark maintained by Fcash, Inc.

[fcore]: http://github.com/fcash-project/fcore
[ECIES]: http://en.wikipedia.org/wiki/Integrated_Encryption_Scheme
[ryan]: http://github.com/ryanxcharles
