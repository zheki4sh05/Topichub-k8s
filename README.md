# TopicHub-web-forum deploy guide in Minikube

Links for all project's repositories: <br>
https://github.com/zheki4sh05/TopicHub-webforum <br>
https://github.com/zheki4sh05/TopicHub-ImageService <br>
https://github.com/zheki4sh05/TopicHub-frontend <br>
https://github.com/zheki4sh05/TopicHub-frontend-admin <br>

### Installation
Clone project:
```bash
https://github.com/zheki4sh05/Topichub-k8s.git
```
Go to clone folder

Init minikube:
```bash
minikube start --cpus=3 --memory=3000 --disk-size=5g
```
Go to topichub-chart folder in current repository and step-by-step apply config yamls
For Mongo Data Base
```bash
kubectl apply -f pv-mongo.yaml
```
```bash
kubectl apply -f pvc-mongo.yaml
```

PostgresSQl
```bash
kubectl apply -f pv-postgres.yaml
```
```bash
kubectl apply -f pvc-postgres.yaml
```

ConfigMap and Secret
```bash
kubectl apply -f cm.yaml
```
```bash
kubectl apply -f secret.yaml
```

In addition, apply monitoring
```bash
kubectl apply -f pv-grafana.yaml
```
```bash
kubectl apply -f pvc-grafana.yaml
```
```bash
kubectl apply -f pv-prometheus.yaml
```
```bash
kubectl apply -f pvc-prometheus.yaml
```
Next, go up and start Helm 
```bash
helm install topichub topichub-chart
```

After pods creation need to launch Ingress Controller
```bash
minikube addons enable ingress
```
So next create tunnel
```bash
minikube tunnel
```

In result, application will be access via http://localhost






