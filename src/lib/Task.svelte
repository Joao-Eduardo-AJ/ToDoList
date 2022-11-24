<script lang="ts">
  export let content: string;
  export let completed: boolean;
</script>

<div
  class="flex w-full border border-neutral-300 shadow-sm p-2 rounded-md space-x-2 "
>
  <input
    type="checkbox"
    bind:checked={completed}
    class="ml-2 cursor-pointer accent-red-300 font-semibold"
  />
  <input
    type="text"
    bind:value={content}
    disabled={completed}
    class="pl-2 py-1 disabled:opacity-30 disabled:line-through w-full"
  />
</div>
