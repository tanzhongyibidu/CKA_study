# Cluster 11%
https://cka-exam.blog/cluster-maintenance-11/

 * Understand Kubernetes cluster upgrade proces.
   * The current state of cluster upgrades is provider dependent. https://kubernetes.io/docs/tasks/administer-cluster/cluster-management/

 * Facilitate operating system upgrades.
   * https://kubernetes.io/docs/tasks/administer-cluster/cluster-management/#maintenance-on-a-node
     * kubectl drain $NODENAME
     * kubectl uncordon $NODENAME

 * Implement backup and restore methodologies.

  About etcd, look at the chapter focused on backup&restore:
  * Etcd disaster recovery documentation
  https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/

  * ETCD backup:
    * ETCDCTL_API=3 etcdctl --endpoints=https://127.0.0.1:2379 --cert=/etc/kubernetes/pki/apiserver-etcd-client.crt --key=/etc/kubernetes/pki/apiserver-etcd-client.key --cacert=/etc/kubernetes/pki/etcd/ca.crt  snapshot save snapshot.db
    
    * ETCDCTL_API=3 etcdctl --endpoints=https://127.0.0.1:2379 --cert=/etc/kubernetes/pki/apiserver-etcd-client.crt --key=/etc/kubernetes/pki/apiserver-etcd-client.key --cacert=/etc/kubernetes/pki/etcd/ca.crt  snapshot status ./snapshot.db --write-out=table

