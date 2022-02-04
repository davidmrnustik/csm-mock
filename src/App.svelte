  <script>
  import Nav from './Nav.svelte';
  import HlavniMenu from './HlavniMenu.svelte';
  import StartMenu from "./StartMenu.svelte";
  import NotFound from "./NotFound.svelte";

  const hashNames = {
    START_MENU: '#start-menu',
    HLAVNI_MENU: '#hlavni-menu'
  };

  const titles = {
    [hashNames.START_MENU]: 'Start Menu',
    [hashNames.HLAVNI_MENU]: 'Hlavní Menu'
  };

  const hashMap = {
    [hashNames.START_MENU]: StartMenu,
    [hashNames.HLAVNI_MENU]: HlavniMenu
  };

  let page = location.hash || hashNames.START_MENU;

  let component = hashMap[location.hash] || StartMenu;

  function hashChange() {
    component = hashMap[location.hash] || NotFound;
    page = location.hash;
  }
</script>

<svelte:window on:hashchange={hashChange} />

<Nav {titles} bind:page/>
<svelte:component this={component}/>
