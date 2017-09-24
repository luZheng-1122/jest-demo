# jest-demo
Hi there, this is a simple demo of unit-testing in react with jest. Learn from: [testing-javascrpt](https://github.com/kentcdodds/testing-workshop)

## Get Started
The demo invovles [yarn](https://yarnpkg.com/en/), [jest](http://facebook.github.io/jest/) and [react](https://facebook.github.io/react/).
### setup

1. yarn

```
brew install yarn
yarn init
```

2. jest

```
yarn add --dev jest
```
Add the following section to your package.json:
```
{
  "scripts": {
    "test": "jest"
  }
}
```

3. react

Since this demo is more about testing, so it does not include react setup.

### install babel
```
yarn add --dev babel-core babel-preset-env
```
then add ".babelrc":
```
{
    "presets" : ["env"]
}
```


## Simple Start

Let's create a .js file and write a normal function, in our case, a 'sum.js' file in root directory.
```
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```

Then, create a directory called `__test__`, and create a file named sum.test.js.
```
const sum = require('../sum'); //pay attention to the path

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

Finally, run **yarn test** to get our test result:
```
$ jest
 PASS  __test__/sum.test.js
  ✓ adds 1 + 2 to equal 3 (7ms)
```

## code coverage
> code coverage is basically about how much our code is been run.
```
"scripts": {
    "test": "jest --coverage",
    "test:watch": "jest --watch" //watch mode to quickly respond to your change
  }
```

if some files are not been imported at all, jest will report that as well, but need to add this:

```
"jest": {
    "collectCoverageFrom": [
      "*.js"
    ]
  }
```