# Ecosystem

The following are Dock ecosystem stakeholders:

### Identity owners

Entities who have an on-chain [DID](https://www.w3.org/TR/did-core/). The DID \(Decentralized Identity\) has an associated public key that can be used to authenticate the DID or verify assertions from the DID, either on or off-chain.

### Issuers

Entities who issue credentials using the Dock SDK. The issuers do not need to have a DID on Dock \(or on any chain\) to issue as long as their public key is reliably accessible \(or embedded in the credential\) as the issuers sign the credential during issuance.

### Revocation authorities

Entities who are allowed to revoke \(or undo the revocation in some cases\) issued credentials. The issuer can choose one or more revocation authorities for a credential or decide to be the authority himself. Each credential specifies its revocation authorities. As the revocation registry is maintained on-chain, the revocation authorities must have an on-chain identity, which is their DID.

### Holders

Entities who receive credentials from issuers. The holders can verify the authenticity of their received credential and its revocation status by using the Dock SDK. The holders, like issuers, do not need to have an on-chain identity if their public key is reliably accessible \(or embedded in the credential\). Holders can create presentations from their received credentials.

### Verifiers

Entities who verify the received presentations from the holder. These are generally service providers who are willing to provide services to the holder when the holder verifiably satisfies certain conditions. The verifiability comes from the credentials used in the presentation. They don't need to have an on-chain identity.

### Validators

Entities who run a full node and are in charge of producing blocks and finalizing them. As the network will have a proof of authority consensus model in the initial stage, the validators will not stake any tokens and will be selected based on their testnet performance by the Governing Council.

### Governing Council

A group of individuals and/or organizations who are part of the Dock Association, a Swiss non-profit whose remit is to govern the network and manage its ongoing development while driving adoption. The council sets the rules of the Dock network including determining base fees for operations and block reward distribution by controlling what \(source code\) upgrades are allowed on the network.



