```kubectl get nodes --show-labels```
```kubectl label nodes <your-node-name> disktype=ssd```
```kubectl label nodes <node-name> labelKey:labelValue```
```kubectl taint nodes <node-name> key1=value1:NoSchedule```
```kubectl taint nodes node1 env=prod:NoSchedule-```
```kubectl describe node <node-name>```
why taint ?
taint policies 
    NoSchedule
    PreferNoSchedule
    NoExecute

Why tolerations ?


  107  22/10/25 10:39:20 kubectl describe node ip-192-168-11-196.ec2.internal
  108  22/10/25 10:40:24 kubectl get nodes --show-labels
  109  22/10/25 10:40:57 kubectl label nodes ip-192-168-43-145.ec2.internal  disktype=ssd
  110  22/10/25 10:41:01 kubectl get nodes --show-labels
  111  22/10/25 10:41:47 kubectl describe node ip-192-168-43-145.ec2.internal
  112  22/10/25 10:42:04 ls
  113  22/10/25 10:42:14 kubectl apply -f 01-node-selector.yaml
  114  22/10/25 10:44:03 kubectl taint nodes ip-192-168-43-145.ec2.internal key1=value1:NoSchedule
  115  22/10/25 10:44:11 kubectl describe node ip-192-168-43-145.ec2.internal
  116  22/10/25 10:45:23 kubectl apply -f 02-node-selector-toleration.yaml
  117  22/10/25 10:46:36 git pull
  118  22/10/25 10:46:39 kubectl apply -f 02-node-selector-toleration.yaml
  119  22/10/25 10:47:45 kubectl taint nodes ip-192-168-43-145.ec2.internal key1=value1:NoExecute
  120  22/10/25 10:47:59 kubectl apply -f 02-node-selector-toleration.yaml
  121  22/10/25 10:48:24 kubectl taint nodes ip-192-168-43-145.ec2.internal key=value1:NoExecute
  122  22/10/25 10:49:34 kubectl taint nodes ip-192-168-43-145.ec2.internal key=value1:NoExecute-
  123  22/10/25 10:49:41 kubectl apply -f 02-node-selector-toleration.yaml
  124  22/10/25 10:50:04 kubectl taint nodes ip-192-168-43-145.ec2.internal key1=prod:NoSchedule
  125  22/10/25 10:50:13 kubectl taint nodes ip-192-168-43-145.ec2.internal key4=prod:NoSchedule
  126  22/10/25 10:50:27 kubectl apply -f 02-node-selector-toleration.yaml
  127  22/10/25 10:50:58 kubectl taint nodes ip-192-168-43-145.ec2.internal key4=prod:NoSchedule-
