node-rijndael
=============

A native binding to mcrypt's rijndael encryption with a block size of 256 bits. This allows for the encryption and decryption of data generated by Drupal, which uses rijndael-256, despite the AES standard of rijndael-128.

This module enables interfacing between PHP and Node.js, especially where third-party frameworks like Drupal are involved. Drupal uses rijndael-256 by default, and OPENSSL has no support for any block-side of rijndael apart from 128.

Installation
============

You _will_ need a development version of libmcrypt installed on your system to build node-rijndael.

```sh
# for debian derivatives
$ [sudo] apt-get install libmcrypt-dev
# for red hat derivatives
$ [sudo] yum install libmcrypt-devel
```

<small>If you know how to package an external library with a Node Addon, consider submitting a [pull request][pr].</small>

[npm][]
-------

```sh
$ npm install node-rijndael
```

[github][]
----------

```sh
$ git clone https://github.com/skeggse/double-cycle.git
```

API
===

For simplicity's sake, `node-rijndael` only operates on Buffers. You may, of course, convert your strings into buffers with `new Buffer`.

new Rijndael(key, [encoding])
-----------------------------

The constructor creates a Rijndael object bound to a specific key, with methods for encrypting and decrypting. If you don't care for an object bound to a key, use the [encrypt][] and [decrypt][] functions exported by node-rijndael.

The provided key can be either a `Buffer` or a `string`, and if a string is provided, the encoding parameter will be passed to the `Buffer` constructor.

Rijndael.encrypt(plaintext)
---------------------------

Encrypt the provided `plaintext` with the bound key, and return the encrypted `ciphertext`. `plaintext` must be a `Buffer`, and `encrypt` will return a `Buffer`.

Rijndael.decrypt(ciphertext)
---------------------------

Decrypt the provided `ciphertext` with the bound key, and return the decrypted `plaintext`. `ciphertext` must be a `Buffer`, and `decrypt` will return a `Buffer`.

rijndael.encrypt(plaintext, key)
--------------------------------

Encrypt the provided `plaintext` with the provided `key`, and return the encrypted `ciphertext`. All variables involved must be instances of `Buffer`.

rijndael.decrypt(ciphertext, key)
--------------------------------

Encrypt the provided `ciphertext` with the provided `key`, and return the encrypted `plaintext`. All variables involved must be instances of `Buffer`.

Unlicense / Public Domain
=========================

> This is free and unencumbered software released into the public domain.

> Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.

> In jurisdictions that recognize copyright laws, the author or authors of this software dedicate any and all copyright interest in the software to the public domain. We make this dedication for the benefit of the public at large and to the detriment of our heirs and successors. We intend this dedication to be an overt act of relinquishment in perpetuity of all present and future rights to this software under copyright law.

> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> For more information, please refer to <[http://unlicense.org/](http://unlicense.org/)>

[pr]: https://github.com/skeggse/node-rijndael/pulls
[encrypt]: https://github.com/skeggse/node-rijndael#rijndaelencryptplaintext-key
[decrypt]: https://github.com/skeggse/node-rijndael#rijndaeldecryptciphertext-key
[npm]: http://npmjs.org/package/node-rijndael "node-rijndael on npm"
[github]: https://github.com/skeggse/node-rijndael "node-rijndael on github"
