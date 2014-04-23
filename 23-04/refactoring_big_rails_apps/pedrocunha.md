Stephan Hagemann

Component based architecture

/the_next_big_thing
  /components
    /annoyance
    /email...
  /rails_container
  Gemfile

Use the gemfile to reference several components

"Exploding complexity"
- Splitting into components - reduced (exploded) complexity

"The devil always shits on the big spot"
- example user.rb (most LOC)

Single Responsability Principle
- Identifies things that do not belong

Using mixins is just saying you cant be bothered
to look at many things on your string AKA hidding complexity

Components over SOA
- 1 repo
- 1 test suite (and splittable)
- 1 deployment
- no additional versioning constraints
- easier refactorings between parts

Within a SOA componentize your app

Teasing out App Component
1. Find a vertical that makes sense on its own
2. Namespace controllers, views, models
3. Hunt down other dependencies
4. Move all namespaced code into an engine

Extracting functional component
1. Find a functional component 
2. Build a gem
3. Move all files into gem (and namespace)
4. 
5. Require the gem from your app
6. Add shims/ports/adapters to make the app happy
