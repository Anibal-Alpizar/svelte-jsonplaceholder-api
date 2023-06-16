<script>
  let titles = ["id", "name", "username", "email"];

  let users = [];

  const loadUsers = async () => {
    const res = await fetch("https://jsonplaceholder.typicode.com/users");
    const data = await res.json();
    console.log(data);
    users = data;
  };

  loadUsers();
</script>

<main>
  <div class="container">
    <div class="row">
      <h1>Hello world</h1>

      <input
        type="text"
        class="form-control bg-dark text-white rounded-0 border-0 my-4"
        placeholder="Search users..."
      />

      <table class="table table-dark">
        <thead>
          <tr>
            {#each titles as title}
              <th>{title}</th>
            {/each}
          </tr>
        </thead>
        <tbody>
          {#each users as user}
            <tr>
              <td>{user.id}</td>
              <td>{user.name}</td>
              <td>{user.username}</td>
              <td>{user.email}</td>
            </tr>
          {/each}
        </tbody>
      </table>
    </div>
  </div>
</main>

<style>
  :global(body) {
    background: #141414;
    color: #fff;
  }
</style>
