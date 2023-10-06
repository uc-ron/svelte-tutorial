<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Krish";
  let title = "Developer";
  let description = "Some Content";
  let img = "https://img.freepik.com/premium-photo/image-colorful-galaxy-sky-generative-ai_791316-9864.jpg?w=2000";
  let formState = "empty";

  let createContact = [];

  function addContact() {
    if (
      name.trim().length === 0 ||
      title.trim().length === 0 ||
      img.trim().length === 0 ||
      description.trim().length === 0
    ) {
      formState = "invalid";
      return;
    }
    createContact = [
      ...createContact,
      {
        id: Math.random(),
        name,
        title,
        img,
        description,
      },
    ];
    formState = "done";
  }

  function deleteFirst() {
    createContact = createContact.slice(1);
  }

  function deleteLast() {
    createContact = createContact.slice(0, -1);
  }
</script>

<div class="container">
  <div class="form">
    <div class="form-control">
      <label for="">Name</label>
      <input type="text" bind:value={name} />
    </div>
    <div class="form-control">
      <label for="">Job Title</label>
      <input type="text" bind:value={title} />
    </div>
    <div class="form-control">
      <label for="">Image URL</label>
      <input type="text" bind:value={img} />
    </div>
    <div class="form-control">
      <label for="">Description</label>
      <textarea rows="3" bind:value={description} />
    </div>
    <button on:click={addContact}>Add Contact Card</button>
    <button on:click={deleteFirst}>Delete First</button>
    <button on:click={deleteLast}>Delete Last</button>
    {#if formState === "invalid"}
      <p class="invalid">Invalid input!</p>
    {:else if formState === "empty"}
      <p>Please enter details and hit Add Contact Card.</p>
    {/if}
  </div>

  {#each createContact as contact, index (contact.id)}
    <h2 class="center"># {index}</h2>
    <ContactCard
      userName={contact.name}
      jobTitle={contact.title}
      description={contact.description}
      userImage={contact.img}
    />
  {:else}
    <h3 class="center">No Contact Found! Please Add Contact...</h3>
  {/each}
</div>

<style>
  label {
    color: purple;
    font-weight: 600;
  }
  .invalid {
    color: red;
    font-weight: bold;
  }
  .form,
  input,
  textarea {
    width: 30rem;
    margin: auto;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    border-radius: 5px;
  }
  .form {
    padding: 1rem;
  }
  .form-control {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
    padding-bottom: 1rem;
  }
  .center {
    text-align: center;
  }
</style>
