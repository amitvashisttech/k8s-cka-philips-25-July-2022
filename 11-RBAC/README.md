```
402  cd 11-RBAC/
  403  ls
  404  kubectl  get pods
  405  kubectl  get roles
  406  kubectl create role pod-reader --help
  407  kubectl create role pod-reader --verb=get,list,watch --resource=pods,deployment --dry-run
  408  kubectl create role pod-reader --verb=get,list,watch --resource=pods,deployment --dry-run -o yaml
  409  kubectl create role pod-reader --verb=get,list,watch --resource=pods,deployment --dry-run -o yaml  > pod-reader-role.yaml
  410  ls
  411  mv pod-reader-role.yaml 01-Pod-reader-role.yaml
  412  ls
  413  kubectl  apply -f 01-Pod-reader-role.yaml
  414  kubectl get roles
  415  kubectl describe roles pod-reader
  416  kubectl create rolebinding pod-reader-binding-amit --role=pod-reader --user=amit --dry-run
  417  kubectl create rolebinding pod-reader-binding-amit --role=pod-reader --user=amit --dry-run -o yaml > 02-Pod-reader-binding-amit.yaml
  418  ls
  419  kubectl  get rolebindings
  420  kubectl  apply -f 02-Pod-reader-binding-amit.yaml
  421  kubectl  get rolebindings
  422  kubectl  describe  rolebindings
  423  kubectl  describe  role
  424  kubectl auth can-i get pods --user=amit
  425  kubectl auth can-i delete pods --user=amit
  426  kubectl auth can-i create deployments --user=amit
  427  kubectl  get clusterroles
  428  kubectl create rolebinding cluster-admin-binding-amit --clusterrole=cluster-admin --user=amit --dry-run
  429  kubectl create rolebinding cluster-admin-binding-amit --clusterrole=cluster-admin --user=amit --dry-run -o yaml > 03-Cluster-Admin-binding-amit.yaml
  430  kubectl auth can-i create deployments --user=amit
  431  kubectl auth can-i delete pods --user=amit
  432  kubectl  apply -f 03-Cluster-Admin-binding-amit.yaml
  433  kubectl auth can-i create deployments --user=amit
  434  kubectl auth can-i delete pods --user=amit
  435  kubectl auth can-i delete pods -n kube-system --user=amit
  436  kubectl  get rolebindings
  437  kubectl create clusterrolebinding cluster-admin-cluster-binding-amit --clusterrole=cluster-admin --user=amit --dry-run -o yaml > 04-Cluster-Admin-Clusterbinding-amit.yaml
  438  kubectl  apply -f 04-Cluster-Admin-Clusterbinding-amit.yaml
  439  kubectl  get rolebindings
  440  kubectl  get clusterrolebindings
  441  kubectl auth can-i delete pods -n kube-system --user=amit
  442  kubectl auth can-i delete ns myspace2 --user=amit
  443  kubectl auth can-i delete ns myspace --user=amit
  444  kubectl  get ns
  445  kubectl auth can-i delete namespace myspace2 --user=amit
  446  kubectl  delete -f 04-Cluster-Admin-Clusterbinding-amit.yaml
  447  kubectl  get rolebindings
  448  kubectl  delete -f 03-Cluster-Admin-binding-amit.yaml
  449  kubectl  get rolebindings
  450  kubectl  delete -f 02-Pod-reader-binding-amit.yaml

```
