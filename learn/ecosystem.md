# Ecosystem

The following are Dock ecosystem stakeholders:

### Identity owners

Entities who have an on-chain [DID](https://www.w3.org/TR/did-core/). The DID (Decentralized Identity) has an associated public key that can be used to authenticate the DID or verify assertions from the DID, either on or off-chain.

### Issuers

Entities who issue credentials using the Dock network. **** The issuers can be organizations, developers, companies, or government entities that provide credentials. **** The issuers sign the credential during issuance and thus their public key needs to be known for signature verification. We strongly recommend having a [DID](https://www.w3.org/TR/did-core/) with which their public key is associated but its not mandatory long as their public key is reliably accessible (or embedded in the credential) as shown [here](https://www.w3.org/TR/vc-data-model/#issuer).

### Holders

Entities who receive credentials from issuers. The holders can verify the authenticity of their received credential and its revocation status by using the Dock SDK. The holders, like issuers, do not need to have an on-chain identity if their public key is reliably accessible (or embedded in the credential). Holders can create presentations from their received credentials.

### Verifiers

Entities who verify the received presentations from the holder. These are generally organizations that require verification of certain conditions to be satisfied by the holder in order to engage, transact, or provide services to holders. The verifiability comes from the credentials used in the presentation.

### Validators

Entities who run a full node on the Dock network and are in charge of producing blocks and finalizing them. The Dock network has a Proof of Stake consensus which requires validators to stake Dock tokens, or have tokens staked on their behalf, in order to participate in validating the network and are rewarded for their efforts.

### Governing Council

A group of individuals who are elected using Dock's open governance to make and implement proposals such as determining base fees for operations or block reward distribution by controlling which (source code) upgrades are allowed on the network. They work with the Dock Association, a Swiss non-profit whose remit is to govern the network and manage its ongoing development while driving adoption.

### Revocation authorities

Entities who are allowed to revoke (or undo the revocation in some cases) issued credentials. The issuer can choose one or more revocation authorities for a credential or decide to be the authority himself. Each credential specifies its revocation authorities. As the revocation registry is maintained on-chain, the revocation authorities must have an on-chain identity, which is their DID.

###

