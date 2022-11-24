<script lang="ts">
  import Task from '$lib/Task.svelte';

  interface ITask {
    text: string;
    completed: boolean;
  }

  let tasks: ITask[] = [];

  function addTask() {
    tasks = [
      ...tasks,
      {
        text: 'Digite aqui sua tarefa!',
        completed: false,
      },
    ];
  }
</script>

<div
  class="mt-10 p-4 h-fit flex justify-start items-center flex-col space-y-2 max-w-lg mx-auto"
>
  <button
    class="bg-red-200 active:bg-red-100 border-2 active:border-neutral-300 border-neutral-400 border-dashed p-3 rounded-lg w-full flex justify-center items-center space-x-2 text-neutral-500 font-semibold hover:border-neutral-400 active:text-neutral-400 transition-all"
    on:click={addTask}
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="w-6 h-6"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M12 9v6m3-3H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"
      />
    </svg>

    <span>Adicionar Tarefa!</span></button
  >
  {#each tasks as task}
    <Task content={task.text} completed={task.completed} />
  {/each}
</div>
