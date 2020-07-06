<script>
	import Counter from './components/Counter.svelte'
	// export - Values that are passed in as props
	export let name;
</script>

<main>
	<h1>Hello {name}!</h1>
	<Counter />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
</style>