SvelteKit project configured to generate and auto-load source maps, both in the server and in the client.

Instructions:

1. `npm run build`, `npm run preview`
2. load the page, a client-side error is thrown
3. uncomment the server-side error in `src/routes/+page.svelte`, `npm run build`, `npm run preview`
4. reload the page, a server-side error is thrown

At 2. the stack trace in the browser is correctly source mapped.
At 4. the stack trace in Node is correctly source mapped.

Changes wrt default SvelteKit project:

- add code to throw errors in `src/routes/+page.svelte`
- edit `preview` script as `NODE_OPTIONS=--enable-source-maps vite preview` in `package.json`
- add `build: { sourcemap: true }` in `vite.config.ts`

Refs: https://github.com/sveltejs/kit/issues/7320
