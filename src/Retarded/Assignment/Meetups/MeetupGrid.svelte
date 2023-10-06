<script>
  import MeetupItem from "./MeetupItem.svelte";
  export let meetups;
</script>

<div>
  {#each meetups as meetup}
    <MeetupItem
      imageUrl={meetup.imageUrl}
      title={meetup.title}
      subTitle={meetup.subtitle}
      description={meetup.description}
      address={meetup.address}
      email={meetup.email}
    />
  {/each}
</div>

<style>
    div{
        display: grid;
        gap: 1rem;
        grid-template-columns: 1fr 1fr;
    }
</style>