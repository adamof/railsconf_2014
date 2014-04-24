Effectively Testing Services
---
Neal Kemp

### Why?
Why are services themselves important?
- build faster
- scale easy
- services are critical to most modern Rails apps

Why test them?
- they compose crucial features

### How?

What is different about services?
- external network requests
- you don't own the code

Airplane mode:
- failure is bad
- no network requests
- pre-recorder responses are okay

### gem sham_rack
Loads a rack server that doubles some external services for testing purposes.
- expressive
- readable

- vcr
- gem puffing-billy
- Postman addon for chrome
- HTTPie
- Charles






