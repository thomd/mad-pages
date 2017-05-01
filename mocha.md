
# mocha(1)

    npm i -g mocha
    mocha              # run all tests in 'test' folder
    mocha-w -R min     # watch mode

# Synchronous Test

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

# Hooks

    describe('hooks', function() {
      before(function() {
        // runs before all tests in this block
      })
      after(function() {
        // runs after all tests in this block
      })
      beforeEach(function() {
        // runs before each test in this block
      })
      afterEach(function() {
        // runs after each test in this block
      })
    })

