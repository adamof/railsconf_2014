Advanced AREL
---
When ActiveRecord just isn't enough

Problems:
- the join methods
- - have to write JOIN and ON
- - have to know mysql
- - we don't know the table names
- the where method
- - have know mysql
- - matching ? to arguments
- - not OO

### AR vs AREL
AREL is used for building queries - relational algebra
- enables chaining
- applies query optimization
- doesn't know about columns and tables
- just creates the queries and passes them to AR to execute
- arel-helpers gem

### Tables, columns
By using the arel-helpers you can reference columns in your tables

### Terminal methods
Execute immediately
count, first, last, to_a, pluck

### SQL operators
#### Select
  Post.select(Post[:visitors].sum).to_sql
  Post.select(Post[:visitors].max).to_sql
Post.select(:id).from(...)

#### Where
  Post.where(Post[:visitors].gt(250)).to_sql

#### Join
  Author.joins(:comments, comment: :post).where(Post[:id].eq(42)).to_sql

#### QueryBuilders

scuttle.io

### Logical

### MATCH in

WE DONT NEED STRINGS








