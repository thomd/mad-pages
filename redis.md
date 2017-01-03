
# redis

    > brew install redis
    > redis-server

# node_redis

    > npm i redis

app.js:

    var redis = require('redis'), client = redis.createClient()

    client.on('connect', () => {
       client.set('key1', 'some value', redis.print)
       client.get('key1', redis.print);
    }

  Set/Get String:

    client.set('key1', 'value1')
    client.get('key1', (err, reply) => { console.log(reply) })

  Deleting/Expiring Keys:

    client.del('key1')
    client.expire('key1', 30)                   # expire after 30 sec

  Incrementing and Decrementing:

    client.set('key2', 0)
    client.incr('key2')
    client.incrby('key2', 2)
    client.decr('key2')
    client.decrby('key2', 2)

