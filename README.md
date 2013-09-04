# passport-redgate

A passport provider for Red Gate ID.

[![Build Status](https://travis-ci.org/ForbesLindesay/passport-redgate.png?branch=master)](https://travis-ci.org/ForbesLindesay/passport-redgate)
[![Dependency Status](https://gemnasium.com/ForbesLindesay/passport-redgate.png)](https://gemnasium.com/ForbesLindesay/passport-redgate)
[![NPM version](https://badge.fury.io/js/passport-redgate.png)](http://badge.fury.io/js/passport-redgate)

## Installation

    npm install passport-redgate

## Example

```js
var RedGateStrategy = require('passport-redgate')

passport.use(new RedGateStrategy({
    returnURL: 'http://localhost:3000/login',
    realm: 'http://localhost:3000/'
  },
  function(identifier, done) {
    User.findByOpenID({ openId: identifier }, function (err, user) {
      return done(err, user);
    });
  }
));


app.get('/login', passport.authenticate('redgate'), function(req, res){
  // Successful authentication, redirect home.
  res.redirect('/');
});
```

## License

  MIT