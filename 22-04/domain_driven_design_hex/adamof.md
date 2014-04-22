Domain Driven Design - Hexagonal Architecture Rails
---
Declan Whelan
Eric Roberts

Ideas
- Embrace complexity
- - Tackle it headfirst
- Know where you're going
- - What would the responsibilities would be
- Be more than just a "Rails developer"

Something doesn't fit in the M, V, C areas and you end up with awful coupling

link - 7 patterns to refactor fat activerecord models - Code climate

M, V, C are extra concerns

### Ubiquitous language
Share language between the domain and the code
- If there is a "Customer" concept, it should be visible in the code
- Minimal translations

### Hexagonal architecture

#### Form object
Tickets and Ticketform
TicketForm includes ActiveModel model

#### Request object
order

#### Service object
reusable and extendable

The elephant in the room - the Repository


I liked:
the separation between persistance and the domain objects
+ form / request / service object, whichi you can reuse outside of rails
