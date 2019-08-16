<script>
  let todos = [];
	let newTodo = '';

  function addTodo() {
    todos = [...todos, {
      description: newTodo,
      done: false,
    }]
    newTodo = '';
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
    width: 72%;
  }

  button {
    color: #fff;
    background: #263238;
    font-weight: 600;
  }
</style>

<ul>
	{#each todos as todo}
		<li>{todo.description}</li>
  {:else}
    <li class="no-todos">No todos yet. Try adding one!</li>
	{/each}
</ul>

<form on:submit|preventDefault={addTodo}>
  <input type="text" bind:value={newTodo} placeholder="try svelte later" />
  <button type="submit">Add Todo</button>
</form>
