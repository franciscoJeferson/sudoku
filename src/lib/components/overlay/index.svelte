<script>
  import { fade } from "svelte/transition";
  let visible = false;
  export const show = () => {
    visible = true;
    document.querySelectorAll(".ripple").forEach(item => item.remove());
  };
  export const hide = () => {
    visible = false;
  };
</script>
{#if visible}
	<main transition:fade="{{ duration: 300 }}" on:click="{() => window.history.back()}">
	</main>
{/if}
<style>
  main {
    max-width: 800px;
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0px;
    z-index: var(--z-overlay);
    background-color: hsla(0, 0%, 0%, 0.1);
  }
</style>