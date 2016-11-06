# Unit Testing Express Routes

Example project to show how to unit test Express routes using [Mocha](https://mochajs.org/), [Sinon](http://sinonjs.org/), [Chai](http://chaijs.com/) and [Proxyquire](https://github.com/thlorenz/proxyquire).

## Install

Clone this repository and install the dependencies as follows:

```
git clone git@github.com:MarcL/unit-test-express-routes.git
npm install
```

## Running the tests

The code sets up a basic Express server with a few routes and some tests which just cover testing the server setup. The middlewares have no tests as they're simply there for stubbing expectations in the `launch.test.js` tests. Run the test suite using Mocha:

```
mocha
```

The tests assert that the routes are set up with the expected middleware. In my mind, it helps to complete code coverage, and also helps to guarantee that the routes are called with all of the expected middleware. A good example is for routes that are locked down using an authentication layer. Your tests can now assert that the authentication middleware is **definitely** called on the the expected routes. In this case it means that these test almost become and additional set of security tests too.

I'd expect there to be an additional layer of integration testing using [supertest](https://github.com/visionmedia/supertest) and [nock](https://github.com/node-nock/nock) which would better verify the full flow on each route too.

I'll write up this in more detail in a blog post shortly.