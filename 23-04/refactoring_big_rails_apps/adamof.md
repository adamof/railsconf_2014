Refactoring towards Component-based Rails architectures
---
Stephan Hagemann

Use gems as a packaging mechanism for parts of the application and mount them as engines.

Eveything is organised under this engine namespace
- routes
- controllers
- migrations and other things
- specs that don't need to load the whole damn application
Your app = sum of smaller parts

The complexity explodes, because of the number of possible interactions

Preferrential attachment - the more you have, the more you get

80/20 Rule applies to some main files, for example user.rb

## Single responsibility Principle
Refactor:
- methods
- classes
- modules as namespace
- applications?
- components

## Components over SOAs
- 1 repo
- 1 test suite
- 1 deployment
- no additional versioning constraints
- easier refactorings between parts

## Refactoring towards #cbra
### Teasing out app component
0. Got tests?
1. Find a vertical that makes sense on its own
2. Namespace controllers, views, models
3. Hunt down dependencies
4. Move all namespaced code into an engine
5. Profit...

### Extracting functional component
0. Got tests?
1. Find functional component
2. bundle gem 
3. move all files into gem
4. require the gem in your main app
5. add shims/ports/adapters to make the app happy
6. Profit


















