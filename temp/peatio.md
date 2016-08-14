
# #
依赖 [RabbitMQ](https://www.rabbitmq.com/), 使用 RabbitMQ 做消息队列

brew install rabbitmq

使用gem amqp  bunny

[amqp_queue.rb](https://github.com/peatio/peatio/blob/master/app/models/amqp_queue.rb)

### gem

#### [active_hash](https://github.com/zilkey/active_hash)

```
class Country < ActiveHash::Base
end


class Currency < ActiveYaml::Base
end
```

[currency.rb](https://github.com/peatio/peatio/blob/master/app/models/currency.rb)

***

#### [datagrid](https://github.com/bogdan/datagrid)

[code](https://github.com/peatio/peatio/blob/master/app/grids/statistic/orders_grid.rb#L3-#L14)

```
    include Datagrid
    include Datagrid::Naming
    include Datagrid::ColumnI18n

    scope do
      Order.order('created_at DESC')
    end

    filter(:currency, :enum, :select => Order.currency.value_options, :default => 3, :include_blank => false)

```

***

#### [ransack](https://github.com/activerecord-hackery/ransack)

[code](https://github.com/peatio/peatio/blob/master/app/views/admin/statistic/members/show.html.slim#L7)

``` = search_form_for @q do |f|```

[code](https://github.com/peatio/peatio/blob/master/app/controllers/admin/statistic/members_controller.rb#L5-#L7)

```
@q = Member.order('id desc').includes(:two_factors, :id_document).search(params[:q])
result = @q.result(distinct: true)
@result_count = result.size

```

***

#### [gon](https://github.com/gazay/gon)
[code](https://github.com/peatio/peatio/blob/master/app/controllers/application_controller.rb#L13)

```gon.market = Market.find(latest_market).attributes ```

[code](https://github.com/peatio/peatio/blob/master/app/assets/javascripts/component_ui/market_chart.js.coffee#L14)

``` $.getJSON "/api/prices/#{gon.market.id}", (data) -> ```

***

#### [phonelib](https://github.com/daddyz/phonelib)
手机验证

***

#### [aasm](https://github.com/aasm/aasm)

AASM - Ruby state machines

AASM started as the acts_as_state_machine plugin but has evolved into a more generic library that no longer targets only ActiveRecord models.

It currently provides adapters for ActiveRecord and Mongoid, but it can be used for any Ruby class, no matter what parent class it has (if any).


#### [rotp](https://github.com/mdp/rotp)

ROTP - The Ruby One Time Password Library 基于HMAC的一次性口令生成算法

用于二次验证

[code](https://github.com/peatio/peatio/blob/master/app/models/two_factor/app.rb#L19)

`totp = ROTP::TOTP.new(otp_secret)`


## 资料

[Erlang和RabbitMQ学习总结](http://codemacro.com/2013/04/11/rabbitmq-erlang/)
