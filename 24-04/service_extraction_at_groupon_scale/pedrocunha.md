Service Extraction at Groupon Scale
====

Monolith is not necessarily bad thing

Before
- 1 app
- 1 test suite

2009 - 2y old - 3K RPM

8 months later - 30k RPM


Oprah was killing groupon


commits per month
- Jan 2009 ~ 600
- Jan 2011 ~ 2200

Casual coupling
- preventing the SOA

code growth - LOC
- 0.5M - 2009
- 2M   - 2011

45 minutes test suite

deploy was 3h

Order logic to a service
- contention on the db
- the service has read-only access the monolithic 
- has its own db
- the main web app repo, has the orders service on `app/services/order`

disable / deprecrate models
- raise violations quickly
- detect uses on codebase
- detect interactions
- build a wall in the controller
  - disabled_model_access "services/orders", :excepts => [...]

lots of cruft remains
- is this endpoint even used ?

route 66 
- track dead routes

new service, old schema
- pros: minimal changes aid fast extarction, speedy endpoint roll-out time
- cons: still tied to legacy db schema, lots of cruft remains in the code

greenfield + messaging (bus)
- preserve a legacy API while making devs happy
- pros: eradicate legacy more quickly; minimize cutover w/phased rollouts; 
own endpoint roll-out timing;
- cons: synchronization build not trivial; validation layer even less trivial;
managing race conditions;

facade as a service
- centralize ownership and hide complexity
- pros: easy to incorporate different data sources; hides complexity
of multiple systems;
- cons: accessors bound to schema changes reliance on old
schemas is a crutch;

things we learned
- have a strategy: you need to know priorities; you need to know
what you gonna leave on the monolith
- envision the whole stack: consider ops requirements; SLAs, caching
data flow
- messaging is critical: understand delivery; payloads and format
- authentication + authorization: know your users and know what they
do
- support env: spend time on tooling and release tactics
- consider UUIDs - be careful with row ID integration
- models inform APIs: consider them a sketch of service endpoints
- avoid tangled parts: has_many problems
- test at high levels: more end-to-end, less unit
