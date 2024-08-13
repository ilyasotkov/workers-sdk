---
"miniflare": patch
---

fix: `getPlatformProxy` errors from RPC methods are missing the `.remote` property, have `.cause` set to `undefined`

This fix makes `getPlatformProxy` behavior more consistent with `workerd` so that errors thrown from an RPC method and proxied to a Node.js environment have the `.remote` property set to `true` and won't any any more have the property `.cause` (before the fix, it would always be present but set to `undefined`).
