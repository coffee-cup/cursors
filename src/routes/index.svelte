<script lang="ts">
  import CursorItem from "$lib/CursorItem.svelte";

  const cursors = [
    "alias",
    "all-scroll",
    "auto",
    "cell",
    "context-menu",
    "col-resize",
    "copy",
    "crosshair",
    "default",
    "e-resize",
    "ew-resize",
  ];
</script>

<main class="px-4 w-full">
  <header class="mt-12 mb-8 max-w-sm mx-auto">
    <h1 class="text-6xl text-pink-600 font-bold text-center mb-4">Cursors</h1>
    <h2 class="text-gray-500 text-center">
      List of all the possible cursors on the web <br /> Click to copy
    </h2>
  </header>

  <div class="grid gap-1 grid-cols-2 md:grid-cols-4 max-w-3xl mx-auto">
    {#each cursors as cursor, index}
      <CursorItem {cursor} />
    {/each}
  </div>
</main>
