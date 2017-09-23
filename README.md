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

## Simple Start

Let's create a .js file and write a normal function, in our case, a 'sum.js' file in root directory.
```
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```

Then, create a directory called '__test__', and create a file named sum.test.js.
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
