## Pre Process

Run `npm i`

## REPL steps

1. `module` is `commonjs` pattern.

Run `npx tsc --noEmit`.
Then below errors come.

```
node_modules/@types/cacheable-request/index.d.ts(26,42): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(77,51): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(81,69): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(84,71): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(89,51): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(95,51): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(104,51): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(108,70): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(112,73): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(115,76): error TS2709: Cannot use namespace 'ResponseLike' as a type.
node_modules/@types/cacheable-request/index.d.ts(118,60): error TS2709: Cannot use namespace 'ResponseLike' as a type.
```

2. `module` is `ESNext` pattern.

Run `npx tsc --noEmit`.
No error comes.

## How to Fix it

After change require to import statement.
THen both `commonjs` and `ESNext` don't get error.

```diff
// node_modules/@types/cacheable-request/index.d.ts
- import ResponseLike = require('responselike');
+ import ResponseLike from 'responselike';

```
