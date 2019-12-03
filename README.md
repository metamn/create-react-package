# create-react-package

A quick help to create a react package. Not automatic, but at least simple and works with hooks, too.

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

## Resources

- [Building a React component as an NPM module](https://medium.com/recraftrelic/building-a-react-component-as-a-npm-module-18308d4ccde9)
