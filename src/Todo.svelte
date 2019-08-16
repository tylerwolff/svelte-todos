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
  .todo {
    padding: 1.25em 0 1.25em 0.25em;
    border-bottom: 1px solid #b0bec5;
  }

  .todo:last-of-type {
    border-bottom: 0;
  }

  button {
    float: right;
    height: 1em;
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
  {todo.text}
  <button type="button" title="delete item" on:click={deleteTodo}>&times;</button>
</li>
