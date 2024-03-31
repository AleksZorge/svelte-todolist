<script>
  let todoList = [];
  let task = "";

  function handleAddTask() {
    todoList = [
      {
        task: task,
        status: "pending",
      },
      ...todoList,
    ];
    task = "";
  }
  function handleExecuteTask(index) {
    todoList[index].status = "completed";
    todoList = [...todoList];
  }
  function handleRemoveTask(index) {
    todoList.splice(index, 1);
    todoList = [...todoList];
  }
</script>

<main>
  <section class="todo">
    <form class="todo-form">
      <input type="text" class="todo-input" bind:value={task} />
      <button class="todo-add" on:click={handleAddTask}> Add </button>
    </form>
    <ul class="tasks">
      {#each todoList as todo, i}
        <li class="task">
          <p
            class="task-text {todo.status == 'completed'
              ? 'task-text-crossed'
              : ''}"
          >
            {todo.task}
          </p>
          <button
            class="task-btn {todo.status == 'completed'
              ? 'task-btn-active'
              : ''}"
            on:click={() => {
              handleExecuteTask(i);
            }}>&#10004;</button
          >
          <button
            class="task-btn"
            on:click={() => {
              handleRemoveTask(i);
            }}>&#10006;</button
          >
        </li>
      {/each}
    </ul>
  </section>
</main>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  main {
    background-color: rgb(114, 114, 114);
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .todo {
    padding: 20px;
    background-color: rgb(28, 28, 28);
    width: 250px;
    border-radius: 20px;
  }
  .todo-form {
    margin: 20px 0px;
    display: flex;
  }
  .todo-input {
    margin: 20px 0px;
    border: 1px solid rgb(167, 58, 58);
    height: 40px;
    outline: none;
    border-radius: 20px;
    flex: 1;
    text-indent: 20px;
  }
  .todo-add {
    margin: 20px 0px;
    font-size: 1rem;
    border: 1px solid rgb(167, 58, 58);
    height: 40px;
    outline: none;
    border-radius: 20px;
    width: 60px;
    margin-left: 5px;
    color: rgb(167, 58, 58);
    cursor: pointer;
  }
  .tasks {
    min-height: 100px;
  }
  .task {
    margin: 10px 0px;
    display: flex;
  }
  .task-text {
    flex: 1;
    color: #f5f5f5;
    font-size: 1.25rem;
    margin: 0px 5px;
  }
  .task-btn {
    width: 25px;
    height: 25px;
    border: 1px solid rgb(167, 58, 58);
    color: rgb(167, 58, 58);
    border-radius: 50%;
    margin: 0px 5px;
    cursor: pointer;
  }
  .task-btn-active {
    background: rgb(167, 58, 58);
    color: #f5f5f5;
  }
  .task-text-crossed {
    text-decoration: line-through;
    text-decoration-color: rgb(167, 58, 58);
  }
</style>
