<script>
    export let userName;
    export let jobTitle;
    export let userImage;
    export let description;

    let initialName = userName;
  </script>
  
  <div class="contact-card">
    <header>
      <div class="thumb" class:thumb-placeholder={!userImage}>
        <img src={userImage} alt={userName} />
      </div>
      <div class="user-data">
        <h1>{userName} / {initialName}</h1>
        <h2>{jobTitle}</h2>
      </div>
    </header>
    <div class="description">
      <p>{@html description}</p>
    </div>
  </div>
  
  <style>
    .contact-card {
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
      max-width: 30rem;
      border-radius: 5px;
      margin: 1rem 0;
      margin: auto;
      margin-top: 2rem;
    }
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 120px;
    }
    .thumb {
      width: 33%;
      height: 100%;
    }
    .thumb-placeholder {
      background-color: #ccc;
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    .user-data {
      width: 67%;
      padding-left: 1rem;
      display: flex;
      justify-content: center;
      flex-direction: column;
    }
    .description {
      border-top: 1px solid #ccc;
      padding: 1rem;
    }
    h1 {
      font-size: 1.25rem;
    }
    h2 {
      font-weight: normal;
      font-size: 1rem;
    }
  </style>
  