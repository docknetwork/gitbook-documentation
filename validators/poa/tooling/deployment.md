# Deployment

Docker images are provided for the testnet and mainnet for various versions. But the scripts `run_poa_test_node` and `run_poa_main_node` run the latest version of the testnet and mainnet respectively. The scripts must be run on the machine on which the node is supposed to be hosted either by logging into the machine or via remote execution.

The provided Docker images can be used to run 1 or more of the following:

1. A full node
2. A validator node
3. A sentry node
4. A bootstrap node
5. A full node serving RPC traffic from clients
6. A JSON-RPC proxy

A **full node** is a node running Dock's core software. A full node can control who is allowed to connect to it and what it's allowed to do. Validators, sentry nodes and bootstrap nodes are full nodes. A **validator node** processes transactions, produces and finalizes blocks and earns rewards. Its public keys must be shared with the network so that its produced and finalized blocks can be verified by other nodes. 

Since the validator's availability impacts the rewards, it's advised to protect it from DoS attacks. One step towards that is using 1 or more sentry nodes to communicate with other validators. A **sentry node** is a full node connected to the validator and filtering duplicate messages. A validator can have 1 or more sentry nodes and it only connects to those sentry nodes. The sentry nodes then connect to other validators and relay messages to the validator after filtering duplicate messages. 

**A bootstrap node** lets full nodes discover other nodes in the network as a full node will know the libp2p addresses of all discoverable nodes in the network. Any node can become a bootstrap node by connecting to all nodes while enabling and maintaining connections from any other node. A sentry node can act as a bootstrap node. A full node might decide to serve RPC traffic from clients. This full node might at the same time function as bootstrap node or sentry or validator. A "JSON-RPC proxy" is not a full node but serves a filter for client RPC traffic allowing only certain methods to be called. It is advised to run this when serving clients and have it behind an Nginx server.

### Scripts

**Deploy nodes on the validator** 

The scripts will accept the hostname and access credentials of the machine and deploy a full node on the machine and by running a Docker container. The node data is stored in a Docker volume. [Ansible](https://www.ansible.com/) [playbooks](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html) are used to run the services.

Deploy validator The validator is deployed by downloading the latest Docker image on the remote machine, creating a docker volume if not present, and using the volume for keeping chain state.  
  
_Note: The scripts mentioned below are not written yet and will be made available once we launch the testnet._

1. The following will deploy a validator with name `MyValidator`, the libp2p key `0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b`, aura seed `0xa80035a771055e7414ecfa8e884447ef07a557020f353b809269cd0ab9fc185e`, grandpa seed `0xb0cbb37e0840a9fed7bd754bd154c672083d540314fbfc11248bd6f50e947ba5` and will allow connections from any node.

   ```text
    ansible-playbook -s poa-testnet-validator.yml --extra-vars "name=MyValidator libp2p-key=0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b aur-sk= 0xa80035a771055e7414ecfa8e884447ef07a557020f353b809269cd0ab9fc185e gran-sk=0xb0cbb37e0840a9fed7bd754bd154c672083d540314fbfc11248bd6f50e947ba5"
   ```

2. The following will deploy a validator similar to above but will only allow connections from libp2p node `/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm`. In practice, this will be the sentry. But note that value of `reserved-nodes` is an array so it can have any number of values, i.e. libp2p peer ids.

   ```text
    ansible-playbook -s poa-testnet-validator.yml --extra-vars "name=MyValidator libp2p-key=0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b aur-sk= 0xa80035a771055e7414ecfa8e884447ef07a557020f353b809269cd0ab9fc185e gran-sk=0xb0cbb37e0840a9fed7bd754bd154c672083d540314fbfc11248bd6f50e947ba5 reserved-nodes=['/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm']"
   ```

3. The following will deploy a validator but allow RPC traffic from everyone

   ```text
    ansible-playbook -s poa-testnet-validator.yml --extra-vars "name=MyValidator libp2p-key=0x2c0ac6d8f3eb6b51af3e67f851f8d72875f3c6a0612ce67fe1cfa6f0e46deb6b aur-sk= 0xa80035a771055e7414ecfa8e884447ef07a557020f353b809269cd0ab9fc185e gran-sk=0xb0cbb37e0840a9fed7bd754bd154c672083d540314fbfc11248bd6f50e947ba5 allowRPCExt=true"
   ```

Similarly, `poa-mainnet-validator.yml` can be used for mainnet

Deploy sentry A sentry node is deployed similar to the validator but does not need the aura and grandpa keys as it's not producing or finalizing blocks.

1. The following will deploy a sentry with name `MySentry`, the libp2p key `0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f` for the validator running at `/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg`. The sentry node, however, allows connections from all nodes

   ```text
    ansible-playbook -s poa-testnet-sentry.yml --extra-vars "name=MySentry libp2p-key=0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f sentry=/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg"
   ```

2. The following will deploy a sentry similar to above but the sentry will only allow connection from 2 nodes, `/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm` and `/ip4/54.218.195.100/tcp/30333/p2p/QmaWVer8pXKR8AM6u2B8r9gXivTW9vTitb6gjLM6FYQcXS`

   ```text
    ansible-playbook -s poa-testnet-sentry.yml --extra-vars "name=MySentry libp2p-key=0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f sentry=/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg reserved-nodes=['/ip4/35.155.248.216/tcp/30333/p2p/QmawgZD3BANiKR72ZXsSEEAMpz9iQkCy4r2RDyihQysuRm', '/ip4/54.218.195.100/tcp/30333/p2p/QmaWVer8pXKR8AM6u2B8r9gXivTW9vTitb6gjLM6FYQcXS']"
   ```

3. Similar to the validator, the sentry node can use the flag `allowRPCExt` to allow RPC connections from outside.

Similarly, `poa-mainnet-sentry.yml` can be used for mainnet

Deploy bootstrap node A bootstrap node is deployed similar to the sentry node but it allows connections from all.

1. The following will deploy a sentry with name `MySentry`, the libp2p key `0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f` for the validator running at `/ip4/44.231.55.99/tcp/30333/p2p/QmaAARGgiUyGfqi87ZscaDRKknyw9jX9jJqsBwFi9jocYg`. The sentry node, however, allows connections from all nodes

   ```text
    ansible-playbook -s poa-testnet-bootstrap.yml --extra-vars "name=MyBootnode libp2p-key=0x8d72875f3c6a0612ce67fe1cfa6f0e46deb6b2c0ac6d8f3eb6b51af3e67f851f"
   ```

2. Similar to the validator and sentry, the bootstrap node can use the flag `allowRPCExt` to allow RPC connections from outside. Also, the flag `allowPrometheusExt` allows any Prometheus server to pull data from the node and setting `allowTelemetry` to false disables the telemetry endpoint.

JSON-proxy To allow only specific RPC calls, run the JSON-proxy server below. The run below will make the server listed to all hosts and at port 9949. It expects the full node at 9944.

```text
ansible-playbook -s json-proxy.yml --extra-vars "listen='0.0.0.0:9949' full-node=127.0.0.1:9944"
```



