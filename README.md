# micro-should

Ultra-simple testing framework without dependencies. Supports async cases.

Works with any assertion library.

> npm install micro-should

![](https://raw.githubusercontent.com/paulmillr/micro-should/ab36ccc16635545d80df7cbacf5aedaeda6756ce/screenshot.png)

## Usage

```js
const {should} = require("micro-should");

// Built-in node.js assertion lib.
// You can use any other library, like Chai.js or Expect.js.
const assert = require("assert");

should("add two numbers together", () => {
  assert.equal(2 + 2, 4);
});

should("catch errors", () => {
  assert.throws(() => { throw new Error("invalid"); });
});

should("produce correct promise result", async () => {
  const fs = require("fs").promises;
  const data = await fs.readFile("README.md", "utf-8");
  assert.ok(data.includes("Minimal testing"));
});

// should.only("execute only one test", () => {
//   assert.ok(true);
// });

// should.skip("disable one test by using skip", () => {
//   assert.ok(false); // would not execute
// })

// Execute this at the end of a file.
should.run();
```

## License

MIT (c) Paul Miller (https://paulmillr.com), see LICENSE file.
