<script>
  import { createEventDispatcher } from 'svelte';
  
	const dispatch = createEventDispatcher();
  export let todo;

	const deleteTodo = () => dispatch('delete');
</script>

<li>
  {todo}
  <button on:click={deleteTodo}>
    Remove
  </button>
</li>

<style>
  li {
    display: flex;
    justify-content: space-between;
  }
</style>