<script>
  let todos = [];
  let todo = "";

  function handleAddTodo() {
    todos = [todo, ...todos];
    todo = "";
  }

  function handleCheckToDo(todoIndex) {
    todos = todos.filter((todo, index) => todoIndex !== index);
  }
  //$: console.log({ todos });
</script>

<style>
  li {
    padding: 10px;
    margin: 2px;
  }
  ul {
    list-style: square;
  }
  span {
    cursor: pointer;
    color: cadetblue;
  }
</style>

<h1>Simple Todos App</h1>
<input type="text" bind:value={todo} />
<button on:click={handleAddTodo}>Add</button>
<ul>
  {#each todos as todoItem, index}
    <li>
      {todoItem}
      <span on:click={() => handleCheckToDo(index)}>check</span>
    </li>
  {/each}
</ul>
