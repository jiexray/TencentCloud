# NFS Server Installment on Tencent Cloud(Ubuntu)
* 1. Get NFS-server by `apt-get`
```
sudo apt-get install nfs-kernel-server
```
* 2. Edit `conf` file and start NFS server
```
sudo vi /etc/exports
```
Add a new mountpoint
```
/nfs *(rw,sync,no_subtree_check,no_root_squash,insecure)
```
Here:
- `/nfs`: mount point(a folder)
- `rw`: read, write permission
- `sync`: consistent
- `no_subtree_check`: do not check father folder's permission
- `no_root_squash`: let you become a root, you can write to this folder
- `insecure`: the limit of the TCP port(>1024).
Restart server
```
sudo service nfs-kernel-server restart
```
Here you can check your work by
```
mkdir your_dir
sudo mount -t nfs localhost:/nfs your_dir
```
If this work, Continue.
* 3. Modify `mountd` port number
Modify port number of mountd
```
sudo vi /etc/services
```
Add this at the bottom of the file
```
mountd 49780/tcp
mountd 49780/udp
```
Check your port
```
rpcinfo -p localhost
```
* 4. Open port at Tencent Cloud
open following ports:
```
111 portmapper tcp
2049 nfs tcp
49780 mountd tcp
```
* 5. Connect to NFS Server from mac
```
mount -o tcp,nolock -t nfs address:/nfs your_dir
```

**Finished**

## Problems
* 1. Not set `insecure`, cannot set `mountd`'s port number greater than 1024
