# 🦉 OWL

> GIT hooks made easy.

&plus; Written in pure JS. \
&plus; Configuration as code: Stored in readable JSON format. \
&plus; MIT Licensed.

[![@bbortt/owl](https://img.shields.io/npm/v/@bbortt/owl?label=@bbortt/owl)](https://www.npmjs.com/package/@bbortt/owl)
[![Blazing Fast](https://img.shields.io/badge/speed-blazing%20%F0%9F%94%A5-brightgreen.svg)](https://twitter.com/acdlite/status/974390255393505280)
[![License](https://img.shields.io/github/license/bbortt/owl)](https://github/bbortt/owl/blob/release/LICENSE)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fbbortt%2Fowl.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fbbortt%2Fowl?ref=badge_shield)

**Table Of Contents**

- [Installation](#installation)
- [Configuration Files](#configuration-files)
- [CLI](#cli)
- [How Does It Work?](#how-does-it-work)
- [License](#license)

# Installation

Once downloaded you need to initialize the hook and create a configuration. Follow the steps below, and you will be good
to go in seconds!

## Scripts

### Automated

Add `@bbortt/owl` and `@bbortt/owl-autoinstall` at the same time. The `postinstall` script in the second package will
take care of installing the scripts in `.owl`.

### Manual

Add `@bbortt/owl` via `npm` or `yarn` and execute the installation command in order to set up the hooks:

```shell
owl install
```

## Initialization

You can create a compatible rc file by hand or via `owl init` (see the [documentation](#init)). Add hooks using
the `owl add` command (`help` for help), or by hand too. Example:

```shell
owl add pre-commit "npx pretty-quick --staged"
```

Take a look at [configuration files](#configuration-files) or the [CLI documentation](#cli) for more information.

# Configuration Files

In order to support multiple commands in the same hook this project reads configuration
via [`cosmiconfig`](https://github.com/davidtheclark/cosmiconfig). Valid files are for example `package.json`
, `.owlrc.json` or other compatible rc files. \
This does make it possible to configure hooks without using the [CLI](#cli)
too. An example [`.owlrc.json`](https://github.com/bbortt/owl/blob/release/.owlrc.json):

```json
{
  "hooks": {
    "pre-commit": ["npx pretty-quick --staged"]
  }
}
```

## Supported Hooks

- `pre-commit`

More to come in [#1](https://github.com/bbortt/owl/issues/1).

# CLI

The following commands are executable through the cli `owl [COMMAND] args..`:

## `install`

Signature: `owl install [dir=.owl]`. \
Arguments:

- `--force` install outside process directory (useful for multi module projects).

Installs the binary into `.owl`. **Careful:** Do not manually update the generated files. They will be overwritten by
any subsequent calls of this command (for example in a `postinstall` script).

## `init`

Signature: `owl init`.

Initializes a configuration file called `.owlrc.json` in the root directory. It does not contain any hooks.

## `add`

Signature: `owl add [TYPE] [COMMAND]`.

Adds a hook by type into any found configuration file. E.g.
the [`.owlrc.json`](https://github.com/bbortt/owl/blob/release/.owlrc.json) was completed
using `owl add pre-commit "ngx pretty-quick --staged"`.

Supported hooks are: [ `applypatch-msg`, `commit-msg`, `fsmonitor-watchman`, `post-update`, `pre-applypatch`, `pre-commit`, `pre-merge-commit`, `pre-push`, `pre-rebase`, `pre-receive`, `prepare-commit-msg`, `update` ].

# How Does It Work?

> It really is no magic! To be documented.

# License

This project is licensed under the terms of the [MIT license](https://github/bbortt/owl/blob/release/LICENSE).
