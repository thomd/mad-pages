
# mocha(1)

    npm i -g mocha
    mocha              # run all tests in 'test' folder
    mocha-w -R min     # watch mode

# Synchronous Test

File _test/myTest.js_:

    var assert = require('assert')
    describe('description', function() {
      it('should ...', function() {
        var value = getSync()
        assert.equal(value, expected_value)
      })
    })

  Passing arrow-functions is discouraged.

# Asynchronous Test

Add a callback `done` to `it()` if you want to test an error-first callback:

File _test/myAsyncTest.js_:

    var assert = require('assert')
    describe('description', function() {
      it('should ...', function(done) {
        getAsync(function(err, value) {
          assert.equal(value, expected_value)
          done()
        })
      })
      it('should ... without errors', function(done) {
        getAsync(done)
      })
    })
