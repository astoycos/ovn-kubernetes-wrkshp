# ovn-kubernetes-wrkshp
Repo for housing materials created during the ovn-kubernetes RedHat workshops starting 06/30/21

## How to run `ovn-nbctl` commands on the static DBs provided in this repo 

** Note new ovn-dbs will most likely work with openvswitch >= 2.15 ** 

In one terminal run 

```
sudo ovsdb-server --remote=punix:$(pwd)/ovndb.sock
```

To Start a local ovsdb instance 

Then in another terminal run 

```
sudo ovsdb-client restore unix:$(pwd)/ovndb.sock < <DB Snapshot> 
```

Then you should be able to run normal `nbctl`, `sbctl` and even `ovn-trace` 
commands on the local instance like so: 

```
sudo ovn-nbctl --db=unix:$(pwd)/ovndb.sock show
```