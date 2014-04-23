Rails as an SOA client
---
Pete Hodgson @ph1

## Conway's law
"The commonucations patterns of an information system tend to mimic the communication patterns of the system users"

Fight dependence with fake versions of the services

## Bounded integration tests
Test that the main app is working in isolation

### Fake services

In process - stubs
- vcr
- webmock

Out of process - actual server that speaks HTTP
- mimic, moco, stubby, montebank

## Contract tests
Test other services. 
- rspec, pacto, pact

## Service gateways
Wrap the entry points to a service
- urls
- paths
- connections
- authentication
- caching

## Hexagonal architecture
Pushing the geeky tech details to the borders of the system so we can concentrate on the business logic

You need to translate the responses to domain objects

Some tools:
- hashie - makes working with hashes easier
- lazy_doc
- embedded_doc
- representable

## Caching
Act as a browser

Add caching headers
Add caching middleware in the faraday setup



