# Andrew Vaughan's Generator Package

<!-- Status Badges -->

[![Version][badge-version]][github-releases]
[![License][badge-license]][github-license]
[![Build Status][badge-build]][ci-travis]
[![Dependency Status][badge-dependencies]][ci-daviddm]
[![Coverage percentage][badge-coverage]][ci-coveralls]

This set of [Yeoman][yeoman] Generators provides bootstrap resources for building new projects in the style of
standards developed and maintained by [Andrew Vaughan][github-profile].

---

## Installation

Before using these generators, [Yeoman][yeoman] must first be installed globally via [npm][npm]:

```bash
npm i -g yo
```

To use these specific generators, this package must also be installed. As this NPM package is private, you must do so
locally and link the repository on your system:

```bash
git clone https://github.com/andrewvaughan/generator-andrewvaughan
cd generator-andrewvaughan
npm link
```

### Usage

A complete list of generators can be found, after installation, with the `yo generators` command:

```
$ yo --generators
Available Generators:

  andrewvaughan
```

It is recommended to create an empty project folder and run the appropriate generator within that empty directory. For
example, to create a new example project and bootstrap a Node.js project:

```bash
mkdir example-node-project
cd example-node-project
yo andrewvaughan:node
```

Each generator is configured to develop a project both locally and, optionally, for various remote services, such as
GitHub. Detailed instructions on each can be found [below](#available-generators), but all generators are also
configured to be fairly understandable without documentation.

---

## Available Generators

The primary generator included can be used to make a basic, agnostic project focusing more on documentation and common
service configuration.  Each of the sub-generators provided can be used to add or modify specific files,
configurations, and structures beyond basic standards.

| Generator       | Description                                                                |
|-----------------|----------------------------------------------------------------------------|
| `andrewvaughan` | Default generator to setup files and configurations common to all projects |

### `andrewvaughan`

The primary generator focuses mainly on standard documentation and common tool configurations. It specifically builds
the following:

| File        | Description |
|:-----------:|-------------|

Optionally, the main generator will also configure a GitHub project, whether new or one that already exists.

---

## Contributing

All contribution is managed via [GitHub Issues][github-issues]. All contributors are expected to familiarize
themselves with the [Contribution Guidelines][github-contribute]. No work will be accepted if they do not follow these
guidelines.

### Release Policy

Releases of this project follow [Semantic Versioning][semver] standards in a `MAJOR.MINOR.PATCH` versioning scheme of
the following format:

* `MAJOR` - modified when major, incompatible changes are made to the application,
* `MINOR` - modified when functionality is added in a backwards-compatible manner, and
* `PATCH` - patches to existing functionality, such as documentation and bug fixes.

---

## License

This project, in part and in whole, regardless of contributor, is made available under the
[MIT License][github-license]:

```
The MIT License (MIT)

Copyright (c) 2019 Andrew Vaughan <hello@andrewvaughan.io> (https://andrewvaughan.io)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated
documentation files (the "Software"), to deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the
Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Effective: November 22, 2019
```




[badge-build]:        https://travis-ci.org/andrewvaughan/generator-andrewvaughan.svg?branch=develop
[badge-coverage]:     https://coveralls.io/repos/github/andrewvaughan/generator-andrewvaughan/badge.svg?branch=develop
[badge-dependencies]: https://david-dm.org/andrewvaughan/generator-andrewvaughan.svg
[badge-license]:      http://img.shields.io/badge/license-MIT-blue.svg?style=flat
[badge-version]:      http://img.shields.io/badge/version-1.0.0-blue.svg?style=flat

[ci-coveralls]:       https://coveralls.io/github/andrewvaughan/generator-andrewvaughan?branch=develop
[ci-daviddm]:         https://david-dm.org/andrewvaughan/generator-andrewvaughan
[ci-travis]:          https://travis-ci.org/andrewvaughan/generator-andrewvaughan

[github-contribute]:  CONTRIBUTING.md
[github-issues]:      https://github.com/andrewvaughan/generator-andrewvaughan/issues
[github-license]:     LICENSE
[github-profile]:     https://github.com/andrewvaughan/
[github-releases]:    https://github.com/andrewvaughan/generator-andrewvaughan/releases

[npm]:                https://www.npmjs.com/
[semver]:             https://semver.org/
[yeoman]:             https://yeoman.io/
