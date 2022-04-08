<script>
  export let task;
  export let completed;
  export let added;
  export let id;
  export let deleteTask;
  export let toggleTask;
</script>

<li class="todoitem">
  <p>{task}</p>
  <button on:click={() => toggleTask(id)}>
    {#if completed}
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
        class="bi bi-bag-check-fill"
        viewBox="0 0 16 16"
      >
        <path
          fill-rule="evenodd"
          d="M10.5 3.5a2.5 2.5 0 0 0-5 0V4h5v-.5zm1 0V4H15v10a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V4h3.5v-.5a3.5 3.5 0 1 1 7 0zm-.646 5.354a.5.5 0 0 0-.708-.708L7.5 10.793 6.354 9.646a.5.5 0 1 0-.708.708l1.5 1.5a.5.5 0 0 0 .708 0l3-3z"
        />
      </svg>
    {:else}
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
        class="bi bi-app"
        viewBox="0 0 16 16"
      >
        <path
          d="M11 2a3 3 0 0 1 3 3v6a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3V5a3 3 0 0 1 3-3h6zM5 1a4 4 0 0 0-4 4v6a4 4 0 0 0 4 4h6a4 4 0 0 0 4-4V5a4 4 0 0 0-4-4H5z"
        />
      </svg>
    {/if}
  </button>
  <button on:click={() => deleteTask(id)}>Delete</button>
</li>
