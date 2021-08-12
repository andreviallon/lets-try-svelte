<script>
  import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();
  let input = '';

	const submit = () => dispatch('submit', input);
</script>

<p>Add todo</p>
<form class="grid" on:submit|preventDefault={submit}>
  <input class="form-input" bind:value={input}>
  <input class="btn" type="submit" value="Add todo">
</form>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));
		gap: 1rem;
	}

	.form-input {
		grid-column: span 2 / span 2;
	}

	.btn {
		grid-column: span 1 / span 1;
	}
</style>