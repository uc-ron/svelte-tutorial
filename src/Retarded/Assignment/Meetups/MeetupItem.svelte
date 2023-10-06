<script>
  import Button from "../UI/Button.svelte";

  export let title;
  export let subTitle;
  export let imageUrl;
  export let description;
  export let email;
  export let address;
</script>

<article>
  <header>
    <h1>{title}</h1>
    <h2>{subTitle}</h2>
    <p>{address}</p>
  </header>
  <div class="img">
    <img src={imageUrl} alt={title} />
  </div>
  <div class="content">
    <p>{description}</p>
  </div>
  <footer>
    <Button href="mailto:{email}" name="Contact" />
    <Button type="button" name="Favorite" mode="outline" />
    <Button type="button" name="Show Details" />
  </footer>
</article>

<style>
  article {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    font-family: Georgia, "Times New Roman", Times, serif;
    padding: 1rem;
    margin-bottom: 10px;
    border-radius: 10px;
  }
  h1 {
    font-weight: 600;
  }
  h2 {
    font-weight: normal;
    color: #7d7d7d;
  }
  .content {
    text-align: right;
    height: 4rem;
    padding: 0.5rem;
  }

  .img {
    width: 100%;
    height: 20rem;
    background: linear-gradient(to right, #ff0366, yellow);
  }
  img {
    width: 100%;
    height: 20rem;
    object-fit: cover;
  }
</style>
