<h1 align="center">commitlint-config-ghostwriter</h1>

<div align="center">

[![CI Status](https://github.com/JSanchezIO/commitlint-config-ghostwriter/workflows/CI/badge.svg)](https://github.com/JSanchezIO/commitlint-config-ghostwriter/actions/workflows/ci.yml)
[![Code Style: Prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://prettier.io/)
[![Commitizen Friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![NPM Package Version](https://img.shields.io/npm/v/commitlint-config-ghostwriter)](https://www.npmjs.com/package/commitlint-config-ghostwriter)
[![Semantic Release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://semantic-release.gitbook.io/semantic-release/)

</div>

<br />

You want to leverage commitlint to enforce a consistent commit messages that can be parsed to
generate a `CHANGELOG.md` but none of the available presets support your commit types or tools,
e.g., Bitbucket, JIRA, Trello. This preset supports configuration via a `.changelogrc.js` file.

<br />

## Installation

```sh
npm i commitlint-config-ghostwriter
```

<br />

## Usage

1. Create and configure a `.changelogrc.js` file in the root of your repository
2. Update commitlint to leverage `commitlint-config-ghostwriter`

   ```js
   module.exports = {
     extends: ['ghostwriter'],
   };
   ```

3. Run commitlint

<br />

## Configuration

<br >

### `scopes` : _Scope[] | undefined_

---

The array of scopes that are available for selection when commiting. If left `undefined`, then any
scope may be entered when committing.

```ts
type Scope = { description: string; type: string };
```

<br >

### `types` : _Array<HiddenType | VisibleType>_

---

The array of type objects representing the explicitly supported commit message types, and whether
they should show up in generated CHANGELOGs.

```ts
type CommitType = { description: string; type: string };

type HiddenType = CommitType & { hidden: true; section: undefined };

type VisibleType = CommitType & { hidden: undefined; section: string };
```
