# Basics

<!-- TOC -->
* [Basics](#basics)
  * [Problems k8s solves](#problems-k8s-solves)
  * [High level Idea required in the following areas](#high-level-idea-required-in-the-following-areas)
  * [Master Nodes and Processes](#master-nodes-and-processes)
    * [1- API Server](#1--api-server)
    * [2-  Scheduler](#2--scheduler)
    * [3- Controller](#3--controller)
    * [4- etcd](#4--etcd)
  * [Worker Nodes and Processes](#worker-nodes-and-processes)
    * [1- Container Runtimes (Needs to be installed on every note)](#1--container-runtimes-needs-to-be-installed-on-every-note)
    * [2- Kubelet](#2--kubelet)
    * [3- Kube proxy](#3--kube-proxy)
  * [Requisites for a simple cluster](#requisites-for-a-simple-cluster)
<!-- TOC -->

## Problems k8s solves

* High availability 
* Scalability - scale up and down containers
* Disaster Recovery - backup and restore

## High level Idea required in the following areas

* Pod
* Service
* Ingress
* Config Maps
* Secrets
* Volumes
* Deployment
* StatefulSet
* Replicas
* DaemonSets
* Kube proxy

##  Master Nodes and Processes

### 1- API Server
* Allows for client to interact with k8s cluster
* Gatekeeper for authentication
* Cluster Gateway

### 2-  Scheduler

* Allows for scheduling a pod on a worker node based on resources
* Client - > Issues Request - > Api Server - > Delegates to -> Scheduler -> Decides which node to place the pod -> Delegates to Kubelet

### 3- Controller

* Detect state changes of k8s objects and attempts a recovery
* Controller Manager -> Scheduler -> Decides which node to place the pod -> Delegates to Kubelet

### 4- etcd

* Key-Value Distributed Store
* Maintains all state changes of k8s objects
* Maintains resources available on each node


##  Worker Nodes and Processes

### 1- Container Runtimes (Needs to be installed on every note)
  * containerd
  * docker
  * cri-o

### 2- Kubelet

* Interacts with both container and node
* Starts the pod with a container inside

### 3- Kube proxy

* Services to pod communication
* Ensures low overhead communication

##  Requisites for a simple cluster

* 2 Control Plane Nodes
* 3 Worker Nodes
* Master Nodes consume less CPU, RAM, Storage compared to worker nodes.


---

##  TLS Certificates