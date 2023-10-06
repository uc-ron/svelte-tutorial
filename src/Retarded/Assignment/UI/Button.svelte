<script>
  export let name;
  export let type;
  export let href;
  export let mode;
</script>

{#if href}
  <a {href}>{name}</a>
{:else}
  <button class={mode} {type}>{name}</button>
{/if}

<style>
  button,
  a {
    padding: 0.5rem 1rem;
    background: rgb(255, 3, 102);
    color: white;
    font-size: 1rem;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none;
  }
  button:disabled {
    color: #999;
  }

  button:not(:disabled):active {
    background-color: #ddd;
  }
  button:focus {
    border-color: #666;
  }
  button:hover,
  a:hover,
  button:focus,
  a:active {
    color: #000;
  }
  .outline {
    background: transparent;
    color: rgb(255, 3, 102);
    border: 1px solid rgb(255, 3, 102);
  }
  .outline:hover,.outline:active,.outline:focus {
    background: rgb(255, 3, 102);
    color: #fff;
  }
</style>
