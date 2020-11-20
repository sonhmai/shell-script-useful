# kubeclt related scripts

## act on multiple deployments,...

### update deployment by rollout
kubectl get deployment | grep $DEPLOYMENT | awk '{print $1}' | xargs -n 1 kubectl rollout restart deployment 

### update deployment by scaling
kubectl get deployment | grep $DEPLOYMENT | awk '{print $1}' | xargs -n 1 kubectl scale deployment --replicas 0
kubectl get deployment | grep $DEPLOYMENT | awk '{print $1}' | xargs -n 1 kubectl scale deployment --replicas 1
