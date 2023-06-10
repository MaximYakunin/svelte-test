<svelte:head>
    <title>Портфолио</title>
</svelte:head>
<div class="container">
    <h1>Мои проекты</h1>
    <div class="apps">
        {#each routes as page} 
        <div class="app"> 
        <h2>{page.title}</h2>
        <p>{page.body}</p>
        </div> 
        {/each}
    </div>
</div>   

<h1>Портфолио</h1>
todo..
<script>
    import { routes } from './routes.js';
</script>
<style>
    .container{
        margin: 50px auto;
        max-width: 800px;
        padding: 0 20px;
        }
</style>