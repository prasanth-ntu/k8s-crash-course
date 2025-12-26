# k8s-demo

Kubernetes manifests for MongoDB + a demo webapp (from Nana Janashia's k8s demo).

## Apply

```bash
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f webapp.yml
```

## Access (Minikube)

```bash
minikube service webapp-service --url
# or
kubectl port-forward svc/webapp-service 3000:3000
```

## Files

- `mongo-config.yaml` - ConfigMap with MongoDB service URL
- `mongo-secret.yaml` - Secret with MongoDB credentials (base64 encoded)
- `mongo.yaml` - MongoDB Deployment + Service
- `webapp.yml` - Web app Deployment + NodePort Service
