<!-- Специальный скрипт для того, чтобы наше меню показывалось
сразу на нескольких страницах без подгрузки -->
<script>
    import Nav from "../components/nav.svelte";
</script>

<div class="p-8 max-w-6xl mx-auto">
    <!-- Вызов меню навигации -->
    <Nav/>
    <!-- Тег slot для создания навигации по всем страницам -->
    <slot></slot>
</div>

<!-- Стили библиотеки tailwind -->
<style>
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>