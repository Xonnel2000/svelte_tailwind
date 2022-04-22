<script context="module">
  export async function load({ fetch }) {
    const res = await fetch("https://jsonplaceholder.typicode.com/posts");
    const users = await res.json();

    if (res.ok) {
      return {
        props: {
          users,
        },
      };
    }

    return {
      status: res.status,
      error: new Error("Could not fetch the guides"),
    };
  }
</script>

<script>
  export let users;
</script>

<div class="users">
  <h2 class="text-3xl font-bold ">Get Api and load</h2>
  <ul>
    {#each users as guide}
      <li>
        <a href="/">{guide.title}</a>
      </li>
    {/each}
  </ul>
</div>

<style>
  .users {
    margin-top: 20px;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  a {
    display: inline-block;
    margin-top: 10px;
    padding: 10px;
    border: 1px dotted rgba(255, 255, 255, 0.2);
  }
</style>
