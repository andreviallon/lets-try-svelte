<script>
	import AddTodo from './AddTodo.svelte';
	import Todo from './Todo.svelte';
	
	let name = 'svelte';
	let appName = 'todo';
	let todos = ['Clean the house', 'Buy some milk', 'Code an awesome app', '4'];

	function handleSubmit(todo) {
		todos = [...todos, todo];
	}

	function handleDelete(i) {
		todos = todos.filter((todo, index) => index !== i);
	}
</script>

<h1>Hello {name}!</h1>
<h2>Let's build a {appName} app</h2>

<main>
	<div class="grid">
		<AddTodo on:submit={(todo) => handleSubmit(todo.detail)} />
		<ul>
			{#each todos as todo, i}
			<Todo todo={todo} on:delete={() => handleDelete(i)} />
		{/each}
		</ul>
	</div>
</main>

<style>
	h1 {
		font-size: 28px;
		text-align: center;
	}

	h2 { 
		font-size: 20px;
		text-align: center;
	}

	main {
		max-width: 500px;
		margin: 3rem auto 0;
	}

	ul {
		padding: 0;
	}
</style>