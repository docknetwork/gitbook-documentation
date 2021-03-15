# Node

The blockchain node is built on [Substrate](https://substrate.dev/) and can be found on [Github](https://github.com/docknetwork/dock-substrate). The node can either be built from the source or it can be run with Docker using the [Docker images](https://hub.docker.com/repository/docker/docknetwork/dock-substrate) at Dockerhub.

### Using with Substrate Sidecar

When using with [substrate-api-sidecar](https://github.com/paritytech/substrate-api-sidecar), you need to add [our custom types](https://github.com/docknetwork/dock-substrate/blob/master/types.json) in a file like shown below and set the environment variable `SAS_SUBSTRATE_TYPES` as the path of the types file. Refer to [this section](https://github.com/paritytech/substrate-api-sidecar#custom-substrate-types) of sidecar documentation for more details. 

```text
{
      "Address": "AccountId",
      "LookupSource": "AccountId",
      .....
      ........
 }
```

