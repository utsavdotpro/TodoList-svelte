<script>
  export let photoURL;
  export let uid;

  export let login;
  export let logout;
</script>

<nav>
  <img src="/favicon.png" alt="logo" />
  <h2>Todo List</h2>

  <div class="flex-1" />

  {#if !uid}
    <button on:click={login}
      ><img src="/google.png" alt="google" /> Login</button
    >
  {:else}
    <img class="img-user" src={photoURL} alt="user" />

    <button on:click={logout}>Logout</button>
  {/if}
</nav>

<style>
  nav {
    padding: 1em;
    margin: 0;
    margin-bottom: 2em;
    border-radius: 0.5em;
    display: flex;
    align-items: center;

    background: #8a2387;
    background: -webkit-linear-gradient(to right, #f27121, #e94057, #8a2387);
    background: linear-gradient(to right, #f27121, #e94057, #8a2387);

    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  }

  img {
    width: 2em;
    height: 2em;
  }

  h2 {
    margin: 0;
    margin-left: 0.5em;
  }

  button {
    border: none;
    padding: 0.8em 1.5em;
    border-radius: 0.5em;
    text-transform: uppercase;
    cursor: pointer;
    font-weight: bold;
    transition: all 0.3s;
    display: flex;
    align-items: center;
  }

  button img {
    width: 1em;
    height: 1em;
    margin-right: 0.8em;
  }

  button:hover {
    transform: scale(1.05);
  }

  .img-user {
    width: 2em;
    height: 2em;
    border-radius: 50%;
    margin-right: 1em;
  }
</style>
