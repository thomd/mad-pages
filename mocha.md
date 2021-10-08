
# mocha(1)

    npx mocha                   # run all tests in folder `test`
    npx mocha test.js           # run test `test.js`
    npx mocha -w -R min         # watch mode with 'min' reposter

## Synchronous Test

    var assert = require('assert')
    describe('description', () => {
       it('should ...', () => {
         assert.ok(true)
         assert.equal(value, expected_value)
       })
    })

  Do not use arrow-functions when using Mocha Context.

## Asynchronous Test

  Add a callback `done` to `it()` if you want to test an error-first callback:

    var assert = require('assert')
    describe('description', () => {
       it('should ...', done => {
          do-something-async((err, value) => {
             assert.equal(value, expected_value)
             done()
          })
       })
    })

## Hooks

    describe('hooks', function() {
       before(function() { ... })
       after(function() { ... })
       beforeEach(function() { ... })
       afterEach(function() { ... })
    })

