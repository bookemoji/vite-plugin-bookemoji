# vite-plugin-bookemoji

This is the Vite plugin that powers the [bookemoji.dev](https://bookemoji.dev) experience.

It exists to create virtual files for the bookemoji package to access from user-land.

## Key Detail

In order for this plugin to work yyou need to set it/it's library as excluded:

```diff

import { sveltekit } from "@sveltejs/kit/vite";
import { defineConfig } from "vite";
import { bookemoji } from "bookemoji/vite";

export default defineConfig({
  plugins: [sveltekit(), bookemoji()],
+  optimizeDeps: {
+    exclude: ["bookemoji"],
+  },
  server: {},
});


```
