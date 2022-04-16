<script>
    import { createEventDispatcher } from "svelte";
    import { recipes } from "./recipes";

    // make a list of coffee recipes
    // random coffee recipe
    let recipe = recipes[Math.floor(Math.random() * recipes.length)];
    let ingredients = recipe.ingredients;
    const dispatch = createEventDispatcher();

    function randomRecipe() {
        let newRecipe;
        do {
            newRecipe = recipes[Math.floor(Math.random() * recipes.length)];
        } while (newRecipe === recipe);
        recipe = newRecipe;
        ingredients = recipe.ingredients;
    }

    function navigateToList() {
        dispatch("navigate");
    }
</script>

<section>
    <h1>Coffee Recipes</h1>
    <h2>{recipe.name}</h2>
    <h3>Ingredients</h3>
    <ul>
        {#each ingredients as ingredient}
            <li>{ingredient}</li>
        {/each}
    </ul>
    <h3>Instructions</h3>
    <pre>{recipe.instructions}</pre>
    <button type="button" class="btn btn-primary" on:click={randomRecipe}
        >Random a new one!</button
    >
    <button type="button" class="btn btn-info" on:click={navigateToList}>
        Get me a list
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
