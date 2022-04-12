<script>
	import CoffeeRecipe from "./CoffeeRecipe.svelte";
</script>

<style>

</style>

<h1>Taoloy</h1>
<h2>Don't know what coffee you want to drink today?</h2>
<h2>Let us think!</h2>

<CoffeeRecipe />

<button type="button" class="btn btn-primary" on:click={CoffeeRecipe}>Random a new one!</button>