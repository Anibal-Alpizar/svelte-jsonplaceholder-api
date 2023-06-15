<script>
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
      <table class="table table-dark">
        <thead>
          <tr>
            <th />
          </tr>
        </thead>
        <tbody>
          {#each users as user}
            <tr>
              <td>{user.name}</td>
            </tr>
          {/each}
        </tbody>
      </table>
    </div>
  </div>
</main>

<style>
</style>
