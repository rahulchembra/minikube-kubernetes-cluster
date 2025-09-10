# Kubernetes Local Cluster with Minikube

## Objective
This project demonstrates how to deploy and manage applications in a local Kubernetes cluster using Minikube, kubectl, and Docker. It covers fundamental Kubernetes concepts such as deployments, services, scaling, and debugging workloads in a local development environment.

## Tools
- Minikube – Local Kubernetes cluster  
- kubectl – Kubernetes CLI for cluster management  
- Docker – Container runtime for pods  

## Project Steps
1. **Start Minikube**
   minikube start --driver=docker
   - Starts a local Kubernetes cluster on your system.

2. **Create Deployment**
   - Create a deployment.yaml file defining your app (e.g, Nginx).  
   - Apply the deployment:
   kubectl apply -f deployment.yaml

3. **Expose Deployment as Service**
   - Create a service.yaml file to expose the deployment:
   kubectl apply -f service.yaml

4. **Verify Pods and Services**
   kubectl get pods
   kubectl get svc
   kubectl get pods --show-labels

5. **Access Application**
   minikube service <service-name>
   - Opens the deployed app in the browser.

6. **Scale Deployment**
   kubectl scale deployment <deployment-name> --replicas=3
   - Adds more pods to handle increased load.

7. **Check Pod Logs and Description**
   kubectl logs <pod-name>
   kubectl describe pod <pod-name>

## Project Structure
```
kubernetes_project/
│
├── deployment.yaml          # Deployment manifest for the app
├── service.yaml             # Service manifest to expose the app
├── README.md                # Project documentation
└── screenshots/
    ├── kubectl_get_pods.png        # Output of `kubectl get pods`
    ├── kubectl_get_svc.png         # Output of `kubectl get svc`
    ├── app_running_browser.png     # App running in browser
    └── app_running.png             # App running in terminal
 ```                 

## Project Deliverables
1. YAML Files
   - deployment.yaml  
   - service.yaml

2. Screenshots
   - Pods running in cluster (kubectl_get_pods.png)  
   - Services running (kubectl_get_svc.png)  
   - App running in browser (app_running_browser.png)  
   - App running in terminal (app_running.png)             

## Outcome
- Local Kubernetes cluster running successfully  
- Application deployed and exposed via NodePort  
- Pods can be scaled and managed using kubectl commands  
- Hands-on experience with deployments, services, scaling, and debugging in Kubernetes  

## Notes
- Ensure Docker is running before starting Minikube.  
- Use minikube stop to stop the cluster when not in use.  
- Use minikube delete to remove the cluster completely.
