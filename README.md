# babel-preset-flow-syntax

This is an extension of the official [flow][preset-flow] that is supposly is a:

> Babel preset for all Flow plugins.

But there are certain features like [class properties syntax][] that flow
supports out of the box while babel requires [transform-class-properties][]
plugin in order to be able to parse it.


> Babel preset that supports full flow syntax.

This preset includes the following plugins & presets:

- [preset-flow]()
- [transform-class-properties][]

## Example

**In**

```javascript
function foo(one: any, two: number, three?): string {}
```

**Out**

```javascript
function foo(one, two, three) {}
```

## Installation

```sh
npm install --save-dev babel-preset-flow
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "presets": ["flow-sytax"]
}
```

### Via CLI

```sh
babel --presets flow-syntax script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  presets: ["flow-syntax"]
});
```

[preset-flow]:https://babeljs.io/docs/plugins/preset-flow/
[class properties syntax]:https://tc39.github.io/proposal-class-public-fields/
[transform-class-properties]:https://babeljs.io/docs/plugins/transform-class-properties/