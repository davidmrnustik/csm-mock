<script>
 export let titles;
 export let page;
</script>

<nav>
  {#each Object.keys(titles) as key, index}
    <a href={`index.html${key}`} class:selected={page === key} on:click={() => page = key}>{titles[key]}</a>
  {/each}
</nav>

<style>
  nav a {
    cursor: pointer;
    display: inline-block;
    text-decoration: underline;
    padding: 20px;
  }
  nav {
    background-color: #fff;
  }
  .selected {
    background-color: #1a5781;
    text-decoration: none;
    color: #fff;
  }
</style>