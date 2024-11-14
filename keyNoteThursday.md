# KeyNote Thursday 11/14


Windows Exporter Alert
image from: http://pr-ptproc-p11.tps.local:9182/metrics
![Screenshot 2024-11-14 100034](https://github.com/user-attachments/assets/8b3987bd-a46d-4156-b7a4-5427df716187)
COpilot breakdown: 
It looks like you’re referring to a metric from a monitoring system, possibly Prometheus. The metric {collector="net"} 0 suggests that the net collector has a value of 0. 
This could indicate that there is no network activity or that the network collector is not reporting any data at the moment.

CNCF Technology Landscape Radar

# Kube Network Security

Ingress Gateway
service to service: service mesh
side car infrastructure

great for l4 traffic

l7 traffic all require a gateway. Don't need a sidecar need to be able to dynamically provision individual mciro gateways

ambient mesh
Fast, Secure, and Simple: Istio's ambient mesh mode
ambientmesh.io

Envoy proxy: defacto standard or data plane proxies
Gloo open source project: kubernettes native control plane and dec larative API to program envoy proxy as the data plane.;

k8s Gateway is an envoy-powered API gateweay

# cloudnative next decade steady, secure, and ready for distrucption...?

Next Decade
* security problems
* Get Ahead of the Hype
* SBOM: software bill of materials
* GUAC: helps u store, analyze and vizualize data
  * links your artifacts in a graph. creates a dependacy tree
  * query: vulnerable packages, SLSA proveanance documents, bad actors
* answer crucial questions: is a dependancy I'm using leaking my data

# Securing your software supply chain

MIcrosoft

Observability and Integrity

Aquire --> Catalog --> Build --> Deploy --> Run

Observability into software supply chain
OpenTelemetry observe CI CD PIpelines and bring observability to the left

Guac dependancy graphs

# Redhat: Open Source Pushing boundaries

podman
* pod manager
* smallest deployment unit in kubernettes
* podman desktop is an open source graphical tool enabling seemlessly work with containers

bootc
* boot container
* build using standard container tools and eployu and upgrade in place with Bootsy

podman builds an os image and pushes the image to the same oci container
then your ci cd pipeline can scan for vulnerabilites

12:30 free signed copies of podman in action

# professor session. NYU and Purdue

Open source security is not a spectator sport











