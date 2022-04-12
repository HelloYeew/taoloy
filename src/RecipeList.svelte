<script>
	// TODO: Fix this.
	// Put recipes in another file
	import { recipes } from "./recipes";
	import {createEventDispatcher} from "svelte";
	const dispatch = createEventDispatcher();

	function navigateBack() {
		dispatch("navigate");
	}

</script>

<section>
	<h1>Recipe List</h1>
	<!-- TODO: Make it a card -->
	{#each recipes as rec}
		<div class="card">
			<div class="card-content" style="color: black;">
				<h3>{rec.name}</h3>
				<p>Ingredients : {rec.ingredients}</p>
				<p>Instructions : {rec.instructions}</p>
			</div>
		</div>
	{/each}
	<button type="button" class="btn btn-primary" on:click={navigateBack}>
		Back
	</button>
</section>

<style>
	section {
		/* CSS Variable from Bootstrap */
		color: var(--bs-white);
	}
</style>
