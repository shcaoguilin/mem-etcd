
## golang,goland
install golang to C:\Go\
install goland-2019.3.1.exe

## etcd run in cmd
in cmd
- cd C:\zz\
- git clone https://github.com/etcd-io/etcd.git  # C:\zz\etcd\.git\
export GOPROXY=https://goproxy.io
- set GOPROXY=https://goproxy.io
- .\build.bat


## etcd run in goland
in goland
- # open C:\zz\etcd\




## etcd cluster mode,run in goland or cmd
etcd cluster mode
- mkdir c:\zz\etcd_log\

### node1
- C:\zz\etcd\etcd.exe -name zcluster-node1 -debug -initial-advertise-peer-urls http://192.168.6.11:2380 -listen-peer-urls http://192.168.6.11:2380 -listen-client-urls http://192.168.6.11:2379 -advertise-client-urls http://192.168.6.11:2379 -initial-cluster-token zcluster-token -initial-cluster zcluster-node1=http://192.168.6.11:2380,zcluster-node2=http://192.168.6.12:2380,zcluster-node3=http://192.168.6.13:2380 -initial-cluster-state new  >> c:\zz\etcd_log\192.168.6.11.etcd.log

### node2
- C:\zz\etcd\etcd.exe -name zcluster-node2 -debug -initial-advertise-peer-urls http://192.168.6.12:2380 -listen-peer-urls http://192.168.6.12:2380 -listen-client-urls http://192.168.6.12:2379 -advertise-client-urls http://192.168.6.12:2379 -initial-cluster-token zcluster-token -initial-cluster zcluster-node1=http://192.168.6.11:2380,zcluster-node2=http://192.168.6.12:2380,zcluster-node3=http://192.168.6.13:2380 -initial-cluster-state new  >> c:\zz\etcd_log\192.168.6.12.etcd.log

### node3
- C:\zz\etcd\etcd.exe -name zcluster-node3 -debug -initial-advertise-peer-urls http://192.168.6.13:2380 -listen-peer-urls http://192.168.6.13:2380 -listen-client-urls http://192.168.6.13:2379 -advertise-client-urls http://192.168.6.13:2379 -initial-cluster-token zcluster-token -initial-cluster zcluster-node1=http://192.168.6.11:2380,zcluster-node2=http://192.168.6.12:2380,zcluster-node3=http://192.168.6.13:2380 -initial-cluster-state new  >> c:\zz\etcd_log\192.168.6.13.etcd.log

## client
- curl -L http://192.168.11.13:2379/v3/kv/put   -X POST -d '{"key": "Zm9v", "value": "YmFy"}'
