Rails holy grail
Where did the OO go? Views should be objects too
---
Andrew Warner @ rapgenious

### What is the holy grail of the web
#### Best possible user experience
Single page, no thick clients

#### Best possible developer experience
Easy things should be easy
- Developer friendly frameworks
- DRY
- Write mostly one language
- SEO friendly

Airbnb Rendr

### Existing rails solutions
- duplicate code on client and server ?
- - have to update both
- turbo links
- - write just server-side HAML/ERB views
- - client is very simple
- anglular / ember / backbone
- - new twitter
- - kinda slow

Each thing has a tradeoff

### So what is the solution
- Perspectives library
- Same template on the client/server
- find the lowest common denominatior - {{mustache}}
- - because server and client have access to different resources
- - "logicless"

Generating the hash required for the view (perspective)
- Just a ruby object

### Benefits
- Separation of concerns
- - ugly conditionals in the views
- Testing
- - Perspectives are just ruby objects
- Caching
- - getting it for free with the 'cache' keyword







 
