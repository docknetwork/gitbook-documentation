# Traceable Credentials

Anonymous credentials are credentials that allow people prove claims about themselves without having to show their personal information. For example, members of a marketing association can securely authenticate their credentials online and vote anonymously on items without revealing any of their identity details.&#x20;

But anonymity allows bad actors to hide and authorities like law enforcement need to be able to identify them in certain situations. Traceable credentials are a way to allow the relevant authorities to “unwind” that layer of privacy and identify those bad actors through verifiable encryption.

Traceability is an opt-in feature for the credential holder. A verifier can request that the holder encrypts a specific attribute like an ID number so that the regular can access it only if needed. Only the regulator would be able to decrypt the attribute, not the verifier. &#x20;

### Learn More

* [Exposing Bad Actors Who Hide Behind Anonymity With Traceable Credentials](https://blog.dock.io/exposing-bad-actors-behind-anonymity-with-traceable-credentials/)

### Developers

* [The verifiable encryption protocol is implemented in Rust here](https://github.com/docknetwork/crypto/tree/main/saver). Find the corresponding [Typescript (using the WASM bindings to the Rust code) code here](https://github.com/docknetwork/crypto-wasm-ts/).
* [How to use it with anonymous credentials](https://github.com/docknetwork/crypto-wasm-ts/#verifiable-encryption-using-saver)
* [Usage in SDK](https://github.com/docknetwork/sdk/blob/master/tests/integration/anoncreds/saver-and-bound-check.test.js)
