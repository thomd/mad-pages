
# express

  app.js

    const app = require('express')()
    app.get('/', (req, res, next) => res.send('hello')).listen(3000)

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
