# @stackline/vfile-sort

> vfile utility to sort messages by line/column.

[![npm version](https://img.shields.io/npm/v/@stackline/vfile-sort.svg?style=flat-square)](https://www.npmjs.com/package/@stackline/vfile-sort)
[![license](https://img.shields.io/npm/l/@stackline/vfile-sort.svg?style=flat-square)](https://github.com/alexandroit/stackline-vfile-sort)
[![GitHub repository](https://img.shields.io/badge/GitHub-alexandroit%2Fstackline-vfile-sort-181717?style=flat-square&logo=github)](https://github.com/alexandroit/stackline-vfile-sort)
[![Docs](https://img.shields.io/badge/docs-alexandro.net-0f766e?style=flat-square)](https://alexandro.net/docs/vanilla/vfile-sort/)
[![Reddit community](https://img.shields.io/badge/community-r%2FStackline-ff4500?style=flat-square&logo=reddit&logoColor=white)](https://www.reddit.com/r/Stackline/)

**[Documentation](https://alexandro.net/docs/vanilla/vfile-sort/)** | **[npm](https://www.npmjs.com/package/@stackline/vfile-sort)** | **[Issues](https://github.com/alexandroit/stackline-vfile-sort/issues)** | **[Repository](https://github.com/alexandroit/stackline-vfile-sort)**

**Current package version:** `1.0.1`

---

## Why this package?

`@stackline/vfile-sort` is the Stackline-maintained distribution of `vfile-sort@3.0.1`. It is an independent continuation of [vfile-sort](https://github.com/vfile/vfile-sort); original authors and licenses remain credited below.

## Compatibility

| Item | Value |
| :--- | :--- |
| Package | `@stackline/vfile-sort@1.0.1` |
| API target | `vfile-sort@3.0.1` |
| Supported Node.js | `See supported framework requirements` |
| License | `MIT` |
| Module type | `module` |
| Main entry | `index.js` |
| Types | `index.d.ts` |
| Runtime dependencies | `vfile, vfile-message` |

## Installation

```bash
npm install @stackline/vfile-sort
```

Preserve existing imports and plugin resolution with an npm alias:

```bash
npm install vfile-sort@npm:@stackline/vfile-sort
```

## Usage and API reference

### vfile-sort


[`vfile`][vfile] utility to sort messages.

## Contents

*   [What is this?](#what-is-this)
*   [When should I use this?](#when-should-i-use-this)
*   [Install](#install)
*   [Use](#use)
*   [API](#api)
    *   [`sort(file)`](#sortfile)
*   [Types](#types)
*   [Compatibility](#compatibility)
*   [Contribute](#contribute)
*   [License](#license)

## What is this?

This is a small package to sort the list of messages.
It first sorts by line/column: earlier messages come first.
When two messages occurr at the same place, sorts fatal error before warnings,
before info messages.
Finally, it sorts using `localeCompare` on `source`, `ruleId`, or finally
`reason`.

## When should I use this?

You can use this right before a reporter is used to give humans a coherent
report.

## Install

This package is [ESM only][esm].
In Node.js (version 14.14+ and 16.0+), install with [npm][]:

```sh
npm install @stackline/vfile-sort
```

In Deno with [`esm.sh`][esmsh]:

```js
import {sort} from 'https://esm.sh/vfile-sort@3'
```

In browsers with [`esm.sh`][esmsh]:

```html
<script type="module">
  import {sort} from 'https://esm.sh/vfile-sort@3?bundle'
</script>
```

## Use

```js
import {VFile} from 'vfile'
import {sort} from '@stackline/vfile-sort'

const file = VFile()

file.message('Error!', {line: 3, column: 1})
file.message('Another!', {line: 2, column: 2})

sort(file)

console.log(file.messages.map(d => String(d)))
// => ['2:2: Another!', '3:1: Error!']
```

## API

This package exports the identifier [`sort`][api-sort].
There is no default export.

### `sort(file)`

Sort messages in the given [vfile][].

###### Parameters

*   `file` ([`VFile`][vfile])
    — file to sort

###### Returns

Sorted file ([`VFile`][vfile]).

## Types

This package is fully typed with [TypeScript][].
It exports no additional types.

## Compatibility

Projects maintained by the unified collective are compatible with all maintained
versions of Node.js.
As of now, that is Node.js 14.14+ and 16.0+.
Our projects sometimes work with older versions, but this is not guaranteed.

## Contribute

See [`contributing.md`][contributing] in [`vfile/.github`][health] for ways to
get started.
See [`support.md`][support] for ways to get help.

This project has a [code of conduct][coc].
By interacting with this repository, organization, or community you agree to
abide by its terms.

## License

[MIT][license] © [Titus Wormer][author]



[build-badge]: https://github.com/vfile/vfile-sort/workflows/main/badge.svg

[build]: https://github.com/vfile/vfile-sort/actions

[coverage-badge]: https://img.shields.io/codecov/c/github/vfile/vfile-sort.svg

[coverage]: https://codecov.io/github/vfile/vfile-sort

[downloads-badge]: https://img.shields.io/npm/dm/vfile-sort.svg

[downloads]: https://www.npmjs.com/package/vfile-sort

[size-badge]: https://img.shields.io/bundlephobia/minzip/vfile-sort.svg

[size]: https://bundlephobia.com/result?p=vfile-sort

[sponsors-badge]: https://opencollective.com/unified/sponsors/badge.svg

[backers-badge]: https://opencollective.com/unified/backers/badge.svg

[collective]: https://opencollective.com/unified

[chat-badge]: https://img.shields.io/badge/chat-discussions-success.svg

[chat]: https://github.com/vfile/vfile/discussions

[npm]: https://docs.npmjs.com/cli/install

[esm]: https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c

[esmsh]: https://esm.sh

[typescript]: https://www.typescriptlang.org

[contributing]: https://github.com/vfile/.github/blob/main/contributing.md

[support]: https://github.com/vfile/.github/blob/main/support.md

[health]: https://github.com/vfile/.github

[coc]: https://github.com/vfile/.github/blob/main/code-of-conduct.md

[license]: license

[author]: https://wooorm.com

[vfile]: https://github.com/vfile/vfile

[api-sort]: #sortfile

## Credits and original authors

- Original project: [vfile-sort](https://github.com/vfile/vfile-sort).
- Titus Wormer.
- Copyright (c) 2015 Titus Wormer <tituswormer@gmail.com>.
- Stackline maintenance: [Alexandro Paixao Marques](https://www.linkedin.com/in/aleinfo/) and [Stackline contributors](https://github.com/alexandroit).

Original copyright, license notices and contributor acknowledgements remain part of this distribution. Stackline maintenance does not replace authorship of the original work.

## Community and Links

- [Stackline website](https://alexandro.net/)
- [GitHub projects](https://github.com/alexandroit)
- [npm packages](https://www.npmjs.com/~alex360qc)
- [Reddit community — r/Stackline](https://www.reddit.com/r/Stackline/)
- [Maintainer LinkedIn](https://www.linkedin.com/in/aleinfo/)

Use this repository's issue tracker for reproducible bugs and feature requests. Join r/Stackline for examples, usage questions and release discussions.
