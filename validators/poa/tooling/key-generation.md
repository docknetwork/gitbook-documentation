# Key generation

The script `gen_keys_poa_validator` \(LINK NEEDED\) is present in the Substrate node's `scripts` directory. It requires 4 arguments, an account type, an account password, a session password and a network type.

* The account type can have one of the three values: `ed25519`, `sr25519` and `secp256k1` to generate the type of account private key.
* The account password is used to protect the account secret phrase.
* The session password is used to protect the secret phrase used for generating Aura and Grandpa keys.
* The network type can be either `test` or `main` depending on for which network the account is generated.

It generates the following:

1. An account address.
2. The account's private key.
3. The secret phrase for account. This phrase is protected by the password.
4. The secret phrase used for generating Aura and Grandpa keys. This phrase is protected by the password.
5. An Aura private key
6. The corresponding Aura public key
7. A Grandpa private key
8. The corresponding Grandpa public key
9. The libp2p peer id
10. The path of the file containing the libp2p secret key

During the validator application, the information shown in blue, i.e. the account address, the Aura public key, Grandpa public key and the libp2p public key must be submitted to Dock and the private information shown in red, i.e. the secret phrases and the private keys must be stored securely. Also the passwords must be remembered if the keys are to be regenerated using the secret phrase. The file containing libp2p secret key must be secured and is moved to the validator node. This script internally uses `subkey`.

Some example runs and their outputs:

1. Generate an ed25519 account with passwords `pass1` and `pass2` for account and validator keys respectively, for the testnet

   ```text
    gen_keys_poa_validator ed25519 pass1 pass2 test
   ```

   TODO: SHOW COLORED OUTPUT  

2. Generate an sr25519 account with passwords `foo` and `bar` for account and validator keys respectively, for the mainnet

   ```text
    gen_keys_poa_validator sr25519 foo bar main
   ```

   TODO: SHOW COLORED OUTPUT  

3. Generate a secp256k1 account with passwords `foo` and `baz` for account and validator keys respectively, for the mainnet

   ```text
    gen_keys_poa_validator secp256k1 foo baz main
   ```

   TODO: SHOW COLORED OUTPUT

Clear your bash history and console buffer once you have noted the above information elsewhere.

In case the validator wants to change his account or keys, he should run the above script again and submit the new account and/or the validator keys.

