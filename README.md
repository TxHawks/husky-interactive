# husky-interactive [![](http://img.shields.io/npm/dm/husky-interactive.svg?style=flat)](https://www.npmjs.org/package/husky-interactive) [![npm version](https://badge.fury.io/js/husky-interactive.svg)](https://www.npmjs.com/package/husky-interactive) [![Mac/Linux Build Status](https://img.shields.io/travis/TxHawks/husky-interactive/master.svg?label=Mac%20OSX%20%26%20Linux)](https://travis-ci.org/TxHawks/husky-interactive) [![Windows Build status](https://img.shields.io/appveyor/ci/TxHawks/husky-interactive-4f05b/master.svg?label=Windows)](https://ci.appveyor.com/project/TxHawks/husky-interactive-4f05b/branch/master)

> Git hooks made easy

Husky can prevent bad commit, push and more :dog: _woof!_

This is a fork of the [original husky](/typicode/husky), which enables interactive git hooks, **at the cost of compatibility with gui clients**.

## Install

```sh
npm install husky-interactive --save-dev
```

```sh
yarn add husky-interactive --dev
```

```javascript
// Edit package.json
{
  "scripts": {
    "precommit": "npm test",
    "prepush": "npm test",
    "...": "..."
  }
}
```

```bash
git commit -m "Keep calm and commit"
```

_Existing hooks aren't replaced and you can use [any Git hook](HOOKS.md)._

_If you're migrating from `ghooks`, simply run `npm uninstall ghooks --save-dev && npm install husky-interactive --save-dev` and edit `package.json`. Husky-interactive will automatically migrate `ghooks` hooks._

## Uninstall

```sh
npm uninstall husky-interactive
```

```sh
yarn remove husky-interactive
```

## Tricks

<details>

### Debug hooks easily

If you need to debug hooks, simply use `npm run <script-name>`. For example:

```bash
npm run precommit
```

### Git GUI clients support

If you've installed Node using the [standard installer](https://nodejs.org/en/), [nvm](https://github.com/creationix/nvm) or [homebrew](http://brew.sh/), Git hooks will be executed in GUI applications.

### Working with multiple version of Node

If [`nvm`](https://github.com/creationix/nvm) is installed, husky-interactive will try to use the `default`/`current` installed Node version or use the project `.nvmrc`.

__Tip__ to use the system-installed version of node, `nvm` provides a [`system`](https://github.com/creationix/nvm#system-version-of-node) alias

### Accessing Git params

Git params can be found in `GIT_PARAMS` environment variable.

### accessing the initiating Git command

The command that initiated the execution of the hook can be found in the `GIT_COMMAND` environment variable.

### Setting a different log level

By default, husky-interactive will run scripts using `--silent` to make the output more readable. If you want to override this, simply pass a different log level to your scripts:

```json
"precommit": "npm run some-script -q"
```

_`-q/--quiet` is equivalent to `--loglevel warn` which is npm default log level._

### Git submodule and subtree support

Yes

### Cygwin support

Yes

### Yarn support

Please use `yarn` `v0.24+`

</details>

## See also

* [pkg-ok](https://github.com/typicode/pkg-ok) - Prevents publishing modules with bad paths
* [please-upgrade-node](https://github.com/typicode/please-upgrade-node) - Show a message to upgrade Node instead of a stacktrace in your CLIs
* [react-fake-props](https://github.com/typicode/react-fake-props) - Fake props for your React tests

## License

MIT - [Typicode :cactus:](https://github.com/typicode) - [Patreon](https://www.patreon.com/typicode)
