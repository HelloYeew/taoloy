<script>
	import { createEventDispatcher } from "svelte";
	const dispatch = createEventDispatcher();

	let isOrdered = false;
	let isProcessing = true;

	function navigateToBack() {
		dispatch("navigate");
	}

	function order() {
		isOrdered = true;
		setTimeout(() => {
			isProcessing = false;
		}, 3000);
	}
</script>

<section>
	<h1>Coffee Order</h1>
	{#if !isOrdered}
		<h2>Please input your budget (Baht)</h2>
		<input type="number" name="budget" id="budget" />
		<h2>Please select app to order</h2>
		<button on:click={order} type="button">Delivery App 1</button>
		<button on:click={order} type="button">Delivery App 2</button>
		<button on:click={order} type="button">Delivery App 3</button>
		<p>Please wait a while until we got your order.</p>
	{:else if isProcessing}
		<h2>Please wait...</h2>
	{:else}
		<h2>Your order is ready</h2>
		<p>Latte from Somlek's Cafe</p>
		<p>
			Somlek's cafe is famous for homemade coffee with special grade
			coffee.
		</p>
	{/if}
	<button type="button" class="btn btn-info" on:click={navigateToBack}>
		Back
	</button>
</section>

<style>
	section {
		background-color: inherit;
		/*
        CSS Variable from Bootstrap
        */
		color: var(--bs-light);
	}
	ul {
		list-style: none;
		padding-left: 0;
	}
	pre {
		font-family: inherit;
		font-size: inherit;
	}
</style>
