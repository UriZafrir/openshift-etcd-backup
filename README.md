#https://developers.redhat.com/articles/2024/09/26/enable-etcd-backups-openshift-clusters-hybrid-cloud-environments#:~:text=to%20back%20up-,How%20to%20back%20up,log%20in%20to%20master%20node.

```
oc new-project etcd-bkp
```

```
oc apply -f backup-rbac.yaml
```
