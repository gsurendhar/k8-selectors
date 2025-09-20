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

