Improve Performance Quick and Cheap: Optimize Memory and Upgrade to Ruby 2.1
---
Alexander Dymo

Rails apps become slow because of GC

Memory overhead + slow GC = High memory consumption + enourmous time spent in GC

Don't hold big things in memory!

- ruby 2.1 is not a silver bullet

## Memory optimization strategies
### Tune GC
Balance the number of GC runs and peak memory usage

When is Ruby GC triggered in 2.1?
Minor GC - faster, only new objects collected
- not enough space for new obects

Environment variables

http://ruby-performance-book.com

### Limit the growth of your ruby processes
Introduce memory consumption control
- system tools
- external - heroku, monit, god
- external (OS kernel)
- - Process.setrlimit(Process::RLIMIT_AS, <N bytes>)

*What about background jobs?*
Use ```fork do ... end```

### Control GC manually
- OobGC unicorn/oob_gc
- make sure you have enough workers

### Write less ruby
Use SQL to do the heavy-lifting

### Avoid memory hogs
Everything that makes copies
- Use in-place modifications
- << instead of +=
- Filte::readline or each insteaad of readlines or read

ActiveRecord also consumes lots of data

Rails serializers copy too much

## Tools
- GC.stat
- objspace.so
- Valgrind


















