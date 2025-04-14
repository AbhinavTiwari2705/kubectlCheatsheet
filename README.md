# Kubernetes (kubectl) Commands Cheat Sheet

## 1. `kubectl get`
- **Usage**: `kubectl get <resource>`
- **Explanation**: Retrieves information about resources in the cluster (like Pods, Services, Deployments).
- **Examples**: 
  - `kubectl get pods` — List all pods in the current namespace.
  - `kubectl get services` — List all services.

## 2. `kubectl describe`
- **Usage**: `kubectl describe <resource> <name>`
- **Explanation**: Provides detailed information about a specific resource (like Pod, Node, Deployment).
- **Examples**:
  - `kubectl describe pod <pod-name>` — Show detailed information about a pod.
  - `kubectl describe deployment <deployment-name>` — Show detailed info about a deployment.

## 3. `kubectl create`
- **Usage**: `kubectl create -f <filename>`
- **Explanation**: Creates resources in the cluster from a YAML or JSON file.
- **Examples**:
  - `kubectl create -f deployment.yaml` — Create a deployment from a YAML file.

## 4. `kubectl apply`
- **Usage**: `kubectl apply -f <filename>`
- **Explanation**: Applies changes to the cluster, either creating or updating resources. Preferred method for managing resources.
- **Examples**:
  - `kubectl apply -f deployment.yaml` — Create or update a deployment from a YAML file.

## 5. `kubectl delete`
- **Usage**: `kubectl delete <resource> <name>`
- **Explanation**: Deletes resources from the cluster.
- **Examples**:
  - `kubectl delete pod <pod-name>` — Delete a specific pod.
  - `kubectl delete -f deployment.yaml` — Delete resources specified in the YAML file.

## 6. `kubectl logs`
- **Usage**: `kubectl logs <pod-name>`
- **Explanation**: Retrieves the logs of a container in a pod.
- **Examples**:
  - `kubectl logs <pod-name>` — Show logs from a specific pod.
  - `kubectl logs <pod-name> -c <container-name>` — Show logs from a specific container in the pod.

## 7. `kubectl exec`
- **Usage**: `kubectl exec -it <pod-name> -- <command>`
- **Explanation**: Executes a command in a running container within a pod.
- **Examples**:
  - `kubectl exec -it <pod-name> -- /bin/bash` — Open a bash shell inside the pod.
  - `kubectl exec -it <pod-name> -- ls` — Run `ls` inside the pod.

## 8. `kubectl scale`
- **Usage**: `kubectl scale <resource> <name> --replicas=<count>`
- **Explanation**: Scales a resource (like a deployment or replica set) to the desired number of replicas.
- **Examples**:
  - `kubectl scale deployment <deployment-name> --replicas=3` — Scale a deployment to 3 replicas.

## 9. `kubectl port-forward`
- **Usage**: `kubectl port-forward <pod-name> <local-port>:<pod-port>`
- **Explanation**: Forwards a local port to a port on a pod, allowing access to the pod from your local machine.
- **Examples**:
  - `kubectl port-forward pod/<pod-name> 8080:80` — Forward port 8080 to 80 on the pod.

## 10. `kubectl get nodes`
- **Usage**: `kubectl get nodes`
- **Explanation**: Lists all nodes in the Kubernetes cluster.
- **Examples**:
  - `kubectl get nodes` — Show the list of nodes in the cluster.

## 11. `kubectl top`
- **Usage**: `kubectl top <resource>`
- **Explanation**: Displays resource usage (CPU, Memory) for a given resource.
- **Examples**:
  - `kubectl top pods` — Show CPU and memory usage for all pods.
  - `kubectl top nodes` — Show CPU and memory usage for all nodes.

## 12. `kubectl config`
- **Usage**: `kubectl config <command>`
- **Explanation**: Manages your Kubernetes configuration files (like contexts, clusters, etc.).
- **Examples**:
  - `kubectl config use-context <context-name>` — Switch to a different context.
  - `kubectl config view` — Display the current Kubernetes configuration.

## 13. `kubectl rollout`
- **Usage**: `kubectl rollout <command> <resource>`
- **Explanation**: Manages the rollout of resources, such as deployments.
- **Examples**:
  - `kubectl rollout status deployment <deployment-name>` — Display rollout status.
  - `kubectl rollout undo deployment <deployment-name>` — Roll back to the previous deployment version.

## 14. `kubectl drain`
- **Usage**: `kubectl drain <node-name>`
- **Explanation**: Prepares a node for maintenance by evicting pods.
- **Examples**:
  - `kubectl drain <node-name>` — Evict all pods from a node in the cluster.

## 15. `kubectl cordon`
- **Usage**: `kubectl cordon <node-name>`
- **Explanation**: Marks a node as unschedulable (no new pods will be scheduled on it).
- **Examples**:
  - `kubectl cordon <node-name>` — Marks a node as unschedulable.

## 16. `kubectl uncordon`
- **Usage**: `kubectl uncordon <node-name>`
- **Explanation**: Marks a node as schedulable again (new pods can be scheduled).
- **Examples**:
  - `kubectl uncordon <node-name>` — Marks the node as schedulable again.

## 17. `kubectl get events`
- **Usage**: `kubectl get events`
- **Explanation**: Lists events that have occurred in the cluster.
- **Examples**:
  - `kubectl get events` — Show a list of recent events in the cluster.

## 18. `kubectl apply -k`
- **Usage**: `kubectl apply -k <directory>`
- **Explanation**: Applies Kubernetes resources from a directory containing `kustomization.yaml`.
- **Examples**:
  - `kubectl apply -k ./manifests` — Apply Kubernetes resources from a directory.

## 19. `kubectl cp`
- **Usage**: `kubectl cp <pod-name>:<path-in-pod> <local-path>`
- **Explanation**: Copies files between a pod and your local machine.
- **Examples**:
  - `kubectl cp <pod-name>:/etc/config/config-file.yaml ./` — Copy a file from a pod to the local machine.

## 20. `kubectl version`
- **Usage**: `kubectl version`
- **Explanation**: Displays the client and server versions of Kubernetes.
- **Examples**:
  - `kubectl version` — Show the client and server versions of Kubernetes.

## 21. `kubectl auth can-i`
- **Usage**: `kubectl auth can-i <verb> <resource>`
- **Explanation**: Checks whether a user can perform a specific action (verb) on a resource.
- **Examples**:
  - `kubectl auth can-i get pods` — Checks if the user can list pods.

