# Change ports in NFS server
* 1. `mountd` damoen service use random port number. If we want to set up a fixed port add `--port` option in file
`/etc/default/nfs-kernel-server`.
```
RPCMOUNTDOPTS="--manage-gids --port 56172"
```
