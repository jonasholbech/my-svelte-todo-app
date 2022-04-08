<script>
  import Form from "./Form.svelte";
  import TodoItem from "./TodoItem.svelte";

  let tasks = [
    {
      id: Math.random(),
      task: "Clean House",
      completed: false,
      added: Date.now(),
    },
  ];

  function addTask(newTask) {
    tasks = tasks.concat(newTask);
  }
  function deleteTask(id) {
    console.log(id);
    tasks = tasks.filter((item) => item.id !== id);
  }
  function toggleTask(id) {
    tasks = tasks.map((item) => {
      if (item.id === id) {
        item.completed = !item.completed;
      }
      return item;
    });
  }
</script>

<Form {addTask} />
<section>
  <ol>
    {#each tasks as task}
      <TodoItem {...task} {deleteTask} {toggleTask} />
    {/each}
  </ol>
</section>
