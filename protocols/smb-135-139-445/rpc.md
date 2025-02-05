# rpc

## Recon

```bash
# rpcbind port converts RPC to universal address 
# allows to access the NFS, port:111 
nmap --script=nfs-ls,nfs-statfs,nfs-showmount -p 111 $ip

nmap --script rpcinfo.nse -p 111 $ip
rpcinfo –p IP
rpcbind -p IP

# dumps the remote RPC endpoints information via epmapper.
impacket-rpcdump @[IP | DOMAIN]
```

## rpclient

* [Plundering Windows Account Info via **
  Authenticated** SMB Sessions](https://www.sans.org/blog/plundering-windows-account-info-via-authenticated-smb-sessions/)

```bash
rpcclient -U ['' | USER%PASS | DOMAIN\USER%PASS] IP [-N]
# -N: no password

srvinfo: server information => os.version, samba-version.

querydominfo
enumdomusers: enum DOM users
enumalsgroups domain: ?

lookupnames USER: looks up USER if exists
queryuser USER: Get more information about user

enumprinters: enum printers
```

## enumerate users using SIDs (windows only)

```bash
# needs some user creds (smb also works)
lookupsid.py <USER>:<PASS>@<IP>
```
