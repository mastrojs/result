# @mastrojs/result

An extremely simple `Result` type. Return either an `Ok` or `Err` instead of throwing an exception.

Exceptions in TypeScript are not type-safe, and it's often hard to know whether a function can throw or not. For an introduction of the concept, see e.g. [Using Results in TypeScript](https://imhoff.blog/posts/using-results-in-typescript).


Inspired by Rust's `Result<T, E>` type (known as `Either` in some functional languages), this implementation is a minimal take on [ts-results](https://github.com/vultix/ts-results)'s approach. If you're looking for a more object-oriented alternative, see [neverthrow](https://npmx.dev/package/neverthrow). Unlike the `[data, error]` approach (used e.g. in Go), you don't risk getting the tuple index wrong.

## Usage

```ts
import { Ok, Err, type Result } from "@mastrojs/result";

const go = (): Result<string> =>
  Math.random()
    ? Ok("here is our result")
    : Err("Oh noes");

const res = go();
if (res.ok) {
  console.info(res.val);
} else {
  console.error(res.error);
}
```

To see all functions `@mastrojs/result` exports, see its [API docs](https://jsr.io/@mastrojs/result/doc).


## Install

### Deno

    deno add jsr:@mastrojs/result

### Node.js

    pnpm add jsr:@mastrojs/result

### Bun

    bunx jsr add @mastrojs/result
