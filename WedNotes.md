# Protecting your GitOps System

Identify A Trend -> Study GitOPs -> Exploit -> security vs reality --> wrap up

Identify a trend
* lots of ppl use argocd

What is GitOPs
* Git as a Source of Truth
* Versioning
* Current State == Desired State

IaC & CaC --> Git <-- GitOps Agent (Argo CD) --> Cloud Env (k8's CLuster)

Attack perspective
GitOps Agent --> Cloud Env

GitOPs Agent is appealing to attackers bc it has access to cloud env where secrets are

Attacking Argo CD
Exploit
* Connect a Git Repository with all deployments and latest stuff
* Cluste3r up and running. Plug and play process

Behind the Scenes
How Argo CD WOrks
* Current state in gitrepo synched with current state in kube cluster
* Redis Cache Server middleware between the repo and cluster

Secretes are available to anyone who has access to the Redis instance
Attacker: what if we could inject a melicious deployment straight into redis cache
* tried to inject
* but the repository service was notified and checked to seee if the changes were up to date

Cache Entry Hash
Notes in argo source code says that its just used for checking data corruption

was able to inject into redis cache and get a privlleged connection
* this gave attacker access to all pods
* Steals kubernetes secretes
* The attacker could sniff and intercept Pods networking
* Could steal IAM Role

Vulerability reported to Argo CD and the vulerability was covered
redis instance in a argo cd server
Found 1 aplpication manifest
made the cache

GitOps Security vs. Reality
* cluster seperation
  * Single cluster attacker gets everything in that cluster
  * Gets priveledged access to the gitops agfent and access to entire cluster
* Seperate clusters
  * POD compromised but this time it fails because they have seperate agents
* Network POlicies
  * In argo cd network policies are default
  * but are they enforced by default?
* Version Update
  * How much argo cd are patched in the wild. 2/3rds of public exposed are vunreble 6 months later

Wrapup
GitOps Security Champion
Best practices


