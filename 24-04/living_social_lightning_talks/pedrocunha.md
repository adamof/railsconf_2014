Sharing Templates in an SOA
Ed Weng

- very simple things on a monolith can be very complex
on services

- How do we keep ourselves DRY?
- How do we keep the same view synchronized?
  - probably lots of copy paste coding
  - requires changes in multiple places

- How about to put everything in an engine ?
  - eliminates copy/paste coding
  - shareable translation files, images, etc..
  - you still have to do `bundle update`

- we build another service: stepford. Shares views
across services.

Client app: "Send me footer"
Stepford: "Here is your package"


Package Request
- GET /package?elements=footer&city_id=1
- styles + markup + scripts

Pros: Keeps views DRY; Easy to release changes;
Cons: Another service; another network request (on server side); changes
have much larger impact (JavaScript!)


-----------------------
Production code analysis
- focus on performance and exception monitoring
- test code coverage

how dead code sticks around
- large teams are not good at communicating what is no longer needed
- ab tests never removing a loser
- one offs that are irrelevant

finding dead code
- use newrelic (order by count ASC on transactions - maybe it can be removed)
- stats intstrumentation 
  - background events executed
  - emails sent (tracking of emails)
  - views rendered (ActiveSupport::Notifications.subscribe) - flatfoot gem 
  - one off trackers 
  - production performance comparisons
  - translations usage
- use logs
  - kibana
  - splunk
  - hadoop
  - all in same place
  - standardize log format & some keys / variables across systems
- coverband
  - `set_trace_fun`
  - performance sit reduced by sampling

-----------------------
One weird trick to boost your productivity when working from home
Rodrigo Franco

moourl.com/focus
10y working remotely

**boundaries**

startup ritual: get presentable; drink coffee
eliminate distractions: have a good pair of headphones
focus flag: Im not here do not disturb me
no multitasking: no read HN, Reddit
do not work all the time: find a good balance
spend time with others
codewars.com
khan academy

