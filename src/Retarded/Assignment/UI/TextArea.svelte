<script>
  export let userInput;
  export let id;
  export let type;
</script>

<div class="form-control">
  <label for={id}>{id}</label>
  {#if type == "textarea"}
    <textarea {id} rows="3" value={userInput} on:input />
  {:else}
    <input type="text" {id} value={userInput} on:input />
  {/if}
</div>

<style>
  label {
    text-transform: capitalize;
  }
  .form-control {
    display: flex;
    flex-direction: column;
    width: 50%;
  }
  input,textarea{
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.26);
  }
</style>
