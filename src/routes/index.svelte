<script lang="ts">
  import Footer from "$lib/Footer.svelte";
  import CursorItem from "$lib/CursorItem.svelte";

  const cursors = [
    "auto",
    "default",
    "none",
    "context-menu",
    "help",
    "pointer",
    "progress",
    "wait",
    "cell",
    "crosshair",
    "text",
    "vertical-text",
    "alias",
    "copy",
    "move",
    "no-drop",
    "not-allowed",
    "all-scroll",
    "col-resize",
    "row-resize",
    "n-resize",
    "s-resize",
    "e-resize",
    "w-resize",
    "ns-resize",
    "ew-resize",
    "ne-resize",
    "nw-resize",
    "se-resize",
    "sw-resize",
    "nesw-resize",
    "nwse-resize",
  ];

  const cursors1 = [
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
    "grab",
    "grabbing",
    "help",
    "move",
    "n-resize",
    "ne-resize",
    "nesw-resize",
    "ns-resize",
    "nw-resize",
    "nwse-resize",
    "no-drop",
    "none",
    "not-allowed",
    "pointer",
    "progress",
    "row-resize",
    "s-resize",
    "se-resize",
    "sw-resize",
    "text",
    "url(https://timesofindia.indiatimes.com/photo/67586673.cms)",
    "w-resize",
    "wait",
    "zoom-in",
    "zoom-out",
  ].sort();
</script>

<main class="px-4 w-full">
  <header class="mt-20 mb-8 max-w-sm mx-auto">
    <h1 class="text-6xl text-pink-600 font-bold text-center mb-4">Cursors</h1>
    <h2 class="text-gray-500 text-center leading-relaxed">
      Cursors available in CSS. Click to copy. <br /> Use in CSS with
      <span class="font-mono text-pink-400">cursor: &lbrace;name&rbrace;</span>
    </h2>
  </header>

  <div class="grid gap-1 grid-cols-2 md:grid-cols-4 max-w-3xl mx-auto">
    {#each cursors as cursor, index}
      <CursorItem {cursor} />
    {/each}
  </div>

  <Footer />
</main>
