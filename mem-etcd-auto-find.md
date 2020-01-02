
```bash
curl -w "\n" 'https://discovery.etcd.io/new?size=3'
#https://discovery.etcd.io/86c2c0a6a4af730f6fcb4b9d658f9fbf

C:\zz\etcd\etcd.exe --name zcluster-node1 --initial-advertise-peer-urls http://192.168.6.11:2380   --listen-peer-urls http://192.168.6.11:2380   --listen-client-urls http://192.168.6.11:2379    --advertise-client-urls http://192.168.6.11:2379   --discovery https://discovery.etcd.io/86c2c0a6a4af730f6fcb4b9d658f9fbf

C:\zz\etcd\etcd.exe --name zcluster-node2 --initial-advertise-peer-urls http://192.168.6.12:2380   --listen-peer-urls http://192.168.6.12:2380   --listen-client-urls http://192.168.6.12:2379    --advertise-client-urls http://192.168.6.12:2379   --discovery https://discovery.etcd.io/86c2c0a6a4af730f6fcb4b9d658f9fbf


C:\zz\etcd\etcd.exe --name zcluster-node3 --initial-advertise-peer-urls http://192.168.6.13:2380   --listen-peer-urls http://192.168.6.13:2380   --listen-client-urls http://192.168.6.13:2379    --advertise-client-urls http://192.168.6.13:2379   --discovery https://discovery.etcd.io/86c2c0a6a4af730f6fcb4b9d658f9fbf
```