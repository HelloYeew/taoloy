<script>
    // make a list of coffee recipes
    let recipes = [
        {
            name: 'Cappuccino',
            ingredients: ['Espresso', 'Steamed Milk', 'Whipped Cream'],
            instructions: 'Combine Espresso, Steamed Milk and Whipped Cream in a pot'
        },
        {
            name: 'Latte',
            ingredients: ['Espresso', 'Steamed Milk'],
            instructions: 'Combine Espresso and Steamed Milk in a pot'
        },
        {
            name: 'Mocha',
            ingredients: ['Espresso', 'Steamed Milk', 'Whipped Cream', 'Chocolate Syrup'],
            instructions: 'Combine Espresso, Steamed Milk, Whipped Cream and Chocolate Syrup in a pot'
        }
    ];
    // random coffee recipe
    let recipe = recipes[Math.floor(Math.random() * recipes.length)];
    let ingredients = recipe.ingredients;

    function randomRecipe() {
        recipe = recipes[Math.floor(Math.random() * recipes.length)];
        ingredients = recipe.ingredients;
    }
</script>

<h1>Coffee Recipes</h1>
<h2>{recipe.name}</h2>
<h3>Ingredients</h3>
<ul>
    {#each ingredients as ingredient}
        <li>{ingredient}</li>
    {/each}
</ul>
<h3>Instructions</h3>
<p>{recipe.instructions}</p>
