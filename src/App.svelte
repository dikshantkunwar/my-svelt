<script>
	export let name, count = 0;

	function incrementCount() {
		count += 1;
	}

	function decrementCount() {
		count -= 1;
	}

	function resetCount() {
		count = 0;
	}
</script>

<main>
	<button on:click={incrementCount}>
		Clicked {count} {count === 1 ? 'time': 'times'}
	</button>
	<button on:click={decrementCount}> - </button>
	<button on:click={resetCount}> RESET </button>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>