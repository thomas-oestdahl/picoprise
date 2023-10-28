<script>
  // Define an array with unique items, of orders with ID, customer full name, address, order date and sauna volume
  const orders = [
    {
      id: 1,
      name: "John Smith",
      address: "123 Main St, Anytown USA",
      date: "2023-10-01",
      volume: 4,
    },
    {
      id: 2,
      name: "Jane Doe",
      address: "456 Elm St, Anytown USA",
      date: "2023-10-02",
      volume: 2,
    },
    {
      id: 3,
      name: "Bob Johnson",
      address: "789 Oak St, Anytown USA",
      date: "2023-10-03",
      volume: 3,
    },
    {
      id: 4,
      name: "Alice Williams",
      address: "321 Pine St, Anytown USA",
      date: "2023-10-04",
      volume: 1,
    },
    {
      id: 5,
      name: "Charlie Brown",
      address: "654 Maple St, Anytown USA",
      date: "2023-10-05",
      volume: 5,
    },
  ];
</script>

<section>
  <h1 class="text-3xl font-serif font-bold text-secondary pb-5">Dashboard</h1>
  <h2 class="text-xl font-serif font-bold pb-2">Active</h2>
  <table class="table w-full table-auto">
    <thead>
      <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Address</th>
        <th>Date</th>
        <th>Volume</th>
        <th>Status</th>
      </tr>
    </thead>
    <tbody>
      {#each orders as order}
        <tr>
          <td>{order.id}</td>
          <td>{order.name}</td>
          <td>{order.address}</td>
          <td>{order.date}</td>
          <td>{order.volume} m<sup>3</sup></td>
          <td>
            <span class="badge badge-success">Active</span>
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</section>
