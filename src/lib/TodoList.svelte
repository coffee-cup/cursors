<script lang="ts">
  import type { ITodoItem } from "../types";
  import TodoItem from "./TodoItem.svelte";

  let value = "";

  let list: ITodoItem[] = [
    { text: "One" },
    { text: "Two", completed: true },
    { text: "Three" },
  ];

  $: completed = list.filter(i => i.completed).length;
  $: total = list.length;

  const onCheck = (index: number, completed: boolean) => {
    list = list.map((item, i) => (i === index ? { ...item, completed } : item));
  };

  const handleSubmit = () => {
    console.log("handle submit!");
    list = [...list, { text: value }];
    value = "";
  };
</script>

<div class="mb-4 text-gray-500 text-sm flex space-x-4">
  <span>{completed} Completed</span>
  <span>{total} Total</span>
</div>

<ul>
  {#each list as item, index}
    <TodoItem {item} on:check={e => onCheck(index, e.detail.completed)} />
  {/each}
</ul>

<form
  on:submit|preventDefault={handleSubmit}
  class="flex w-full justify-between space-x-2 mt-4"
>
  <input
    bind:value
    placeholder="Value"
    class="border-2 rounded px-2 py-1 w-full hover:border-pink-500 focus:border-pink-500 focus:outline-none"
  />
  <button class="bg-blue-500 rounded text-white hover:bg-blue-400 px-2"
    >New</button
  >
</form>
