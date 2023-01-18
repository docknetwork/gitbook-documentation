# Multikey Support for Decentralized Identifiers (DIDs)

Dock DIDs can support multiple keys that can be used for different purposes.&#x20;

For example, an issuer could use different keys for each of these functions:

* Issuance of credentials
* Authenticating with some other application
* Engaging in secure communication
* Revoking an issued credential

### For Developers

A DID can have multiple keys that have different capabilities called Verification relationships in the [W3C DID spec](https://www.w3.org/TR/did-core/#verification-relationships). A key can have one or more Verification relationships to the DID depending on the kind of functions it's supposed to perform on the DID's behalf.

**We support 4 verification relationships:**

1. **Authentication:** Keys with this relationship can only be used for authentication such as convincing a party that it’s a key of the DID.
2. **Assertion:** Used for signing credentials during issuance.
3. **Key agreement:** Used during secure communication to encrypt some data for the DID.
4. **Capability invocation:** These keys can modify the [DID Document](https://www.w3.org/TR/did-core/#dfn-did-documents) such as adding existing keys, removing service endpoints, and so on.

**Key DID features**

* DIDs can be controlled by other DIDs
* DIDs can have service endpoints
* Supports off-chain DID Documents

### Learn More

* Technical walkthrough of these features: [Conceptual explanation](https://docknetwork.github.io/sdk/tutorials/concepts\_did.html) and [hands-on example](https://docknetwork.github.io/sdk/tutorials/tutorial\_did.html)
* [Product Update: Dock DIDs Now Support Multiple Key Pairs](https://blog.dock.io/dids-multikey-support/)
