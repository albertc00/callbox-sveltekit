<script>
  let initialRender = true;
  let loaded = false;

  function handleLoad({ target }) {
    initialRender = false;
    loaded = true;
  }
  function handleError({ target }) {
    initialRender = false;
    loaded = false;
  }
</script>

{#if initialRender || loaded}
  <slot onLoad={handleLoad} onError={handleError} />
{:else}
  <p>Error</p>
{/if}
