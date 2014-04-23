Declan Whelan
Eric Roberts

Starts by crashing DHH
- design patterns

1. Embrace complexity
- understand your domain
- expressable code

2. Know where you are going

3. Be more than just a Rails developer

Quote to "7 patterns to refactor fat activerecord models" - code climate

MVC - outside of application hexagon - domain hexagon inside of application

DDD book from Eric Evans

Get more info about "Ubiquitous Language"
- understandable code
- have a customer, price, role, class. Express yourself. You shouldnt
be an expert to understand the domain

Hexagonal architecture

From in to out
- Core application
- Adapters
- Web / Message Queue / DB

Form Object example
- Inherihting ActiveModel::Model
- Validate attributes

Request Object

Service Object
-  

TL;DR; use form, request, service objects to control leaking
the domain problems into the whole system.

