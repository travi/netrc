# netrc

Parse netrc files

<!--status-badges start -->

[![Node CI Workflow Status][github-actions-ci-badge]][github-actions-ci-link]

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

[github-actions-ci-link]: https://github.com/travi/netrc/actions?query=workflow%3A%22Node.js+CI%22+branch%3Amaster

[github-actions-ci-badge]: https://img.shields.io/github/actions/workflow/status/travi/netrc/node-ci.yml.svg?branch=master&logo=github
