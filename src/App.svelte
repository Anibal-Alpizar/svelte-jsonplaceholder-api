<script>
  const loadUsers = async () => {
    const res = await fetch("https://jsonplaceholder.typicode.com/users");
    const data = await res.json();
    console.log(data);
  };

  loadUsers();
</script>

<main>
  <h1>Hello world</h1>
</main>

<style>
</style>
