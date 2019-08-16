<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  export let todo;

  function deleteTodo() {
    dispatch('delete', {
      id: todo.id
    });
  }
</script>

<style>
  li {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .todo {
    padding: 1.25em 0 1.25em 0.25em;
    border-bottom: 1px solid #b0bec5;
    line-height: 1;
  }

  .todo:last-of-type {
    border-bottom: 0;
  }

  .done {
    text-decoration: line-through;
  }

  .checkbox {
    margin: 0 0.25em 0 0;
    vertical-align: top;
  }

  button {
    line-height: 1em;
    margin: 0;
    color: #263238;
    font-weight: bold;
    background: 0;
    border: 0;
    cursor: pointer;
  }
</style>

<li class="todo">
  <label>
    <input class="checkbox" type="checkbox" bind:checked={todo.done} />
    <span class:done={todo.done}>{todo.text}</span>
  </label>
  <button type="button" title="delete item" on:click={deleteTodo}>&times;</button>
</li>
