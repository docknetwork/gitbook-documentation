# Token usages

### Writes to the Dock Blockchain

Any write operation completed on-chain requires tokens. The amount of tokens varies depending on the resource consumption of that operation including; it's size, disk usage, and CPU usage. All operations pay a minimum fee called the base fee.

#### DIDs \(Decentralized Identities\)

* Creating them uses tokens.
* Adding keys to DIDs requires tokens. There are different kinds of keys including those for different variations of anonymous credentials and also keys utilizing different schemas.
* Updating keys of DID requires tokens.

#### Revocation registries

* Creating a new revocation registry requires tokens. The number of

  tokens will vary depending on the type of registry and the policy .i.e. how many DIDs control it and how many can revoke the registry.

* Revoking credentials requires tokens. The number of tokens will vary depending on the number of credentials being revoked and the type and policy of the registry.
* Undoing the revocation of credentials also requires tokens. The number of tokens will vary on the same criteria as revocations.

#### Schema

* Creating schema requires tokens with the number depending on the schema size. Schemas describe the structure of credentials .i.e. a driver license credential should have 10 fields including the licensees name and address. Schemas are shareable among issuers as they do not contain any cryptographic material and thus are created less frequently.

### PoS validator

To become a validator in the PoS network, the candidate needs to lock tokens \("stake"\). The candidate can also invite others to lock tokens on its behalf. The network selects validators based on the stake behind them.

### Governance

The changes to the network are decided by voting on proposals and the value of the vote depends on the number of locked tokens and lock duration.

