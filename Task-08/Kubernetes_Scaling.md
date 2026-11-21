# Kubernetes Scaling

## Aim
To deploy the university result portal in a local Kubernetes cluster with three replicas, demonstrate automatic pod recovery and scale the application to six replicas.

## Software Required
- Docker
- Minikube
- kubectl
- Result Portal Docker image

## Procedure

### Step 1: Start Minikube

```bash
minikube start
```

### Step 2: Load the Docker Image

```bash
minikube image load result-portal:latest
```

### Step 3: Apply the Kubernetes Deployment

```bash
kubectl apply -f deployment.yaml
```

### Step 4: Check the Deployment and Pods

```bash
kubectl get deployments
kubectl get pods
```

The deployment should create three replicas of the result portal.

### Step 5: Access the Application

```bash
minikube service result-portal
```

### Step 6: Test Automatic Pod Recovery

Check the pod names:

```bash
kubectl get pods
```

Delete one pod using its actual name:

```bash
kubectl delete pod <pod-name>
```

Watch the pods:

```bash
kubectl get pods -w
```

Kubernetes automatically creates a replacement pod to maintain the required replica count.

### Step 7: Scale to Six Replicas

```bash
kubectl scale deployment result-portal --replicas=6
kubectl get pods
```

The deployment should now maintain six replicas.

### Step 8: Verify Resource Requests and Limits

```bash
kubectl describe pod <pod-name>
```

Check the CPU and memory requests and limits in the output.

## Expected Output
- Three result portal pods are created.
- A deleted pod is automatically replaced.
- The deployment scales to six replicas.
- Resource requests and limits are displayed.

## Result
The result portal is deployed in a local Kubernetes cluster. Automatic pod recovery and scaling from three to six replicas are demonstrated.
