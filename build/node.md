# Node

The blockchain node is built on [Substrate](https://substrate.dev/) and can be found on [Github](https://github.com/docknetwork/dock-substrate). The node can either be built from source or it can be run with Docker using the [Docker images](https://hub.docker.com/repository/docker/docknetwork/dock-substrate) at Dockerhub.

### Using with Substrate Sidecar

When using with [substrate-api-sidecar](https://github.com/paritytech/substrate-api-sidecar), you need to provide [our custom types](https://github.com/docknetwork/dock-substrate/blob/master/types.json) in [config/types.json](https://github.com/paritytech/substrate-api-sidecar/blob/master/config/types.json) like below 

```text
{
  "CUSTOM_TYPES": {
      "Address": "AccountId",
      "LookupSource": "AccountId",
      .....
      ........
 }
```



