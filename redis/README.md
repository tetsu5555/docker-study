## use redis container
```
# up container
docker-compose up

# enter redis container
docker-compose exec redis bash

# redis cli
# connect to redis
redis-cli
```

## how to use

### kvs

```
# set <key> <value>
127.0.0.1:6379> set foo bar
OK

# get <key>
127.0.0.1:6379> get foo
"bar"
```

### pub/sub

```
# subscribe channel
127.0.0.1:6379> SUBSCRIBE veritas
Reading messages... (press Ctrl-C to quit)
1) "subscribe"
2) "veritas"
3) (integer) 1

# publish to channel
127.0.0.1:6379> PUBLISH veritas 'next unicorn company'
(integer) 1


# get data in subscriber
1) "message"
2) "veritas"
3) "next unicorn company"
```