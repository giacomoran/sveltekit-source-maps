<script lang="ts">
  import { browser } from "$app/environment";

  // Run some JS code, otherwise client error stack trace won't include this
  // file, for some reason.
  console.log("Loaded in ", browser ? "client" : "server");

  if (browser) {
    throw new Error("Some client error.");
  } else {
    // Uncomment to throw server error
    // throw new Error("Some server error.");
  }
</script>

<h1>Welcome to SvelteKit</h1>
<p>
  Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
</p>
