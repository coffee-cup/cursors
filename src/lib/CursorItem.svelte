<script lang="ts">
  import copy from "copy-text-to-clipboard";

  export let cursor: string = "";
  let copied = false;

  const onClick = () => {
    copy(cursor);
    copied = true;
    setTimeout(() => {
      copied = false;
    }, 2000);
  };
</script>

<button
  class="cursor-{cursor} bg-gray-100 py-8 px-4 font-medium flex items-center justify-center rounded-sm focus:outline-none relative"
  style="cursor: {cursor}"
  on:click={onClick}
>
  {#if copied}<span class="animate-bounce"> 👍👍👍 </span>{:else}{cursor}{/if}
</button>
