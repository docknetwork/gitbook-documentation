# Deployment

The code for the testnet is located in the [poa-1 branch](https://github.com/docknetwork/dock-substrate/tree/poa-1) of the [node repo](https://github.com/docknetwork/dock-substrate). The chain spec file for the testnet is [poa\_testnet\_raw](https://github.com/docknetwork/dock-substrate/blob/poa-1/cspec/poa_testnet_raw.json) and should be passed to the `--chain` argument to the node while running the node.  
Docker image is provided for running a node. Additionally, an [Ansible playbook](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html) is provided to deploy node with different settings. _The playbook has only been tested with Ubuntu_. The playbook needs a machine provisioned and ssh access to it. It will set up Docker on that machine, download the node's image and run a container with the given settings.

The playbook can be used to run 1 or more of the following:

1. A full node, that can optionally serve RPC traffic from clients
2. A validator node
3. A sentry node

A **full node** is a node running Dock's core software. A full node can control who is allowed to connect to it and what it's allowed to do. Validators, sentry nodes and bootstrap nodes are full nodes. A **validator node** processes transactions, produces and finalizes blocks and earns rewards. Its public keys must be shared with the network so that its produced and finalized blocks can be verified by other nodes. 

Since the validator's availability impacts the rewards, it's advised to protect it from DoS attacks. One step towards that is using one or more sentry nodes to communicate with other validators. A **sentry node** is a full node connected to the validator and filtering duplicate messages. A validator can have one or more sentry nodes with which it connects. The sentry nodes then connect to other validators and relay messages to the validator after filtering duplicate messages. 

Any node can act as a boot node lets nodes discover other nodes in the network as a full node will know the libp2p addresses of all discoverable nodes in the network. A node can become a boot node by connecting to all nodes while enabling and maintaining connections from any other node. A sentry node can act as a boot node. A full node might decide to serve RPC traffic from clients. This full node might at the same time function as boot node or sentry or validator. It is advised to run Nginx when serving clients and proxy RPC connections through it.

We recommend having a 3 tiered deployment where the 1st tier which is a validator only talks to its sentry. The sentry node is the second tier and talks to the validator its responsible for and other whitelisted \(reserved\) nodes which might be sentries of other validators or other validators or some other full nodes serving clients or bootnodes. The nodes serving clients or acting as full nodes are the 3rd tier. The objective is to allow only whitelisted traffic \(P2P or RPC\) to tier 1 and 2 and only tier 3 allows client RPC traffic.  A sentry most likely will have one full node dedicated to the serving RPC traffic from clients.   

The playbook [poa-1-testnet-node.yml](https://github.com/docknetwork/dock-substrate/blob/poa-1/scripts/ansible/poa-1-testnet-node.yml) will accept the hostname and access credentials of the machine and deploy a full node on the machine and in a Docker container. The node data is stored in a Docker volume. The playbook accepts a few arguments like 

1. node name as `node_name`
2. libp2p secret key as `libp2p_key`, if not provided, the node will generate a random key
3. whether to allow external RPC requests as  `allow_ext_rpc`, defaults to false
4. whether the node is running as a validator or not as `is_validator`, defaults to false
5. if a node is a sentry of a validator as `sentry_of` , if not provided then ignored
6. whether will only connect to its reserved \(whitelisted nodes\) as `reserved_only`, defaults to false
7. its reserved nodes as an array `reserved_nodes`, defaults to empty array
8. if the node should use bootnodes or not as an array `bootnodes`, defaults to empty array
9. what telemetry url it should use as `telemetry_url` , default to no telemetry
10. if session key should be rotated, as `rotate_session_key`, defaults to false

These arguments can be given from the command line or set in the hosts file. A [sample hosts file](https://github.com/docknetwork/dock-substrate/blob/poa-1/scripts/ansible/hosts.sample) is provided showing these variables for validator, sentry and a full node. Note that the sample file has several placeholders enclosed in angle brackets, i.e. like `<validator node ip>` or `<path of private key file>` , these should be appropriately filled. 

### Examples using the playbook

**Deploy validator** 

The validator is deployed assuming a host called `validator` defined in the `hosts` file with host variables similar to the ones in the sample hosts file

1. The following will deploy a validator with name `MyValidator`, overide the libp2p key to be `0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b` , rotate the session key and will allow connections from any node. The session key will be stored in a file called `session_key.txt`. The `rotate_session_key` flag must be used the first time the node is being set up.

   ```text
    ansible-playbook -i hosts poa-1-testnet-node.yml --extra-vars "host=validator node_name=MyValidator libp2p_key=0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b rotate_session_key=true reserved_only=false"
   ```

2. The following will deploy a validator similar to above but will only allow connections from libp2p node `/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm`. In practice, this will be the sentry. But note that value of `reserved_nodes` is an array so it can have any number of values, i.e. libp2p peer ids.

   ```text
    ansible-playbook -s poa-1-testnet-validator.yml --extra-vars "host=validator name=MyValidator libp2p_key=0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b reserved_nodes=['/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm']"
   ```

3. The following will deploy a validator but allow RPC traffic from everyone

   ```text
    ansible-playbook -s poa-1-testnet-validator.yml --extra-vars "host=validator name=MyValidator libp2p_key=0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b allow_ext_rpc=true" 
   ```

**Deploy sentry** 

The sentry is deployed assuming a host called `sentry` defined in the `hosts` file with host variables similar to the ones in the sample hosts file

1. The following will deploy a sentry with name `MySentry`, the libp2p key `0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f` for the validator running at `/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg`. The sentry node, however, allows connections from all nodes

   ```text
    ansible-playbook -s poa-1-testnet-sentry.yml --extra-vars "host=sentry name=MySentry libp2p_key=0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f sentry_of=/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg"
   ```

2. The following will deploy a sentry similar to above but the sentry will only allow connection from 2 nodes, `/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm` and `/ip4/54.218.195.100/tcp/30333/p2p/QmaWVer8pXKR8AM6u2B8r9gXivTW9vTitb6gjLM6FYQcXS`

   ```text
    ansible-playbook -s poa-1-testnet-sentry.yml --extra-vars "host=sentry name=MySentry libp2p_key=0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f sentry_of=/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg reserved_nodes=['/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm', '/ip4/54.218.195.100/tcp/30333/p2p/QmaWVer8pXKR8AM6u2B8r9gXivTW9vTitb6gjLM6FYQcXS']"
   ```

3. Similar to the validator, the sentry node can use the flag `allow_ext_rpc` to allow/disallow RPC connections from outside.

**Deploy full node** 

A full node is deployed similar to the sentry node but it allows connections from all.

1. The following will deploy a full node with name `MyFullNode`, the libp2p key `0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f` . The full node, however, allows connections from all nodes

   ```text
    ansible-playbook -s poa-1-testnet-bootstrap.yml --extra-vars "host=fullnode name=MyFullnode libp2p-key=0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f"
   ```

2. Similar to the validator and sentry, the full node can use the flag `allow_ext_rpc` to allow/disallow RPC connections from outside. 



