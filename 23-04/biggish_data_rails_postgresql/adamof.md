Biggish Data with Rails and Postgresql
---
Starr Horne

Not big data

Postgres is fine with it 
1 terabyte in store
2 gb new every day

Computers get more awesome as time goes forward - Moore's Law
As DB growth outpaces Moore's Law you literaly travel back in time - Starr Horne

Solution 1: Hardware
Get real computers, not AWS

Solution 2: Querry efficiency
- EXPLAIN
- - look at "Plan Rows"
Mo'rows, mo'problems

COUNT and OFFSET & LIMIT kill bunnies

- Use > and < instead
- - SELECT msg FROM errors where id > # and id < #

- Sorting
- - even if have an index it kills bunnies
- - develop against real dataset!
- - limit the number of rows you touch

OS optimisations
- increase read-ahead
- - blockdev --setra 2048 /dev/sda
- use a modern filesystem
- tell PG about all that RAM
- Vacuum regularly

Velocity
- Too many DB connections
- Too many locks
- Intensive database queries
- Partitioning for deletion & archival
- - Kind of sharding
- - if you want to delete old data it just drops the DB
- Backups take forever
- - Can use streaming replication

We turned transistors in lolcats

bit.ly/biggish-data



