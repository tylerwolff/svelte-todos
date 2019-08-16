<script>
	import Todos from './Todos.svelte';
</script>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		-webkit-font-smoothing: antialiased;
	}

	.wrapper {
		max-width: 400px;
		margin: 0 auto;
	}

	.add-margins {
		margin-top: 3em;
		margin-bottom: 3em;
	}

	header {
		padding: 0.25em 0;
		background:	#37474f;
		box-shadow: 0 1px 3px rgba(0,0,0,0.5);
	}

	.flex {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	h1 {
		color: #fff;
	}

	.github {
		float: right;
		color: rgba(255,255,255,0.75);
		font-size: 0.875em;
	}
</style>

<header>
	<div class="wrapper flex">
		<h1>Svelte todos</h1>
		<a class="github" href="https://github.com">github →</a>
	</div>
</header>
<div class="wrapper add-margins">
	<Todos />
</div>
