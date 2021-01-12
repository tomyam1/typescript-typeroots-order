# typescript-typeroots-order
> Test whether the order of directories in typeRoots matter

## It does

```
> npx tsc --project tsconfig.a-first.json

src/src.ts:1:23 - error TS2724: '"foo"' has no exported member named 'OnlyB'. Did you mean 'OnlyA'?

1 import { OnlyA, Both, OnlyB } from 'foo'
                        ~~~~~


$ npm run b-first

> @tepez/typescript-typeroots-order@0.0.0 b-first c:\code\typescript-typeroots-order
> tsc --project tsconfig.b-first.json

src/src.ts:1:10 - error TS2724: '"foo"' has no exported member named 'OnlyA'. Did you mean 'OnlyB'?

1 import { OnlyA, Both, OnlyB } from 'foo'
           ~~~~~

src/src.ts:4:14 - error TS2322: Type '"a"' is not assignable to type '"b"'.

4 export const both: Both = 'a';
               ~~~~
```