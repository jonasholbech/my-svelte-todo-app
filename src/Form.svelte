<script>
  let task;
  export let addTask;
  function submit(e) {
    addTask({
      task: task,
      id: Math.random(),
      completed: false,
      added: Date.now(),
    });
    task = "";
  }
</script>

<form on:submit|preventDefault={submit}>
  <label for="task">Task</label>
  <input type="text" bind:value={task} id="task" name="task" />
  <button>Add Task</button>
</form>
