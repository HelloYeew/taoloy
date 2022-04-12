<script>
	import CoffeeRecipe from "./CoffeeRecipe.svelte";
</script>

<main>
	<img
		src="https://rulesets.info/media/profile_pics/somlek.png"
		alt="Somlek"
	/>

	<h1 class="text-light">Taoloy</h1>
	<h2 class="text-light">Don't know what coffee you want to drink today?</h2>
	<h2 class="text-light">Let us think!</h2>

	<CoffeeRecipe />
</main>

<style>
	main {
		margin: auto;
	}
</style>
