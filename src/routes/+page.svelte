<main>
  <section class="todo">
    <form class="todo-form">
      <input type="text" class="todo-input" />
      <button class="todo-add"> Add </button>
    </form>
    <ul class="tasks">
      <li class="task">
        <p class="task-text"></p>
        <button class="task-btn task-btn-execute">&#10004;</button>
        <button class="task-btn task-btn-delete">&#10006;</button>
      </li>
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
</style>
