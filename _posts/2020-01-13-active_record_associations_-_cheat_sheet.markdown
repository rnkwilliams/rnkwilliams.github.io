---
layout: post
title:      "Active Record Associations - Cheat Sheet"
date:       2020-01-13 15:17:00 +0000
permalink:  active_record_associations_-_cheat_sheet
---


In Rails, an association is a connection between two Active Record models. Associations are super important features as they can make common operations in your code much simpler. By using Active Record's macro-style association class methods, you also get a number of utility methods added to your model. In the last major sections of the curriculum (Sinatra & Rails), associations have been used heavily to make the connection between models easier to understand and work with while building applications. 

According to [RailsGuides](http://https://guides.rubyonrails.org/association_basics.html) documentation website, there are six types of associations that Rails supports:

* **belongs_to**
* **has_one**
* **has_many**
* **has_many :through**
* **has_one :through**
* **has_and_belongs_to_many**



**Many-to-one Relationships - (belongs_to, has_many, has_one, has_one :through)**

The most common relationship declared in Active Record associations is the many-to-one relationship. 

**`belongs_to` **

In the `belongs_to` association, there is a one-to-one connection with another model in such a way that each instance of the declaring model "belongs to" one instance of the other model.

In the example below, each `Post` is assigned with exactly **one** `Author`.

```
class Post < ActiveRecord::Base
  belongs_to :author
end
```
The `Post ` class now has access to new instance methods using `author` which will return the actual `Author` object that is attached to that ` @post`.

```
@post.author_id = 5
@post.author
```

**`has_many`**

On the reverse side of the `belongs_to` association is the `has_many` association. In the `has_many` association, there is a many-to-one connection with another model which indicates that each instance of the model has more instances of another model.

In the example below, the `Author` is assigned to **many** `Posts`.

```
class Author < ActiveRecord::Base
  has_many  :posts
end
```

**`has_one`**

Another one-to-one connection is the `has_one` association. What makes this association different however is that each instance of a model contains or possesses one instance of another model. For example:

```
class User < ActiveRecord::Base
  has_one  :account
end
```

**`has_one :through`**

The `has_one :through` association sets up a one-on-one connection with a model. The declaring model can be matched with one instance of another model by proceeding through a third model.

In the example below, each supplier has one account, and each account is associated with one account history,

```
class Supplier < ApplicationRecord
  has_one :account
  has_one :account_history, through: :account
end```
 
```
class Account < ApplicationRecord
  belongs_to :supplier
  has_one :account_history
end```
 
```
 class AccountHistory < ApplicationRecord
  belongs_to :account
end```



**Many-to-Many Relationships - (has_many :through, has_and_belongs_to_many)**


**`has_many :through`**

The `has_many :through` association is often used to set up a many-to-many connection with another model. This association requires a third model or join table to indicate that the declaring model can be matched with zero or more instances of another model. For example: 

```
class Race < ApplicationRecord
  has_many :sessions
  has_many :workouts, through: :sessions
end```
 
```
class Session < ApplicationRecord
  belongs_to :race
  belongs_to :workout
end```
 
```
class Workout < ApplicationRecord
  has_many :sessions
  has_many :races, through: :sessions
end
```


The `sessions`  table would be considered the join table as it belongs to both race and workout tables.


**`has_and_belongs_to_many`**

The `has_and_belongs_to_many` association creates a direct many-to-many connection with another model, with no intervening model. 

In the below example, if your application includes assemblies and parts, with each assembly having many parts and each part appearing in many assemblies, the models would be declared this way:

```
class Assembly < ApplicationRecord
  has_and_belongs_to_many :parts
end```
 
```
class Part < ApplicationRecord
  has_and_belongs_to_many :assemblies
end
```




