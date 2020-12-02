title: Kubernetes
author:
  name: Mohamed Mohideen
output: k8s.html
controls: true

--

# Kubernetes

--

### What is Kubernetes?

Kubernetes (a.k.a. k8s) is an orchestration platform to host dockerized apps. To understand k8s, we need to first understand Docker.

--

### What is Docker?

Docker is a container platform which eleminates the need for running separate VMs for each application by providing isolation for apps within a single VM.

It is a lightweight alternative for VMs.

--

### Why Docker?

Each VM uses additional resources (CPU/Memory) for running the Operating System (OS).

Docker provides a way run multiple apps in a single VM while providing an isolated environment for each app.

--

### Why Kubernetes?

It facilitates:

- creating and managing containers.
- configuring resources such as storage volumes.
- configuring n/w access and firewall for the containers.

--

### How does it work?

K8s is a distributed platform comprised of controller and worker nodes (Linux machines).

Controller nodes oversee the worker nodes, and they serve as a gateway to interact with the cluster.

Worker nodes host the app containers.

--

### What do we gain?

- Version control - promotions will be simpler and easier to rollback.
- Service uptime - auto restart of failed containers, rolling updates for stateless apps.
- Kubernetes provided services - reverse proxy, certificate management.
- Better monitoring support - we can see resource consuption of apps over time.
- Consistent environment for the apps - thanks to Docker.
- Easier migration - OS upgrades, cloud K8s platforms.

--

### Downsides

- Initial learning curve.
- Complex environment - comprised of multiple components.

--

### Running in Production

* ArchivesSpace
* UMD PACT
* Solr Databases
* In Transition
* Caia / Aleph integration

--

### Migrations In Progress

* Hippo CMS and Websites
* MD-SOAR
* Libi Staff Blog
* Fedora
* REDCap
* Workstation Tracking

--

### Migrations In Progress (Continued)
* Data Warehouse databases
* USMAI Confluence database
* Jasperserver Reports database
* AutoNumber
* Student Applications database
* Fedora 2 databases

--

### Upcoming Migrations

* IIIF Services
* DRUM
* Archelon
* Reciprocal Borrowing

--


### To Learn more

#### Confluence links:

- [Kubernetes Notes](https://confluence.umd.edu/display/LIB/Kubernetes+Notes)
- [K8s Cluster Architecture](https://confluence.umd.edu/display/LIB/K8s+Cluster+Architecture)

--

# Questions?