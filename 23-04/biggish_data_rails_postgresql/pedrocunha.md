Biggish Data with Rails & Postgresl
=========
Starr Horne

Honeybadger
1. terabyte database
2. gigabytes new data every day

Postgresql can handle this, but maybe your app can not

Reference: PDP-11

Moore's Law
- Computers get more awesome as time goes forward
- As DB grows in size, you go back in time according to Moore's Law

Inquiry efficience

Mo' rows
Mo' problems

Use EXPLAIN
- example with count. It does count rows one by one

OFFSET X
- it counts X rows before start paginating
- use > and < instead
 
TIL:
- Develop agaisnt a real dataset
- Do not assume, EXPLAIN
- Limit the number of rows you touch

DOS & DB TUNING
- increase Read-Ahead cache
- use a modern filesystem (bit.ly/biggish-fs)
- tell PG about all that RAM (bit.ly/biggish-pgtune)
- vaccum regularly (bit.ly/biggish-vacuum)

Velocity
- Too many DB connections (bit.ly/biggish-pool)
- Too many locks (bit.ly/biggish-locks)
- Intensive DB queries (bit.ly/biggish-replication)
- Partitioning for deletion & archival (bit.ly/biggish-partition) - you do not
need to update ruby for this, can be at DB level
- Backups take forever (bit.ly/biggish-wal-e), streaming replication



