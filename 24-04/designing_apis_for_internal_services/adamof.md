Designing the APIs for an internal set of services
---
Alberto Leal

### What is an API?
- the interface

Services:
- services allow to evolve different parts of app independently
- services allow us to use the right tool for the job
- makes replacement of services easy

How do we:
- define services contract
- how do we manage deployments
- how do we test this

The process:
- API modelling
- - involves all the stakeholders to create the conceptual model and purpose
- - understand the audience - DEVELOPERS
- - we have to see the developer as our customer and the API as the product
- - develop ubiquitous language
- - do not reinvent the wheel, use existing formats (json, etc)

#### What makes a great API?
- flexible and simple to use
- - /cars?fields=name,model,year
- uses *nouns* instead of *verbs*
- uses the HTTP verbs to perform actions
- returns meaningful errors
- - because the API is a black box to the devs
- - use http status codes and include error messages in body
- - 400 401 403 404 500
- provide great support
- - documentation 
- - communication
- - community
- secure
- - ssl?

#### What about versioning
Support at least 1 version backwards
Use headers to indicate the version

#### Contracts
Contracts can couple service providers and customers

Consumer-driven contracts
/martin fowler/

### Deployments

### Tests









