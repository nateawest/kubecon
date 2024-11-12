# AppDeveloperCon hosted by CNCF

## Harnessing Dapr to build High scale messaging at FICO

Event Message Broker Software-Selection

apache pulsar (we use rabbitMQ)

pub/sub: publish/subscribe API, is a messaging service that allows services to communicate asynchronously by sending and receiving messages.

Principals
* API-First
  * granular api  
  * pub/sub api
* Seperation of Concerns
* Abstraction and Isolation
* Declartive Model

They were tied heavly to kafka and switching to appache pulsar would be major surgery. They also wanted to prevent getting too tied to a new service
* Abstraction layer DAPR - distributed application runtime
  * can build in any language
  * building blocks
    *  secrete management
    *  pub/sub
  * uses kubernetes side car
    * None of the feature request required changes to the application facing Dapr APi
    * Changes were able to be made in the side cars
  * can reconfig dapr and restart pod and your up and running. DOn't have to rebuild and docker image ect

 DAPR sidecar was not a net CPU/Memory addition
 DAPR can be throttled 

 FICO - decompose buisness capabilities, Interconect services using event-driven architecture supported by event server.


## Tales from the crypt application packing and delivery nightmares

Helm package manager for kubernetes for managing yaml

Before - 1 million YAML files and 1 underpaid engineer
After - 1 config and 1 underpaid engineer

Helm - uses GO template place holders

Problem - try to accomodate every use case that everyone has. Every possible case is templated. More template than yaml
Can lead to sphagetti code 

porter - packaing tool and bundles it into an OCI artifact
porter - like a pokedex to keep track of devops tools (pokemon)

Great things
* deploy and config applications on k8s in battle tested ways
* learning how to use k8s
Not Great
* general purpose templating
* abstracting all their workflows in cleaver but impossible to understand

tips to avoid production weirdness
* porter - know the state of your world beofre you optimize it
* explore the ecosystem for the right tool to fit you environment

## 12 factor app presenatation by HEROKU
best practices around creating applications where you dont have to worry about where your app is running
You dont have to worry about all of the things a platform engineer has to worry about

Technology has evolved (microsevices, orchestration)
Telemtry best practices

## Minder
A platform that helps teams build secure software

Synchronous system: make a request, get a repli
Care about getting an answer
request completes before proceding
OPENAPI, gRPC, GraphQL

asynchronous
one message can be routed to mujltiple recipients
dont have to block until work is done

original sender cant eassily get results
error detection and handling -- need retries and dead letter queues

asynchronous might not have a defiend ending "done"

Watermill
standardize eventing for just GO Lang

## Event discovery kubernetes
Knative eventing
Source - takes a event from third party and wraps it into a cloud event
* way to get events into the system/event-mesh
* serivce in the system, which emits events

how to events from third party system into your event system

brokers and triggers
* broker discover end point
* trigger responsible for event delivery

sink
* a way to get events out of the system /event-mesh
* service in the system, which accepts events

WHy do you want event discovery
* what are the available events that I can consume
* what about the internal systems and services

Trial and error is the only solution today

EventType API
* reference to the emiting resource
* attribute of the emitted event

How are EventTYpe catalogs populated
* Manual Registration
* Automatic Registraction (via brokers)


# DAPR

Abstraction

DAPR shines in these 6 ways
* Disparate environmnents (swap them out)
* Scalability (plugable)
* Resiliency (language agnostic) resiliency policies gracefrully retry serivces
* Interoperability (write some actos in JAVA in one serivce and C# in another)
* Security
* Flexibility (application level can deploy in many different environmnents for ex Azure or AWS)

Dapr actors - 

## Open Telemetry

Ebay
*
Air bnb
* Showed reduction in resources. Consolitdate libraries. Can used open source side cars and collectors because OTel is open source
GitHUb
* heavy uses of feature flags and short roll outs. Moved from open tracing to Open Telemetry

OTel - putting a link to the trace in the header so that customers can see
Can embed weird things in trace like DataBase Guide into db related traces

# Authorization

Problems:
* Bad Security
* Inconsistency
* Opportunity Cost

Broken access control Number one problem of authorization

Old SChool Autothorization
* What: Coarse-grained, tenant-level permissions
* HOw: Authorization spaghetti logic
* When: Permissions evaluated at login

Cloud-Native
* Fine-Grained: Resource level
* POlicy based: AUthorization logic extracted out of the application
* Real-TIme: Riught before you grant acccess

Two groups in the current landscape

Policy as code (ABAC)
* Open POlicy Agent

The other thought
* forgot to write it down

## Streamlining cloud native development. MicRock

Fake it with an services sandbox
Diversity of stacks, of middlewares, and apis make it difficult to setup and test on laptop

Library Testcontainers
Unit test with real dependencies

## Fake it until make it

gRPC API

Unit Test _ issues wrt
* code is fragile
* Test depend on more API details than functional reality
* cry wolf effect when code is rewritten
* unreliable for TDD
* Written after the functional code
* Encouragecs creation of replica tests pruely for coverage

Solutions
* Functional tests - memory/disk (fake env)
* Dummy objects
* Mocks
* Spies: partial mocks
* Stubs
* Fakes

The pyramid of Testing
* Manual test
* E2E tests                        Full System deployments
* Ingeration tests                 Fake Tests
* COmponent tests
* Unit Test

The ISSUES of relying on unit and E2E test for functional code testing
The solution of a fake test framework for functional testing, TDD and code refactor
Demo of such a framework
Running your tests data issues, functional testing against a range of env types
