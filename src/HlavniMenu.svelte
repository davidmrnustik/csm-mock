  <script>
  let version = "v1";
  const url = '/assets/hlavniMenu';

  const defaultButtons = {
    continue: {
      default: 'but_continue.gif',
      mouseover: 'but_continue_over.gif',
    },
    fastForward: {
      default: 'but_fast_forward.gif',
      mouseover: 'but_fast_forward_over.gif',
    }
  };

  const buttons = {
    v1: { ...defaultButtons },
    v2: { ...defaultButtons },
    v3: { ...defaultButtons },
    v4: {
      ...defaultButtons,
      fastForward: {
        default: 'but_fast_forward.png',
        mouseover: 'but_fast_forward.png',
      }
    }
  };

  const logaKonfederace = {
    esu: {
      default: 'ico_esu.png',
      mouseover: 'ico_esu_over.png',
    },
    chl: {
      default: 'ico_chl.png',
      mouseover: 'ico_chl_over.png',
    },
    eul: {
      default: 'ico_eul.png',
      mouseover: 'ico_eul_over.png',
    },
    ecl: {
      default: 'ico_ecl.png',
      mouseover: 'ico_ecl_over.png',
    },
    cli: {
      default: 'ico_cli.png',
      mouseover: 'ico_cli_over.png',
    },
    csa: {
      default: 'ico_csa.png',
      mouseover: 'ico_csa_over.png'
    }
  };

	const onClick = event => {
    const { dataset } = event.target;
    ({ version } = dataset);
  }

  const getImageSrc = (ver, but) => {
	  const imgSrc = buttons[ver][but].default;
	  return `${url}/${ver}/${imgSrc}`;
  }

  const getImageLogoSrc = (key) => {
    const imgSrc = logaKonfederace[key].default;
    return `${url}/ico_konfederace/${imgSrc}`;
  }

  const onMouseAction = (event, eventType, ver) => {
	  const { target } = event;
	  const { button } = target.dataset;

    const arr = target.src.split('/');
    arr.pop();
    const imgUrl = `${url}/${version}/${buttons[ver][button][eventType]}`;
    target.src = imgUrl;
  }

  const onMouseActionOnLogo = (event, eventType) => {
    const { target } = event;
    const { logo } = target.dataset;

    const imgUrl = `${url}/ico_konfederace/${logaKonfederace[logo][eventType]}`;
    target.src = imgUrl;
  }
</script>

<nav>
  {#each Object.keys(buttons) as key, index}
    <span class:selected={version === key} data-version={key} on:click={onClick}>Verze {index + 1}</span>
  {/each}
</nav>
<div id="page">
  {#each Object.keys(buttons[version]) as key}
    <img id={key} data-button={key} src={getImageSrc(version, key)} on:mouseover={(e) => onMouseAction(e, 'mouseover', version)} on:mouseleave={(e) => onMouseAction(e, 'default', version)} alt={key} />
  {/each}
  <section id="loga-konfederace">
  {#each Object.keys(logaKonfederace) as key}
    <div class="logo"><img data-logo={key} src={getImageLogoSrc(key)} on:mouseover={(e) => onMouseActionOnLogo(e, 'mouseover')} on:mouseout={(e) => onMouseActionOnLogo(e, 'default')} on:click={(e) => onMouseActionOnLogo(e, 'mouseover')} alt={key}></div>
  {/each}
  </section>
  <img src="{url}/bg.jpg" alt="" >
</div>

<style>
  #loga-konfederace {
    position: absolute;
    bottom: 20px;
    left: 20px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    width: 280px;
    height: 163px;
    padding: 20px;
    box-sizing: border-box;
    grid-gap: 20px;
    padding: 20px;
    background-color: rgba(0, 78, 155, .6);
  }
  #loga-konfederace div {
    display: flex;
    justify-content: center;
    align-content: center;
    width: 100%;
    height: 100%;
    cursor: pointer;
  }
  nav span {
    cursor: pointer;
    display: inline-block;
    margin: 5px 0;
    padding: 5px 8px;
    color: #e7e7e7;
    text-decoration: underline;
  }
  #page {
    width: 1280px;
    height: 720px;
    position: relative;
  }
  nav {
    margin: 0 5px;
  }
  #continue, #fastForward {
    position: absolute;
    top: 647px;
  }
  #fastForward {
    right: 37px;
  }
  #continue {
    right: 103px;
  }
  .selected {
    background-color: #fff;
    text-decoration: none;
    color: #004A97;
  }
</style>