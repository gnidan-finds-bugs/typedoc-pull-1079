Bug Demo Repo
=============

Looks like `excludeNotExported` causes namespaced re-exports to be omitted from
docs output:

```typescript
import * as Utils from "./utils";
export { Utils }; // doesn't show up when using --excludeNotExported
```


Reproduction Steps
------------------

```
$ git clone git@github.com/gnidan-finds-bugs/typedoc-pull-1079.git
$ cd typedoc-pull-1079
$ npm install
$ npm run docs-no-exports
```

Output is in `docs/`... notice the lack of `Utils` module.

(For comparison: if you run `npm run docs-with-exports` instead, `Utils` is
there)
