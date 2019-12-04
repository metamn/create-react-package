# create-react-package

A quick help to create a react package. Not automatic, but at least simple and works with hooks, too.

!! NOTICE !!
It works until the package is updated.
After then in `/example` the `yarn` command enters in an endless loop lost in the cache

```
erbose 27.698079899 Copying "/home/cs/metamn/use-query-filters/example/node_modules/relateurl/lib/relate/relativize.js" to "/home/cs/.cache/yarn/v6/npm-use-query-filters-0.1.0-a854482c-05f3-46c0-9ddd-e8267f048d90-1575461971740/node_modules/use-query-filters/example/node_modules/relateurl/lib/relate/relativize.js".
```

## What's inside

```sh
/src # the package
/example # a CRA using the package
```

## How to use

```sh
# 1. develop in /src
# 2. build the package locally
yarn build
# 3. in /example the package is refreshed because of `yarn add /home/cs/metamn/use-query-filters`
```

## Create a new package

This tutorial just works perfectly: [Building a React component as an NPM module](https://medium.com/recraftrelic/building-a-react-component-as-a-npm-module-18308d4ccde9)

```sh
npm init
yarn add @babel/cli @babel/core --dev
yarn add @babel/preset-env @babel/preset-react --dev
yarn add react react-dom --dev

touch .babelrc
{
    "presets": ["@babel/preset-react", "@babel/preset-env"]
}

mkdir src
cd src
touch index.js
import React, { Component } from 'react';

export default class DummyComponent extends Component {

    render () {

        return (
            <div>I am a dummy react npm module</div>
        )

    }

}

cd ..
nano package.json
"scripts": {
    "build": "./node_modules/.bin/babel src --out-file index.js"
  },

yarn build

cra example
cd example
yarn add /home/cs/metamn/use-query-filters
```

### Additionally ...

```#!/bin/sh
y add --dev react-scripts
nano package.json
"scripts": {
    "build": "./node_modules/.bin/babel src --out-file index.js"
  },

```

## Resources

- [Building a React component as an NPM module](https://medium.com/recraftrelic/building-a-react-component-as-a-npm-module-18308d4ccde9)
