# netrc [![Build Status](https://travis-ci.org/camshaft/netrc.png?branch=master)](https://travis-ci.org/camshaft/netrc)

Parse netrc files

<!--status-badges start -->

<!--status-badges end -->

## Usage

<!--consumer-badges start -->

<!--consumer-badges end -->

```js
var netrc = require('netrc');

var myNetrc = netrc();

console.log(myNetrc['github.com'])
// { login: 'my-oauth-token',
//   password: 'x-oauth-basic' }

myNetrc['github.com'].login = 'my-new-oauth-token';

netrc.save(myNetrc);
```

## API

### netrc([file])

Loads a `.netrc` file, defaulting to `~/.netrc`

### netrc.parse(string)

Parses netrc formatted string into an object:

```json
{
  "machine1.example.com": {
    "login": "my-login",
    "password": "my-password"
  },
  "machine2.example.com": {
    "login": "my-other-login",
    "password": "my-other-password"
  }
}
```

### netrc.format(object)

Formats a netrc object into a valid string

### netrc.save(object)

Persists a netrc object to `~/.netrc`

## Contributing

<!--contribution-badges start -->

<!--contribution-badges end -->

### Dependencies

```sh
$ nvm install
$ npm install
```

### Verification

```sh
$ npm test
```
