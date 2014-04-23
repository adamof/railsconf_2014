Advanced aRel: When ActiveRecord Just Isn't Enough
===
Cameron Dutro (Twitter)


```ruby
# Joins on rails 3+
.joins(:comments => :author)
.joins("JOIN authors ON ....")
```
- have to write JOIN and ON
- have to know mysql syntax
- confusing to match arguments with question marks
- not object-oriented

### aRel

```ruby
Post
  .joins(:comments)
  .joins(Comment.joins(:author).join_sources)
  .where(
    Author[:name].eq("Barack")
  )
```

- Relation algebra for ruby
- builds sql queries, generates asts
- applies queries optimizations
- enables chaining
- vexingly undocumented
- knows nothing about your models
- knows very little about your database
- does not retrive any data
- ActiveRecord does everything else


```ruby
Post.arel_table[:id]
Post.arel_table[:text]
```

With [arel helpers](https://github.com/camertron/arel-helpers)

```ruby
Post[:id]
Post[:text]
```

Chainable scopes
However .count is a terminal method

```ruby
Post.select(Post[:id].count, :text).to_sql
Post.select(Post[:id].sum).to_sql
Post.select(Post[:id].sum.as("foo")).to_sql
```

#### Arel named functions

```ruby
Post.select(Arel.star).to_sql
Post.select(:id).from(Post.select([:id, :text]).ast).to_sql
```

#### where

```ruby
Post.where(Post[:title].not_el("Arel"))
Post.where(Post[:id].gteq(200))
Post.where(Post[:id].lteq(100))
Post.where(Post[:id].in(1, 2))
```

#### joins

```ruby
.join(Comment.arel_table, Arel::OuterJoin)
```

```ruby
include ArelHelpers::JoinAssociation
.joins(join_association(Author, :comment, Arel::OuterJoin)
```

For joins with NxN tables
```ruby
Arel::Table.new(:courses_teachers)
```

#### order

```ruby
Post.order(:visitors) # ActiveRecord
Post.reverse_order(:visitors) # ActiveRecord

Post.order(Post[:name].desc) # aRel
```

#### matches

```ruby
Post.where(Post[:title].matches("%arel%")).to_sql
```


### SQL to AREL
scuttle (scuttle.io)

