<script>
  let titles = ["id", "name", "username", "email"];
  let users = [];
  let filteredUsers = [];

  const loadUsers = async () => {
    const res = await fetch("https://jsonplaceholder.typicode.com/users");
    const data = await res.json();
    users = data;
    filteredUsers = data;
  };

  loadUsers();

  const searchUser = (value) => {
    filteredUsers = users.filter(
      (user) =>
        user.name.toLowerCase().includes(value.toLowerCase()) ||
        user.username.toLowerCase().includes(value.toLowerCase()) ||
        user.email.toLowerCase().includes(value.toLowerCase())
    );
  };
</script>

<main>
  <div class="container">
    <div class="row">
      <h1>Hello world</h1>

      <input
        type="text"
        class="form-control bg-dark text-white rounded-0 border-0 my-4"
        placeholder="Search users..."
        on:keyup={({ target }) => searchUser(target.value)}
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
          {#each filteredUsers as user}
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
