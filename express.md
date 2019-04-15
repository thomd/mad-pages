
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

    app.use(express.static('./public'))

# express(1)

    > mkcd myapp
    > npx express-generator myapp
    > npm install
    > DEBUG=myapp:* ./bin/www

Automatically restart server:

    > npm i -g nodemon
    > DEBUG=myapp_* nodemon bin/www
