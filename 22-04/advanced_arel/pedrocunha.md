Cameron Dutro
- Twitter

Comparison on rails 3/4 how to do joins

.joins(:comments => :author)

.joins("JOIN authors ON ....")
- have to write join and on
- have to know mysql syntax
- confusing to match arguments with question marks
- not object-oriented

AREL
Post
  .joins(:comments)
  .joins(Comment.joins(:author).join_sources)
  .where(
    Author[:name].eq("Barack")
  )

- Relation algebra for ruby
- builds sql queries, generates asts
- applies queries optimizations
- enables chaining
- vexingly undocumented
- knows nothing about your models
- knows very little about your database
- does not retrive any data
=> ActiveRecord does everything else


Post.arel_table[:id]
Post.arel_table[:text]

With arel helpers

Post[:id]
Post[:text]


Chainable scopes
However .count is a terminal method

Post.select(Post[:id].count, :text) (verify this)
Post.select(Post[:id].sum).to_sql
Post.select(Post[:id].sum.as("foo")).to_sql

Arel named functions

Post.select(Arel.star).to_sql

Post.select(:id).from(Post.select([:id, :text]).ast).to_sql

### where

Post.where(Post[:title].not_el("Arel")).to_sql
- gteq(250)
- lteq(100)

Post.where(Post[:id].in(1, 2))

### joins

.join(Comment.arel_table, Arel::OuterJoin)

include ArelHelpers::JoinAssociation
.joins(join_association(Author, :comment, Arel::OuterJoin)

For joins with NxN tables
Arel::Table.new(:courses_teachers)

### order

Post.order(:visitors) ActiveRecord
Post.reverse_order(:visitors) ActiveRecord

Check how to do it with Arel reverse order

### matches

Post.where(Post[:title].matches("%arel%")).to_sql

### reflect

investigate what is reflect

scuttle (scuttle.io)
SQL to AREL
