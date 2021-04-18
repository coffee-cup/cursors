<script lang="ts">
  export let cursor: string = "";
</script>

<div
  class="cursor-{cursor} bg-gray-100 py-8 px-4 font-medium flex items-center justify-center rounded-sm"
  style="cursor: {cursor}"
>
  {cursor}
</div>
