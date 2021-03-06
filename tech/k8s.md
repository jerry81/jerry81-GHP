[Go Home](../index.md)

## Kubectl Reference

kubectl create -f 
creates file (json or yaml)

kubectl config view 
shows users: - "name", clusters, contexts

logs -f <pod id> 
  streams logs from pod to terminal
  
run 
  spawns new container 

exec <pod id> -it -- bash 
  (why an orphaned --)? 
interactive shell in pod

example kubectl exec frame-recommendation-6cb557b789-bgb8x -it -- bash

kubectl describe node <node name> 
gives node status details 
  addresses
  condition
  
 get events - shows a history of recent events, object that was worked on, type of msg, and action/reason
 
kubectl create deployment hello-node --image=k8s.gcr.io/echoserver:1.4 - creates a deployment pod, with name hello-node from a docker image

## Kubernetes Secrets
place to store and manage sensitive info such as passwords or tokens 

to create secret, first have the secret in a file.

echo -n 'admin' > ./username.txt
echo -n '1f2d1e2e67df' > ./password.txt

## Controllers

daemonset - one pod per node, used to monitor each node 

deployment: declarative updates for pods and replicasets 

stateful set - used for persistent storage and network identifiers 

replicaSet - set of identical pods 

job - like cronjob but runs only once 

## Logging 

"kubectl logs" is actually getting the collected logs from std.out and std.error that are stored in memory (not file) as a buffer.
This buffer can then be read by datadog

## Vocabulary

pod - smallest deployable unit 

service - logical set of pods 

fungible - mutually interchangable 

volume (docker also has them) - a directory or disk on a container 
configMap is a type of volume - way to inject a config into a pod 
also lots of plugins to other storage services

namespace - way to divide cluster resources between users 

node - working machine/vm

PLEG - pod lifecycle event generator - automatically starts and restarts containers to reach a "desired state"

kubelet - non-master process that communicates with master 

apiserver - part of the master process 

kube-proxy - non-master process that handles networking on the node 

## Nodes 

nodes not a kubernetes construct, but rather of the cloud provider 
kubertnetes creates an object that represents the node 

## apiserver aka master 

listens at port 443
should require authorization 

2 ways to communicate with clusters:  
to kubelet 
to node, pod, or service through proxy 

second way not secure 

## kind

run k8s on local computer 
requires docker 

## minikube

like kind, run k8s locally

also requires docker or other VM manager like VMWare or VirtualBox

### getting started:

1.  brew minikube
2.  minikube start

## kubeadm

create and manage k8s clusters
