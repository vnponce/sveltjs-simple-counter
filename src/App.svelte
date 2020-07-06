<script>
	import Counter from './components/Counter.svelte'
	// export - Values that are passed in as props
	export let name;
</script>

<main>
	<h1>Hello {name}!</h1>
	<Counter />
	<Counter inferior={2} superior={8}/>
<!--	If we set inferior = 2 and superior = 8 as variables above we can set those properties like -->
<!--	<Counter {inferior} {superior}/>-->
<!--	instead of -->
<!--	<Counter inferior={inferior} superior={superior}/>-->
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