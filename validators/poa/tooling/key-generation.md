# Key generation

There are two scripts provided, one to generate account \(and associated keypair\) and libp2p keypair and the other to rotate the session key of a running node and return the new key. A candidate validator is expected to generate his account and libp2p keypair with the first script and then run his node with the libp2p key and then run the second script to rotate his session key and then share the account address and session key with Dock before his node can be made a validator.

The script [gen\_keys\_poa\_validator](https://github.com/docknetwork/dock-substrate/blob/poa-1/scripts/gen_keys_poa_validator) is used to generate account and libp2p keypair and is present in the Substrate node's [scripts](https://github.com/docknetwork/dock-substrate/tree/poa-1/scripts) directory. This script internally uses [subkey](https://www.substrate.io/kb/integrate/subkey) and requires it to be installed. It requires 2 arguments: account type and an account password.

* The account type can have one of the three values: `ed25519`, `sr25519` and `secp256k1` to generate the type of account private key.
* The account password is used to protect the account secret phrase.

It generates the following:

1. An account address.
2. The account's private key.
3. The secret phrase for the account, this phrase is protected by the password.
4. The libp2p public key.
5. The libp2p secret key.
6. The name of the file containing the libp2p secret key.

The script [rotate\_session\_key](https://github.com/docknetwork/dock-substrate/blob/poa-1/scripts/rotate_session_key) is used to rotate the session key of a running node and return the newly generated and set session key.  It optionally accepts an argument of the node's RPC endpoint and if not given, assumes the node running at http://localhost:9933. 

Some example runs and their outputs:

1. Generate an `ed25519` account with password `pass` to generate account and libp2p keys respectively. The secret information is displayed in red. In place of `ed25519`, `sr25519` and `ecdsa` can be used as well.

   ```text
   $ ./scripts/gen_keys_poa_validator ed25519 pass
   The account address in ss58 format is 5EiCZUY3G6JhN2TTb6R6wEXvbhnp5ciww12rbxX3FJrZefob
   The secret phrase for the account is file upper fever fog achieve side catalog flash age bright mirror split
   The secret key for the account is 0x67826291fd8ce9941e19e2e0d97ad16cd467f40aee9c29898570f9b28645d7c2
   The libp2p public key is QmbhFxGwMoEaK6gSwDR85KLbZt1nwRjktuQTouq1cacu4z
   The libp2p secret key is 2195edf5175f4370051a06415f06b042048e2ed5db8106264ffd82d3a044e294
   The libp2p secret key is also stored in the file lib-p2p-secret.key
   ```

2. Rotate the session key of a running node. The following run assumes the node is running at http://localhost:9933.

   ```text
    $ ./scripts/rotate_session_key
    The session key is 0xd4a23d286b25aa8ee401acf2ac10232047b40905c327c3dd9ab5442cb9539663b1bb339873b201d3995c88bb1e8f6983878be18ae65abce4cc41ef0de01fa8ae
   ```

Clear your bash history and console buffer once you have noted the above information elsewhere.

If the validator wishes to change their account or session, they can run the above script again and submit the new account and/or the session keys.

