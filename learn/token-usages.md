# Token usages

### Writes to the chain

Any write operation done on the chain requires spending tokens. The amount of tokens varies depending on the resource consumption of that operation including the size of the operation, disk usage, and CPU usage. All operations pay a minimum fee called the base fee.

#### DIDs

* Creating them uses tokens.
* Adding keys to DID requires tokens. There can be different kinds of keys including keys for different variations of anonymous credentials and also different schemas.
* Updating keys of DID requires tokens.

#### Revocation registries

* Creating a new revocation registry requires tokens. The amount of tokens vary depending on the type of registry and the policy \(how many DIDs control it, how many can revoke\)
* Revoking credentials requires tokens. The amount of tokens will vary depending on the number of creds being revoked and the type and policy of the registry.
* Undoing the revocation of credentials also requires tokens. The amount of tokens will vary on the same criteria as revocations

#### Schema

* Creating schema requires token and the amount depends on the size. Schemas describe the structure of credentials \(like a driver license cred should have 10 fields with such names and encodings\). Schemas are shareable among issuers as they do not contain any cryptographic material and thus are created less frequently.

### PoS validator

To become a validator in the PoS network, the candidate needs to lock tokens \("stake"\). The candidate can also invite others to lock tokens on its behalf. The network selects validators based on the stake behind them.

### Governance

The changes to the network are decided by voting on proposals and the value of the vote depends on the amount of locked tokens and lock duration.

