<script lang="ts">
  import type { ITodoItem } from "../types";
  import { createEventDispatcher } from "svelte";

  export let item: ITodoItem;

  const dispatch = createEventDispatcher();

  const onCheck = () => dispatch("check", { completed: !item.completed });
</script>

<li>
  <label>
    <input type="checkbox" checked={item.completed} on:change={onCheck} />
    <span class="pl-2 text-lg">{item.text}</span>
  </label>
</li>
