<img src="http://www.fcash.cash/css/images/module-ecies.png" alt="fcash-base ecies" height="35">
# ECIES for fcash-base

[![NPM Package](https://img.shields.io/npm/v/fcash-ecies.svg?style=flat-square)](https://www.npmjs.org/package/fcash-ecies)
[![Build Status](https://img.shields.io/travis/fcash-js/fcash-ecies.svg?branch=master&style=flat-square)](https://travis-ci.org/fcash-js/fcash-ecies)
[![Coverage Status](https://img.shields.io/coveralls/fcash-js/fcash-ecies.svg?style=flat-square)](https://coveralls.io/r/fcash-js/fcash-ecies)

A module for [fcash-base][fcash-base] that implements the [Elliptic Curve Integrated Encryption Scheme (ECIES)][ECIES]. Uses ECIES symmetric key negotiation from public keys to encrypt arbitrarily long data streams.

See [the main fcash-base repo](https://github.com/fcash-js/fcash-base) or the [fcash-base guide on ECIES](http://www.fcash.cash/guide/module/ecies/index.html) for more information.

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

See [CONTRIBUTING.md](https://github.com/fcash-js/fcash-base/blob/master/CONTRIBUTING.md) on the main fcash-base repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/fcash-js/fcash-base/blob/master/LICENSE).

Copyright 2013-2015 Fcash, Inc. Fcash is a trademark maintained by Fcash, Inc.

[fcash-base]: http://github.com/fcash-js/fcash-base
[ECIES]: http://en.wikipedia.org/wiki/Integrated_Encryption_Scheme
[ryan]: http://github.com/ryanxcharles
