<!-- Берем id покемона и возвращаем его страницу -->
<script context="module">
    import { getPokemonById } from "../../pokestore";
    export async function load({params}) {
        const id = params.id;
        const pokeman = await getPokemonById(id);
        return { props: { pokeman }}
    }
</script>

<!-- Возвращается тип покемона -->
<script>
    export let pokeman;
    const type = pokeman.types[0].type.name;
</script>

<!-- Заголовок - имя покемона -->
<svelte:head>
	<title>Pokedex - {pokeman.name}</title>
</svelte:head>

<!-- Контейнер, где находится заголовок, изображение и характристики покемона -->
<div class="flex flex-col items-center">

    <h1 class="text-4xl text-center my-8 uppercase">{pokeman.name}</h1>
    <p>Type: <strong>{type}</strong> | Height: <strong>{pokeman.height}</strong>
        | Weight: <strong>{pokeman.weight}</strong>
    </p>
    <img class="card-image" src={pokeman.sprites['front_default']} 
    alt={pokeman.name}
    />
</div>