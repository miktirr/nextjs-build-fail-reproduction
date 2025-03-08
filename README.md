## Minimal reproduction of Next.js build fail with vanilla-extract and edge runtime

The Next.js version 15.2.0 broke the compatibility with [vanilla-extract](https://vanilla-extract.style). With vanilla-extract installed the build fails to compile:

```
> next build

   ▲ Next.js 15.2.2-canary.4

   Creating an optimized production build ...
Failed to compile.

Conflict: Multiple assets emit different content to the same filename middleware-manifest.json


> Build failed because of webpack errors
```

Note:

- The fail happens only with a clean build. You can reproduce the error by running: `rm -rf .next && pnpm build`.
- The problem is related to edge runtime, [see layout.tsx](https://github.com/miktirr/nextjs-build-fail-reproduction/commit/312509ae4b958c3fa8afd21d17b20509ec468880).
