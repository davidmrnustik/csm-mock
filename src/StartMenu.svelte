<script>
  const url = '/assets/startMenu';
</script>

<div id="page">
  <img src="{url}/logo_csm2022_start.png" class="logo_csm" alt="" >
  <img src="{url}/bg.jpg" alt="" >
  <div class="button button_nahrat" style="--url: {`url(${url}/but_nahrat.png)`}"></div>
  <div class="button button_nova_hra" style="--url: {`url(${url}/but_nova_hra.png)`}"></div>
  <div class="button button_scenare" style="--url: {`url(${url}/but_scenare.png)`}"></div>
  <div class="button button_o_csm" style="--url: {`url(${url}/but_o_csm.png)`}"></div>
  <div class="button button_ukoncit" style="--url: {`url(${url}/but_ukoncit.png)`}"></div>
  <img src="{url}/logo_twitter.png" class="logo" alt="" >
  <img src="{url}/logo_youtube.png" class="logo logo_youtube" alt="" >
  <img src="{url}/logo_facebook.png" class="logo logo_facebook" alt="" >
  <img src="{url}/logo_discord.png" class="logo logo_discord" alt="" >
</div>

<style>
  #page {
    width: 1280px;
    height: 720px;
    position: relative;
  }
  .logo_csm {
    position: absolute;
    left: 99px;
    top: 99px;
  }
  .button {
    position: absolute;
    width: 219px;
    height: 190px;
    background: none;
  }
  .button:hover {
    cursor: pointer;
    background-image: var(--url);
  }
  .button_nahrat {
    left: 524px;
    top: 323px;
  }
  .button_nahrat:hover {
    left: 524px;
    top: 323px;
  }
  .button_nova_hra {
    left: 695px;
    top: 224px;
  }
  .button_scenare {
    left: 865px;
    top: 323px;
  }
  .button_o_csm {
    left: 695px;
    top: 423px;
  }
  .button_ukoncit {
    left: 1036px;
    top: 25px;
  }
  .logo {
    position: absolute;
    left: 1095px;
    top: 666px;
    width: 34px;
    height: 34px;
    cursor: pointer;
  }
  .logo_youtube {
    left: 1139px;
  }
  .logo_facebook {
    left: 1182px;
  }
  .logo_discord {
    left: 1226px;
  }
</style>