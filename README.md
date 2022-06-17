# Vite esmbuild issue

This is a minimal React application created with Vite. The only change I have
made is to convert the `App` component from a function to a function expression
using an arrow function. As soon as I do this, `npm run dev` starts showing this
error:

```
[vite] hmr update /src/App.tsx
[vite] warning: Top-level "this" will be replaced with undefined since this file is an ECMAScript module
23 |          lineNumber: 11,
24 |          columnNumber: 9
25 |        }, this), /*#__PURE__*/_jsxDEV("p", {
   |           ^
26 |          children: "Hello Vite + React!"
27 |        }, void 0, false, {

  Plugin: vite:esbuild
  File: /Users/naresh/projects/vite-esmbuild-issue/src/App.tsx
```

## How to reproduce

```shell
npm ci
npm run dev
```

## Comments

This issue has started appearing with esmbuild v0.14.45. It did not exist with
esmbuild v0.14.44. Vite is starting to pick up v0.14.45 now, which is causing
this issue.

Please see https://github.com/evanw/esbuild/issues/2328 for further discussion.
