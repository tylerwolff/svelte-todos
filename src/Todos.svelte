<script>
  import Todo from './Todo.svelte';

  let todos = [{
    id: 1,
    text: 'Try svelte later',
    done: false
  }, {
    id: 2,
    text: 'Walk the doge',
    done: false
  }];
	let newTodo = '';

  function addTodo() {
    todos = [...todos, {
      id: (new Date()).getTime(),
      text: newTodo,
      done: false,
    }]
    newTodo = '';
  }

  function deleteTodo(event) {
    const newTodos = todos.filter(t => t.id !== event.detail.id);
    todos = newTodos;
  }
</script>

<style>
  ul {
    list-style: none;
    padding: 0;
    margin-bottom: 2em;
  }

  .no-todos {
    color: #999;
  }

  form {
    display: flex;
    justify-content: space-between;
    align-content: center;
  }

  input, button {
    background-color: transparent;
    border: 1px solid WindowFrame;
    color: inherit;
    font: inherit;
    letter-spacing: inherit;
    padding: 0.75em 1em;
    border-radius: 4px;
  }

  input {
    width: 83%;
  }

  button {
    color: #fff;
    background: #263238;
    font-weight: 600;
    cursor: pointer;
  }
</style>

<ul>
	{#each todos as todo}
		<Todo todo={todo} on:delete={deleteTodo} />
  {:else}
    <li class="no-todos">No todos yet. Try adding one!</li>
	{/each}
</ul>

<form on:submit|preventDefault={addTodo}>
  <input type="text" bind:value={newTodo} placeholder="What to do?" />
  <button type="submit">Add</button>
</form>
