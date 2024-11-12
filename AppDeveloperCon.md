# AppDeveloperCon hosted by CNCF

## Harnessing Dapr to build High scale messaging at FICO

Event Message Broker Software-Selection

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

