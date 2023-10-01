# Basic Kubernetes Commands

Kubernetes is a powerful container orchestration platform. Here are some fundamental commands to help you manage your Kubernetes clusters.

## Check Cluster Information

To view the details of your Kubernetes cluster, including the current context, you can use:

```bash
kubectl cluster-info
```

## View Nodes in the Cluster

To list all the nodes in your Kubernetes cluster, use the following command:

```bash
kubectl get nodes
```

## View Pods

To list all pods in the default namespace, you can use:

```bash
kubectl get pods
```
You can specify a different namespace by adding -n <namespace> to the command.

## Describe a Pod

To get detailed information about a specific pod, including its status, events, and containers, use:

```bash
kubectl describe pod <pod-name>
```

## View Services
To list all services in the default namespace, you can use:

```bash
kubectl get services
```

## List Deployments

To list all Deployments in your Kubernetes cluster, you can use the following kubectl command:

```bash
kubectl get deployments
```

## Scale Deployments

To scale the number of replicas for a deployment, use:

```bash
kubectl scale deployment <deployment-name> --replicas=<desired-replica-count>
```

## Delete Resources

kubectl delete pod <pod-name>

```bash
kubectl delete pod <pod-name>
```

**Check ReplicaSet**
```bash
kubectl get replicaset
kubectl get replicaset <replicaset name>
```

**Check container used in replicaset**
```bash
kubectl describe replicaset
```

**Scale existing replicaset**
```bash
kubectl scale rs <name> --replicas=5
```
**Edit existing replicaset**
```bash
kubectl edit replicaset <name>
```

**kubectl apply**
- This command is used to create or update resources by applying a configuration file. If the resource already exists, apply updates the resource with the new configuration.

```bash
kubectl apply -f <yaml file path>
```

**kubectl create**
- create is used to create a new resource by specifying the resource definition in the command itself.
```bash
kubectl create -f <yaml file path>
```