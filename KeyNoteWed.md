# Keynote 11/13 Wednesday

Kueue
MultiKueue
* Helps jobs find a home

local kueue workflow
Kueue created workload and found a onprime cluster to do the job

mult kueue workflow
kueue found a job in germany to do the job
found a remote cluster

# SUSE Open Source-Powered Cloud Native

Open source conversation. How open source can be secure in enterprise.
Open source expanded invoation to the CLoud, Edge, and Ai

Kubernetes announced June 2014 and repaidly got accepted 
No proprity counterpart

why did it when
* open source
* community

open source is defining the standards of ai. Kubernettes is a great platform to deploy ai on

kubernettes runs in satellites even though its only 10 years old

SUSE
* commited to open source projects
* protect open source thos

# Adobe speaker/CoreweAVE SPEAKERS

Ai workloads on kubernetes discussion
* performance, how long it takes to train a new model as quickly as possible using latest technology
* ANy change in any layer in stack can affect performance
* ANything goes wrong can have determinetal impact on cluster

Looking under the hood of a kubernetes training cluster
* need greater observability into whats going on in the cluster

Anatomy of a kubernetes training cluster
* control plant and mgmmt
* lifecycel monitoring
* fleet management

2023
From one ultra-performant cluster
2024
to many

achieved relentless focus on automation

how
* kubernetes as a single source of truth
* automated node life cycle
* continuous health checking and auto-healing

Bare Metal Nodes
* metadata
* bootstrapping info

Node lifecycle
* define a node with baremetal node
* boot
* validation
* firmware provisioning
  * latest version for gpu, cpu ect
* burn-in test
* node code control takes over. POpulate metadata
* run health checks active and passive
  * if fails node control removes the node and places it in a triage env state for investigation

 Observability - single pane of glass
 * monitor and diagnose
   * gpu fell off bus error example
* monitor pci metrics
* monitor node temperature

prometheus
* can look at entire fleet of gpus and can slice and dice metrics like temperature, location
  * can look at trends and find problems before and remove node

 Key takeaways
 * failures are ineveitable shouldn't focus on prevent but how to manage and swiftly handle
 * automation is key
 * effcient fleet management

booth s32

# oracle cloud development speaker

how oracle is using open source tech to build cloud infrastructure and ai

oracle developers
* know for oracle db but developers have a choice to other tech
* Operations chatbot
  * provde operators with some data to help the customers
  * provides some context
  * analyze recent errors to help customer
  * customer logs, faq's, conversations with operator

there cloud services was built using open source

# Lunar

Principals of platform engineering

Core principals
* self-service experience
* exploicit and consistent APIs
* Paved Paths/GOlden Paths
* MOdularity
* platform as a product
* core requirements

Be pragmatic, start small, scale up

At lunar 60% + of text communication with customers in now handled with AI without human intervention
93% reduction in resoltuion time
13%  of full time staff

# Intel Speaker

linux foundations open platform

Open platofmr for enterprise AI

AI.... AI.... AI....

# NIVIDIA\

AI.... AI.... AI....

# Capital 1 speaker

AI.... AI.... AI....

GEN AI
