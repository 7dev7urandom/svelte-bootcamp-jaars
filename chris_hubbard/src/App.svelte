<script lang="ts">
	import Navbar from "./Navbar.svelte";
	import Router from 'svelte-spa-router'
	import routes from "./routes"

	let Pages = [
		{ url: "/", label: "Home" },
		{ url: "/#/counter", label: "Counter"},
		{ url: "/#/input", label: "Input"},
		{ url: "/#/fetch", label: "Fetch"},
	]
</script>



<Navbar navlists={Pages}/>

<main>
	<Router {routes} />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		padding-top: 0;
		max-width: 240px;
		margin: 0 auto;
	}
	 
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

</style>
