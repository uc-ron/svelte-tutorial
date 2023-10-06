<script>
  import App from "./Part1.svelte";

  let input = "";
  let feedback;
  let password;
  let passwords = [];
  function handleInput(e) {
    input = e.target.value;
  }
  function confirm() {
    if (input.trim().length < 5) {
      feedback = "Too short";
    } else if (input.trim().length > 10) {
      feedback = "Too long";
    } else {
      feedback = undefined;
      password = { id: Math.random(), password: input.trim() };
      passwords = [password, ...passwords];
    }
  }

  function deleteItem(e) {
    passwords = passwords.filter((p) => p.id !== e);
  }
</script>

<label for="">Password</label>
<input type="text" id="pass" on:input={handleInput} value={input} />
<button on:click={confirm}>Confirm Password</button>
<br />
{#if feedback}
  <span class="error">{feedback}</span>
{:else if password}
  <p>PASSWORD: {password.password}</p>
{/if}

{#each passwords as p, i (p.id)}
  <ul>
    <li on:click={() => deleteItem(p.id)}>{p.password}</li>
  </ul>
{/each}

<style>
  label {
    font-weight: bold;
  }
  .error {
    color: red;
    font-weight: bold;
  }
</style>
