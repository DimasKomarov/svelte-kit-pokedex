<!-- Скрипт, который выводит в консоль фразу Hello world -->
<script>
    // Импортируем наших покемонов из pokestore
    // и выводим их в консоль при помощи значка реактивности $
    import {pokemon} from "../stores/pokestore"
    console.log($pokemon)
</script>

<!-- Тег свелт для отображения названия в шапке страницы -->
<svelte:head>
    <title>Svelte Kit Pokedex</title>
</svelte:head>

<!-- Заголовок -->
<h1 class ="text-4xl text-center my-8 uppercase">Svelte Kit Pokedex</h1>

<!-- Обработка возможной ошибки, когда вместо pokemon будет pokeman  -->
{#each $pokemon as pokeman}
<p>{pokeman.name}</p>
{/each}

