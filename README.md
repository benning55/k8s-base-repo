# k8s-base-repo

# Minikube
```
You can identify which port you want to expose

minikube start --ports=30100:30100,30200:30200

You can also delete

minikube delete
```

# Rancher
```
docker run --privileged -d --restart=unless-stopped -p 80:80 -p 443:443 rancher/rancher
```

# Encodeing secret
```
echo -n <value> | base64
```

# Step
```
Create Mongo
1. kubectl apply -f mongo-config.yaml
2. kubectl apply -f mongo-secret.yaml
3. kubectl apply -f mongo.yaml

Create App
1. kubectl apply -f webapp.yaml 


Check
1. kubectl get all
2. kubectl get configmap
3. kubectl get secret

Log the pod
kubectl logs -f webapp-deployment-8d94f95d6-c5whs (stream)
kubectl logs webapp-deployment-8d94f95d6-c5whs (not-stream)

Find url of the node to access application
1. kubectl get node -o wide

NAME       STATUS   ROLES           AGE    VERSION   INTERNAL-IP    EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION      CONTAINER-RUNTIME
minikube   Ready    control-plane   146m   v1.26.1   192.168.58.2   <none>        Ubuntu 20.04.5 LTS   5.10.104-linuxkit   docker://20.10.23

2. access via INTERNAL-IP
```