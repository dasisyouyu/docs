---
title: "API: The Renderer Module"
description: Nuxt Renderer Module
---

# Renderer Module

- Source: **[core/renderer.js](https://github.com/nuxt/nuxt.js/blob/dev/lib/core/renderer.js)**

This module is exporting a connect middleware which handles and serves all SSR and asset requests.

## Tapable plugins

We can register hooks on certain life cycle events.

```js
nuxt.plugin('renderer', renderer => {
    renderer.plugin('setupMiddleware', app => {
        // 
    })
})
```

Plugin               | Arguments                 | When
---------------------|---------------------------|--------------------------------------------------------------------------------
`ready`              | renderer                  | SSR Middleware and all resources are ready
`setupMiddleware`    | connect instance (app)    | Before nuxt adds it's middleware stack. We can use it to register custom server side middleware.