# netrc

Parse netrc files

<!--status-badges start -->

[![Node CI Workflow Status][github-actions-ci-badge]][github-actions-ci-link]
![SLSA Level 2][slsa-badge]

<!--status-badges end -->

## Usage

<!--consumer-badges start -->

[![npm][npm-badge]][npm-link]
![node][node-badge]

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

[![semantic-release: angular][semantic-release-badge]][semantic-release-link]
[![Renovate][renovate-badge]][renovate-link]

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

[semantic-release-link]: https://github.com/semantic-release/semantic-release

[semantic-release-badge]: https://img.shields.io/badge/semantic--release-angular-e10079?logo=semantic-release

[renovate-link]: https://renovatebot.com

[renovate-badge]: https://img.shields.io/badge/renovate-enabled-brightgreen.svg?logo=renovatebot

[slsa-badge]: https://slsa.dev/images/gh-badge-level2.svg

[npm-link]: https://www.npmjs.com/package/@travi/netrc

[npm-badge]: https://img.shields.io/npm/v/@travi/netrc?logo=npm

[node-badge]: https://img.shields.io/node/v/@travi/netrc?logo=node.js
