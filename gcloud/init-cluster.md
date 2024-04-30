### Create cluster on google environment

```bash
gcloud container clusters create demo --zone us-central1-c --machine-type e2-medium --num-nodes 2
```
### Delete cluster on google environment

```bash
gcloud container clusters delete demo --zone us-central1-c --project education-410810
```
### Get credentials
```bash
gcloud container clusters get-credentials demo --zone us-central1-c --project education-410810
```

### Check resources
```bash
kubectl get all -A
```

### Create deploy
```bash
kubectl create deploy demo --image gcr.io/education-410810/demo:v1.0.0
```

### Expose
```bash
kubectl expose deploy demo --port 80 --type LoadBalancer --target-port 8080
```
### Get Service details
```bash
kubectl get svc -w
```

### UPDATE
```bash
kubectl set image deploy demo demo=gcr.io/education-410810/demo:v2.0.0
```
### Check 
```bash
kubectl get deployments.apps -o wide
```
## Rollout 
### Check 
```bash
kubectl rollout history deploy demo
```

### undo 
```bash
kubectl rollout undo deploy demo --to-revision 1
```

### select with selectors by labels
```bash
kubectl get po -l app=demo
```

### update labels for group of pods
```bash
kubectl label po --all run=demo
```

### scale deploy
```bash
kubectl scale deploy demo --replicas 9
```
