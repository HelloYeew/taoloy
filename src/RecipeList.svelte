<script>
	// TODO: Fix this.
	// Put recipes in another file
	import { recipes } from "./recipes";
</script>

<section>
	<h1>Recipe List</h1>
	<!-- TODO: Make it a card -->
	{#each recipes as rec}
		<h2>{rec.name}</h2>
	{/each}
</section>

<style>
	section {
		/* CSS Variable from Bootstrap */
		color: var(--bs-white);
	}
</style>
