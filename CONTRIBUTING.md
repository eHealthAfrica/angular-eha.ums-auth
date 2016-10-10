# Contributing

## Prerequisites

- Firefox (for running test suite)
- node (0.12.0)
- bower (1.3.12)
- grunt-cli (0.1.7)
- grunt (0.4.5)


## Installation

```bash
# Fork the upstream repo on github and pull down your fork
git clone git@github.com:yourusername/angular-eha.user-management-auth.git
# change into project folder
cd angular-eha.user-management-auth
# Add the upstream as a remote
git remote add upstream  git@github.com:eHealthAfrica/angular-eha.user-management-auth.git
# Install the dev dependencies
npm install
```

## Docs

Code should be documented following the guidelines set out by [jsdoc](http://usejsdoc.org/) and [ngdoc](https://github.com/angular/angular.js/wiki/Writing-AngularJS-Documentation). We can then leverage [Dgeni](http://github.com/angular/dgeni) or something simlary to generate documentation in any format we like.

## Test Suite

The test suite is configured to run in Firefox and is powered by:

- Karma
- Mocha
- Chai (as promised)
- Sinon (chai)

The library is conducive to TDD.  `grunt test:watch` is your friend. As modules (and templates) are exposed on their own namespace you can easily isolate areas of the code base for true unit testing without being forced to pull in the whole library or stub/mock modules irrelevant to the feature(s) you're testing.

### Running Tests

#### Single run

```bash
grunt test
```

#### Watch

```bash
grunt test:watch
```

## Transpiling templates (html2js)

Transpiling our html templates into js allows us to neatly push them into the `$templateCache`.

To transpile the templates it's another simple grunt command:

```bash
grunt templates
```

This will compile the templates to the `dist/` folder. But it's probably best to avoid this all together. Both the `grunt test` and `grunt release` commands take care of all of this for you.

If you need to override the default template, simply replace what's already in the `$templateCache` with what ever you want. One way to achieve this is like this:

```html
<script id="templates/back-button.directive.tpl.html" type="text/html">
    <button>I'm a button!</button>
</script>
```

## Release Process

We use [semantic-release][] to automate our releases. Just ensure your commit message conforms to the [AngularJS conventions][] and your all set!

[semantic-release]: https://github.com/semantic-release/semantic-release
[angularjs conventions]: https://github.com/ajoslin/conventional-changelog/blob/master/conventions/angular.md
