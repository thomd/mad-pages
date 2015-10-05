
# express

  app.js

      var app = require('express')()
      app.get('/', function(req, res) {
        res.send('hello');
      }).listen(3000)

# express(1)

    npm install -g express-generator

    express myapp
    cd myapp
    npm install
    DEBUG=myapp:* ./bin/www

