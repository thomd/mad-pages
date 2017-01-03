
# express

  app.js

    var express = require('express')
    var app = express()
    app.get('/', function(req, res) {
      res.send('hello');
    })
    app.listen(3000)

Jade Template Engine

    app.set('views', './views')
    app.set('view engine', 'jade')
    ...
    res.render('index')

HTML Template

    res.sendFile(require('path').join(__dirname + '/index.html'))

Static resources

    app.use(express.static('./public'))

# express(1)

    > npm install -g express-generator

    > express myapp
    > cd myapp
    > npm install
    > DEBUG=myapp:* ./bin/www

Automatically restart server:

    > npm i -g nodemon
    > DEBUG=myapp_* nodemon bin/www
