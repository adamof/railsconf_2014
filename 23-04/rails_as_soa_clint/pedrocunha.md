Rails as an SOA client
====
Pete Hodgson

Act I - Co-depedence and independence

"Conway's Law"

System architecture affects how people work together (and vice-versa)

"Who's bug is it anyway?"

Using fake services
- Easier testing
- Bounded integration tests
- in process: vcr / webmock
- out of process: mimic / moco / stubby / monteback

Contract tests
- verify what service does is actually what we expect to do
- plain old rspec
- pacto
- pact


unit tests 
functional tests
bounded integration tests
--
end-to-end tests
--
service A contract tests
service B contract tests
service C contract tests
service D contract tests

When something is failling we expect end to end tests fail
and service X fail

Act II - Service gateways 
- Faraday (serialization, authentication, caching)
- Rack

They allow to abstract from the details (is it json? is it xml?)
instead focus just on the domain (products, users, etc..)

* Serialization
Gems to process responses
- hashie
- lazy_doc / embedded_doc / representable

* Caching
/products/1000.json 
- cache with http headers (10mins for example)
- request goes through faraday, if it is cached no longer uses the network
(mimic browser behaviour)


Epilogue

- conway`s law
- domain driven design (book) - suggest read the second half before first half
- postel`s law - evolve SOA over time
- hexagonal architecture

