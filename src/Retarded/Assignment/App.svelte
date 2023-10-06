<script>
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import Button from "./UI/Button.svelte";
  import Header from "./UI/Header.svelte";
  import TextArea from "./UI/TextArea.svelte";

  let title = "";
  let subtitle = "";
  let imageUrl = "";
  let email = "";
  let address = "";
  let description = "";

  let meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code in 2 hours!",
      description:
        "In this meetup, we will have some experts that teach you how to start coding as a beginner and also will tell how to become a successfull coder",
      imageUrl:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSY2SkU6yFEglZQ4bEfIgnHbpxQkCD0HT-crw&usqp=CAU",
      address: "27th Street, Holy Road, 224554 New Delhi",
      email: "code@69.com",
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Let's Swim Guys!",
      description:
        "We will simply swim some round and have a lot of fun at sunday.",
      imageUrl:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSY2SkU6yFEglZQ4bEfIgnHbpxQkCD0HT-crw&usqp=CAU",
      address: "27th Street, Holy Road, 224554 New Delhi",
      email: "swim@69.com",
    },
  ];
  function addMeetup() {
    const meetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      address: address,
      email: email,
      description: description,
      imageUrl: imageUrl,
    };

    meetups = [...meetups, meetup];
  }
</script>

<Header />
<main>
  <fieldset>
    <legend>Add Meetup</legend>
    <form on:submit|preventDefault={addMeetup}>
      <TextArea
        id="title"
        userInput={title}
        type="input"
        on:input={(e) => (title = e.target.value)}
      />
      <TextArea
        id="subtitle"
        userInput={subtitle}
        type="input"
        on:input={(e) => (subtitle = e.target.value)}
      />
      <TextArea
        id="imageUrl"
        userInput={imageUrl}
        type="input"
        on:input={(e) => (imageUrl = e.target.value)}
      />
      <TextArea
        id="address"
        userInput={address}
        type="input"
        on:input={(e) => (address = e.target.value)}
      />
      <TextArea
        id="email"
        userInput={email}
        type="input"
        on:input={(e) => (email = e.target.value)}
      />
      <TextArea
        id="description"
        userInput={description}
        type="textarea"
        on:input={(e) => (description = e.target.value)}
      />
      <Button name="Save" type="submit" mode="outline" />
    </form>
  </fieldset>
  <MeetupGrid {meetups} />
</main>

<style>
  main {
    padding-top: 4rem;
  }
  form {
    display: grid;
    justify-items: center;
  }
  legend {
    font-weight: 600;
    font-size: 1.5em;
  }
  fieldset {
    border-radius: 10px;
    margin-bottom: 1rem;
  }
</style>
