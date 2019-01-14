
# express

    npm i express pug

  app.js

    const app = require('express')()
    app.get('/', (req, res, next) => res.send('hello')).listen(3000)

Template Engine

    app.set('views', './views')
    app.set('view engine', 'pug')
    ...
    res.render('index')

HTML Template

    res.sendFile(require('path').join(__dirname + '/index.html'))

Static resources

    app.use(express.static('./public'))

# express(1)

    > mkcd myapp
    > npx express-generator myapp
    > npm install
    > DEBUG=myapp:* ./bin/www

Automatically restart server:

    > npm i -g nodemon
    > DEBUG=myapp_* nodemon bin/www
