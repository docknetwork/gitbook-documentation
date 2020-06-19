# Ecosystem

The following are the players in the Dock ecosystem.

### Identity owners

Entities who have an on-chain [DID](https://www.w3.org/TR/did-core/). The DID has an associated public key that can be used to authenticate the DID or verify assertions from the DID, either on-chain or off-chain.

### Issuers

Entities who issue credentials using the Dock SDK. The issuers need not have a DID on Dock \(or on any chain\) to issue as long as their public key is reliably accessible \(or embedded in the credential\) as the issuers sign the credential during issuance.

### Revocation authorities

Entities who are allowed to revoke \(or undo the revocation in some cases\) issued credentials. The issuer can choose one or more revocation authorities for a credential or decide to be the authority himself. Each credential specifies who its revocation authorities are. As the revocation registry is maintained on-chain, the revocation authorities must have an on-chain identity, which is their DID.

### Holders

Entities who receive credentials from issuers. The holders can verify the received the authenticity of the credential and its revocation status by using the Dock SDK. The holders, like issuers, do not need to have an on-chain identity if their public key is reliably accessible \(or embedded in the credential\). Holders can create presentations from their received credentials.

### Verifiers

Entities who verify the received presentations from the holder. These are generally service providers who are willing to provide some service to the holder when the holder verifiably satisfies certain conditions. The verifiability comes from the credentials used in the presentation. They don't need to have an on-chain identity.

### Validators

Entities who run a full node and are in charge of producing blocks and finalizing them. As the network will have a proof of authority consensus model in the initial stage, the validators will not stake any tokens and will be selected by the Governing Council.

### Governing Council

Entities who decide the rules of the Dock network like \(base\) fees for different operations, how are block rewards distributed, etc by controlling what \(source code\) upgrades are allowed on the network.



