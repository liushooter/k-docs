# 2014-02-18

```
  # concern 复用路由
  concern :commentable do
    resources :comments
  end

  resources :events, concerns: [:commentable] do
    resources :event_memberships, only: [:create]
  end
```


```
# polymorphic 多态
class CreateComments < ActiveRecord::Migration
  def change
    create_table :comments do |t|
      t.belongs_to :commentable, polymorphic: true
    end

    add_index :comments, [:commentable_id, :commentable_type] #索引
  end
end
```

[pry-rails](https://github.com/rweng/pry-rails) is Good

***

# 2014-02-20

```
class User < ActiveRecord::Base
  extend Enumerize

  enumerize :role, in: {user: 0, organizer: 1, admin: 2}, default: :user, scope: true
end

```

valid_email

pundit

enumerize

[pundit demo](http://www.elabs.se/blog/52-simple-authorization-in-ruby-on-rails-apps)
***

# 2014-02-21

```bundle  open```

[bash-spaces-in-alias-name](http://superuser.com/questions/105375/bash-spaces-in-alias-name)
