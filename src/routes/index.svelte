<!-- Скрипт, который выводит в консоль фразу Hello world -->
<script>
    // Импортируем наших покемонов из pokestore
    // и выводим их в консоль при помощи значка реактивности $
    import {pokemon} from "../pokestore"
    import PokemanCard from "../components/pokemanCard.svelte";

    // Поиск покемонов, запрос и нужный нам покемон
    let searchTerm = "";
    let filteredPokemon = [];

    $: {
        console.log(searchTerm);
        if (searchTerm) {
            filteredPokemon = $pokemon.filter(pokeman => pokeman.name.toLowerCase().includes(searchTerm.toLowerCase()));
        }else {
            filteredPokemon = [...$pokemon]
        }
    }
</script>

<!-- Тег свелт для отображения названия в шапке страницы -->
<svelte:head>
    <title>Svelte Kit Pokedex</title>
</svelte:head>

<!-- Заголовок -->
<h1 class ="text-4xl text-center my-8 uppercase">Svelte Kit Pokedex</h1>

<!-- Поиск покемонов (текстовое поле) -->
<input class="w-full rounded-md text-lg p-4 border-2 border-gray-200" 
type="text" bind:value={searchTerm} placeholder="Search Pokemon">

<!-- Обработка списка покемонов  -->
<div class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
    {#each filteredPokemon as pokeman}
    <PokemanCard pokeman={pokeman} />
    {/each}

</div>

