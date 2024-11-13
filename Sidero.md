## Sidero Workshop

Sidero and Portainer Masterclass
Kubecon Nov 2024

Portainer - web gui to see status of containers

From Bare Metal to Gitops
Agenda
* OVerview of the architecture
* Demo flow
  * Talos k8 provisioning with Portainer
  * Secure the cluster
  * User Management
  * Namespace creation
  * Deployment with GitOps
  * Scaling the cluster via Portainer
  * Portainer API Server proxy

Portainer: Excel in helping you deploy. Started as a GUI for Docker

Talos: Get rid of the operating systems. Humans don't touch it.
* Extremely limited OS exclusively made to run kube
* written in GO
* put an api in it

OMNI: management system specificaly made to manage Talos Node
Running SaaS

If you run Talos with Mmni you have to make changes using the configuration file with the cli
Omni generates that under the hood, incrpyts it and stores it in their database
If you make changes to Omni it will uopdate Talos

Talos configuration determines worker or control plain node
You state within the type peram I want this to be a worker

Portainer manages the cluser using the omni api
opa gateway

Portainer
* Can Setup Pod constraints
* Can Manage roles
* Can Setup Namespace
* Can have all your configuration in a git repository and can connect with portainer
* Can do gitops. If it checks repo and there are changes it can pull them via portainer

Deployment with gitops
* enable gitops with portainer
* allows you to store git credentials with token and user name
* if you try to deploy something that isn't in your namespace it'll reject
* Portainer has to reference a branch name and apparently tag
* Blue Green

Could have it deploy to a Dev branch and when satisfied have a Production branch and deploy to Production

Upgrade the kube version via portainer

omni/talos
upgrades will go through each nove that its going to upgrade. It'll go through the order recommended by the documentation. It'll go through and patch using the api's. It'll then do the kubettes one by one. ect.. I think

portainer can be used as a proxy api server and you can edit via vs code

60 day trial for portainer and OMni SaaS


