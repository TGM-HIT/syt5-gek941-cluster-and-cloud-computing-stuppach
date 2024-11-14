# SYT GK941 Cluster- und Cloud-Computing 
### "Container mit Kubernetes" 

**Authors:** Stuppig Markus 5DHIT, Wallpach Melissa 5BHIT
**Version:** 2024-11-14

## Einführung 
In dieser Aufgabe wird Kubernetes als aktuelle Lösung zum Starten und Verwalten von verteilten Rechnungsresourcen behandelt. Kubernetes bietet sich hier als eine beliebte, konstenlose Open-Source Lösung, die bei den meisten Cloud-Anbietern aber auch im eigenen Einsatz in einer On-Premise Cloud zum Einsatz kommt.

**Ziel** ist der Einsatz von Orchestrierungs-Engine zur Bereitstellung und Skalierung von Containeranwendungen.


## Umsetzung 

Anleitung zur Installation und Einrichtung von kubectl auf macOS:

### 1. kubectl installieren:

Mit Homebrew :

```bash
# kubectl installieren
brew install kubectl

# Version überprüfen
kubectl version --client
```

oder manuell mit curl:

```bash
# Neueste Version herunterladen
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/amd64/kubectl"

# Binary ausführbar machen
chmod +x ./kubectl

# kubectl in den PATH verschieben
sudo mv ./kubectl /usr/local/bin/kubectl

# Version überprüfen
kubectl version --client
```

### 2. Lokales Cluster einrichten:

```bash
# minikube installieren
brew install minikube

# Cluster starten
minikube start

# Cluster-Status überprüfen
kubectl cluster-info
```

### 3. Einen Dienst im Kubernetes Cluster deployen:

```bash
# Deployment-YAML erstellen
cat <<EOF > nginx-deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
EOF

# Deployment anwenden
kubectl apply -f nginx-deployment.yaml

# Deployment-Status überprüfen
kubectl get deployments
```

### 4. Zugang auf den Dienst erhalten:

```bash
# Service erstellen
kubectl expose deployment nginx-deployment --type=NodePort --port=80

# Service-URL ermitteln
minikube service nginx-deployment --url

# Zugriff testen (ersetzen Sie <URL> durch die ausgegebene URL)
curl <URL>
```

### 5. Zusätzliche Pods für den Dienst im Cluster starten:

```bash
# Auf 3 Replicas skalieren
kubectl scale deployment nginx-deployment --replicas=3

# Pod-Status überprüfen
kubectl get pods
```

### 6. Den Dienst im Cluster rollend aktualisieren:

```bash
# Image aktualisieren
kubectl set image deployment/nginx-deployment nginx=nginx:1.16.1

# Rollout-Status überwachen
kubectl rollout status deployment/nginx-deployment

# Neue Version überprüfen
kubectl describe deployment nginx-deployment

# Optional: Rollback durchführen
kubectl rollout undo deployment/nginx-deployment
```

## Citations:
[1] https://kubernetes.io/docs/concepts/architecture/
[2] https://kubernetes.io/docs/concepts/overview/components/
[3] https://www.qovery.com/blog/what-is-kubernetes-architecture/
[4] https://devopscube.com/kubernetes-architecture-explained/
[5] https://spot.io/resources/kubernetes-architecture/11-core-components-explained/
[6] https://devtron.ai/blog/kubernetes-architecture-the-ultimate-guide/
[7] https://www.aquasec.com/cloud-native-academy/kubernetes-101/kubernetes-architecture/
[8] https://www.vmware.com/topics/kubernetes-architecture
