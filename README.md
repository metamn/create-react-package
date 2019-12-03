# create-react-package

## Steps

This tutorial just works perfectly: [Building a React component as an NPM module](https://medium.com/recraftrelic/building-a-react-component-as-a-npm-module-18308d4ccde9)

```
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


## Resources

- [Building a React component as an NPM module](https://medium.com/recraftrelic/building-a-react-component-as-a-npm-module-18308d4ccde9)
