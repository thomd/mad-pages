
# express

    > npm i express

GET Route

    const express = require('express')
    const app = express()
    app.get('/', (req, res) => res.send('hello'))
    app.listen(80)

POST Route

    const express = require('express')
    const app = express()
    app.use(express.json())
    app.post('/', (req, res) => res.json(req.body))
    app.listen(80)

    > curl -d '{"a":1}' -H 'content-type: application/json' localhost

Template Engine

    > npm i pug

    app.set('views', './views')
    app.set('view engine', 'pug')
    ...
    res.render('index')

HTML Template

    res.sendFile(require('path').join(__dirname + '/index.html'))

Static resources

    app.use(express.static(__dirname + '/public'))


# https server

1. Generate a self-signed certificate

  Using openssl:

    openssl req -nodes -new -x509 -keyout localhost-key.pem -out localhost.pem

  Using mkcert:

    brew install mkcert
    mkcert -install                                                               # install root-ca inn system trust-store

    mkcert -key-file localhost-key.pem -cert-file localhost.pem localhost         # create key and cert for localhost

2. Enable HTTPS in Express

    var express = require('express')
    var fs = require('fs')
    var https = require('https')
    var http = require('http')
    var app = express()
    app.get('/', (req, res) => res.send(req.headers))
    http.createServer(app).listen(80)
    https.createServer({
      key: fs.readFileSync(__dirname + '/localhost-key.pem'),
      cert: fs.readFileSync(__dirname + '/localhost.pem')
    }, app).listen(443)

3. Request

    curl localhost
    curl -k https://localhost          # with self-signed openssl cert
    curl https://localhost             # with mkcert


# express(1)

    > npx express-generator myapp
    > npm install
    > DEBUG=myapp:* ./bin/www

Automatically restart server:

    > npm i -g nodemon
    > DEBUG=myapp_* nodemon bin/www
