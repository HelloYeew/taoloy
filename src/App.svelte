<script>
	import CoffeeRecipe from "./CoffeeRecipe.svelte";
	import RecipeList from "./RecipeList.svelte";
	import Order from "./Order.svelte";

	// RECIPE | LIST | ORDER
	let currentPage = "RECIPE";

	function navigateToList() {
		currentPage = "LIST";
	}

	function navigateBack() {
		currentPage = "RECIPE";
	}

	function navigateToOrder() {
		currentPage = "ORDER";
	}
</script>

<main>
	<img
		src="https://rulesets.info/media/profile_pics/somlek.png"
		alt="Somlek"
	/>

	<h1 class="text-light">Taoloy</h1>
	<h2 class="text-light">Don't know what coffee you want to drink today?</h2>
	<h2 class="text-light">Let us think!</h2>

	{#if currentPage == "RECIPE"}
		<CoffeeRecipe on:navigate={navigateToList} on:order={navigateToOrder} />
	{:else if currentPage == "LIST"}
		<RecipeList on:navigate={navigateBack} />
	{:else}
		<Order on:navigate={navigateBack} />
	{/if}
</main>

<style>
	main {
		margin: auto;
	}
</style>
