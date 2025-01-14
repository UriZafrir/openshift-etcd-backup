#https://docs.openshift.com/container-platform/4.14/backup_and_restore/control_plane_backup_and_restore/disaster_recovery/scenario-2-restoring-cluster-state.html


copy directory files to master
```
#scp /path/to/local/file core@remote_host:/path/to/remote/destination
scp 
```
```
ip -o address | egrep '172.20.121.27|172.20.121.28'
172.20.121.27/32
sudo ip address del 172.20.121.27/32 dev br-ex
```

reached step 14, delete ovn on worker nodes
Check the nodes to ensure they are in the Ready state.
recovery node is 172.20.121.217


```
sudo rm -f /var/lib/ovn-ic/etc/*.db
sudo systemctl restart ovs-vswitchd ovsdb-server


oc -n openshift-ovn-kubernetes delete pod -l app=ovnkube-node --field-selector=spec.nodeName==uri-rvldn-worker-0-4bphd
oc -n openshift-ovn-kubernetes get pod -l app=ovnkube-node --field-selector=spec.nodeName==uri-rvldn-worker-0-4bphd
```

need to delete
uri-rvldn-worker-0-62rlv
uri-rvldn-master-0
uri-rvldn-master-1