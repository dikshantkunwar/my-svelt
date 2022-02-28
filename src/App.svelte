<script>
	import Nested from './Nested.svelte';
	import Info from './Info.svelte';
	import Cats from './Cats.svelte';

	const pkg = {
		name: 'svelte',
		version: 3,
		speed: 'blazing',
		website: 'https://svelte.dev'
	};

	let user = { loggedIn: false };

	export let name, count = 0;
	let numbers = [1, 2, 3, 4];

	$: if (count >= 10) {
		alert('count is dangerously high!');
		count = 9;
	}

	$: sum = numbers.reduce((t,n) => t + n, 0);

	function addNumber() {
		// numbers.push(numbers.length + 1);
		numbers = [...numbers, numbers.length + 1];
	}

	function incrementCount() {
		count += 1;
	}

	function decrementCount() {
		count -= 1;
	}

	function resetCount() {
		count = 0;
	}

	function toggle() {
		user.loggedIn = !user.loggedIn;
	}
</script>

<main>
	{#if user.loggedIn}
		<button on:click={toggle}>Log out</button>
	{:else}
		<button on:click={toggle}>Log in</button>
	{/if}

	<br>
	<p>User is {user.loggedIn ? 'ONLINE :)': 'OFFLINE :('}</p>
	<button on:click={incrementCount}>
		Clicked {count} {count === 1 ? 'time': 'times'}
	</button>
	<button on:click={decrementCount}> - </button>
	<button on:click={resetCount}> RESET </button>
	<h1>Hello {name}!</h1>

	<p>{numbers.join(' + ')} = {sum}</p>
	<button on:click={addNumber}>Add a number</button>

	<Nested answer={55} />
	<Nested />

	<Cats />

	<Info {...pkg} />
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