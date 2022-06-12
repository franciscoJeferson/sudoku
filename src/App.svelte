<script>
  import Menu from "./lib/components/menu/index.svelte";
  import Overlay from "./lib/components/overlay/index.svelte";
  import { createEventDispatcher } from "svelte";

  window.location.hash = "#";
  let overlay;
  let menu;
  const dispatch = createEventDispatcher();
  const root = document.documentElement;
  root.style.setProperty("--height-body", `${window.innerHeight}px`);

  document.body.onhashchange = () => {
    const hash = window.location.hash;
    if (hash === "#menu") {
      overlay.show();
      menu.show();
    } else {
      overlay.hide();
      menu.hide();
    }
  };
</script>

<main>
  <header class="header">
    <div class="header__container"></div>
    <div class="header__container">
      <h2 class="header__title">SUDOKU</h2>
    </div>
    <div class="header__container">
      <button 
        class="header__button-menu"
        on:click="{() => window.location.hash = '#menu'}">
        <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-miterlimit="10" stroke-width="32" d="M80 160h352M80 256h352M80 352h352"/></svg>
      </button>
    </div>
  </header>
  <div class="game-area">
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
      <div class="square">
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
        <div class="number"></div>
      </div>
  </div>
  <Menu bind:this={menu}/>
  <Overlay bind:this={overlay}/>
</main>

<style>
  main {
    align-items: flex-start;
    display: flex;
    height: var(--height-body);
    flex-direction: column;
    align-items: center;
    row-gap: 50px;
    justify-content: center;
    padding: 10px;
    width: 100%;
    background-color: hsl(var(--primary));
  }

  .header {
    align-items: center;
    background-color: hsl(var(--secondary));
    border-radius: var(--rounded-1);
    display: flex;
    height: 70px;
    justify-content: center;
    max-width: 500px;
    padding: 10px;
    width: 100%;
  }
  .header__container {
    align-items: center;
    display: flex;
    height: 100%;
    justify-content: center;
    width: 80%;
  }
  .header__container:nth-child(1),
  .header__container:nth-child(3) {
    justify-content: flex-end;
    width: 20%;
  }
  .header__container:nth-child(1) {
    justify-content: flex-start;
  }
  .header__title {
    font-size: var(--display-2);
    font-weight: normal;
    text-align: center;
    width: calc(100% - 60px);
  }
  .header__button-menu {
    align-items: center;
    background-color: transparent;
    border: none;
    border-radius: var(--rounded-1);
    cursor: pointer;
    display: flex;
    height: 60px;
    justify-content: center;
    outline: none;
    overflow: hidden;
    position: relative;
    width: 60px;
    --rp-transition: var(--rp-time);
    --rp-color: var(--rp-primary);
  }

  .game-area {
    width: 100%;
    max-width: 500px;
    max-height: 500px;
    height: 100vw;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
  }
  .game-area .square {
    width: 33%;
    height: 33%;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
  }
  .game-area .square .number {
    width: 32%;
    height: 32%;
    margin: 0.5%;
    background-color: hsl(var(--secondary));
    border-radius: var(--rounded-1);
  }
</style>
