#https://developers.redhat.com/articles/2024/09/26/enable-etcd-backups-openshift-clusters-hybrid-cloud-environments#:~:text=to%20back%20up-,How%20to%20back%20up,log%20in%20to%20master%20node.

```
oc new-project etcd-bkp
```

```
oc apply -f backup-rbac.yaml
oc apply -f backup-storage.yaml
oc apply -f backup-cronjob.yaml

```

To test the backup, or create an manual backup, you can run a job:
```
backupName=$(date "+etcd-backup-manual-%F-%H-%M-%S")
oc create job --from=cronjob/cronjob-etcd-backup ${backupName}
```

To see if everything works as it should, you can check the logs:
```
oc logs -l job-name=${backupName}
```
Then check on your Storage, if the files are there as excepted.
