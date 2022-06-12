<script>
  import { fly } from "svelte/transition";

  let visible = false;
  export const show = () => {
    visible = true;
  };
  export const hide = () => {
    visible = false;
  };
</script>

{#if visible}
<main transition:fly="{{ y: 10, duration: 300 }}">
<div class="container">
  <h3>Menu</h3>
  <ul>
  <li>Dificuldade
  <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="48" d="M112 184l144 144 144-144"/></svg>
  </li>
  </ul>
</div>
</main>
{/if}
<style>
  main {
    width: 100%;
    left: 0px;
    position: fixed;
    bottom: 0px;
    height: max-content;
    background-color: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px;
    z-index: var(--z-modal);
  }
  main .container {
    padding: 10px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    width: 100%;
    max-width: 500px;
    height: 200px;
    background-color: hsl(var(--primary));
    border-radius: var(--rounded-1);
  }
  main .container h3 {
    font-size: var(--display-3);
  }
  main .container ul {
    padding: 5px 0px 5px 0px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }
  main .container ul li {
    width: 100%;
    height: 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: hsl(var(--secondary));
    border-radius: var(--rounded-1);
    --rp-color: var(--rp-primary);
    --rp-transition: var(--rp-time);
    padding: 10px;
    position: relative;
    overflow: hidden;
    cursor: pointer;
  }
</style>