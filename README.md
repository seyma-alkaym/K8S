# Kubernetes Deployment Guide

This guide explains the steps taken to create and deploy a website using DockerHub and Kubernetes. The YAML files for creating deployments, ReplicaSets, and Pods, as well as the services associated with them, are included in this repository.

## Creating Objects and Services

To create the desired object and its associated service, run the following command:

```bash
kubectl apply -f <fileName>
```

Replace `<fileName>` with the name of the YAML file for the specific object you want to create. This command will create the object (Pod, ReplicaSet, or Deployment) and its associated service as defined in the YAML file.

### Create a Pod from a DockerHub Image

   - Use the YAML file [`pod.yaml`](/pod.yaml) to create a Pod from the DockerHub image and publish it.

```bash
kubectl apply -f pod.yaml
```

If we open the IP address of the node and open port `30005`, the page will appear as shown in the image below:

![pod](/secreenshots/guncel-pod-publish.PNG)


### Create and Publish a ReplicaSet

   - Use the YAML file [`replicaset.yaml`](/replicaset.yaml) to create a ReplicaSet with 4 replicas and publish it.
     
```bash
kubectl apply -f replicaset.yaml
```

If we open the IP address of the node and open port `30006`, the page will appear as shown in the image below:

![replicaset](/secreenshots/replica-guncel-publish.PNG)

### Create and Publish a Deployment

   - Use the YAML file [`deployment.yaml`](/deployment.yaml) to create a Deployment with 4 replicas and publish it.
     
```bash
kubectl apply -f deployment.yaml
```

If we open the IP address of the node and open port `30007`, the page will appear as shown in the image below:

![deployment](/secreenshots/deployment-guncel-publish.PNG)


## Verify Objects and Services

Ensure the object is running with the desired number of replicas.

```bash
kubectl get pods  #pod
```

```bash
kubectl get rs  #replica set
```

```bash
kubectl get deployments  #deployment
```

Check the services running in Kubernetes using the command
```bash
kubectl get services
```

 or 
 
 ```bash
 kubectl get svc
```

![pod+service](/secreenshots/pods+services.PNG)  
