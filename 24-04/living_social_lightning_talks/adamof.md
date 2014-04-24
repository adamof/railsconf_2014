LivingSocial Lightning Talks
---

## Sharing templates in an SOA - Ed Weng
Everything was in one monolith!
The website now is comprised of many smaller app, pretty much every page is an app.

How do we share views and stay DRY?
bad:
- lots of copy/paste
- requires changes in multiple places

What about putting everything in an engine/gem
- eliminates copy/paste coding
- you can share translation files, images, etc
- you still have to 'bundle update' in every app

Another service! - Stepford
Responible for sharing the views

1. Give me the footer
- - just a request to a url
- - can pass parameters (like city id)

2. Package (response) json
- - styles - a path
- - markup - actual HTML
- - scripts - a path

Pros:
- Keeps views DRY
- Easy to release changes

Cons:
- Another service
- Another network request
- Changes have much larger impact

They have caching (Varnish)

## Internal gem infrastructure
Gems help:
- Share all the things!
- Internal open source culture
- separate concerns
- isolation

Example:

### Building
Using bundler
Namespacing
Semantic versioning - semver@google

### Releasing
rake release
don't accidentally opensource your code

### Sharing
gem servers
- geminabox
- stickler

## Production code analysis @danmayer
As you split the application, the code analysis gets tricky

How dead code sticks around?
- large teams aren't good at communicating what's no longer needed
- old AB tests
How to find it?
- NewRelic or Appneta
- - from transactions
- - newrelic_route_check
- stats instrumentation
- - statsd to wrap around methods
- - flatfoot to track views usage
- production code coverage
- use logs
- Coverband
- - based to set_trace_func


## Being more effective working from home
@caffo

Boundaries!
1. Startup ritual
- - dressup
- - make coffee
2. Eliminate distractions
- - good pair of headphones
3. Focus flag
- - show the world I am working
4. No multitasking
- - ignore not importatnt messages
5. Don't work all the time
6. Spend time with others































