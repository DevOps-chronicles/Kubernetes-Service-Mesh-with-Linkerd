# Kubernetes-Service-Mesh-with-Linkerd
A project to demonstrate the implementation of a service mesh using Linkerd on a Kubernetes cluster. The service mesh provides features such as traffic management, service discovery, load balancing, and security for microservices applications

## Prerequisites
- A Kubernetes cluster (version 1.17 or later)
- kubectl command-line tool installed
- Linkerd CLI tool installed

## Steps
### 1. Install Linkerd on the Kubernetes cluster
Use the Linkerd CLI tool to install Linkerd on the Kubernetes cluster. This will deploy the Linkerd control plane components and the Linkerd data plane proxies. `linkerd install | kubectl apply -f -`

### 2. Deploy the Linkerd control plane components
Deploy the Linkerd control plane components such as the web UI, the destination, and the Prometheus-compatible metrics server.  `linkerd control-plane install | kubectl apply -f -`

### 3. Deploy the Linkerd data plane proxies
Deploy the Linkerd data plane proxies, also known as "linkerd-proxy", as a sidecar to each service in the application. `linkerd inject -f path/to/your/manifest.yaml | kubectl apply -f -`

### 4. Configure the service mesh
Use the Linkerd CLI tool to set up traffic management rules, service discovery, and security policies for the service mesh. `linkerd configure --router-replicas=3`

### 5. Monitor the service mesh
Use the Linkerd web UI to monitor the service mesh and gain visibility into service traffic. `linkerd dashboard`


### 6. Scale and update the service mesh
As your application grows and evolves, use the Linkerd CLI tool to scale and update the service mesh as needed. `linkerd upgrade`


## Technical terms used
* Kubernetes: an open-source container orchestration system for automating the deployment, scaling, and management of containerized applications.
* Service mesh: a configurable infrastructure layer for microservices application that makes communication flexible, reliable, and fast, providing features such as traffic management, service discovery, load balancing, and security.
* Linkerd: an open-source service mesh for Kubernetes that provides features such as traffic management, service discovery, load balancing, and security.
Control plane: the control plane components in a service mesh are responsible for managing the configuration of the data plane proxies.
Data plane: the data plane proxies in a service mesh are responsible for enforcing the configuration set by the control plane, and handling the actual traffic between services.
Sidecar: a sidecar container is a separate container that runs alongside the main container in a pod, and provides additional functionality such as traffic management, service discovery, and security.
Prometheus: An open-source systems monitoring and alerting toolkit.
Metrics server: A monitoring solution which provides metrics about the resource usage of pods and nodes.
Web UI: A web-based user interface that allows you to interact with a system.
CLI tool: A command-line interface (CLI) tool is a type of software that allows users to interact with a computer or network by typing commands.
Replicas: Replicas are multiple copies of a pod, service or
