<script>
  import { list } from "./itemList";
  import Item from "./Item.svelte";
</script>

<style>
  table {
    table-layout: fixed;
    border-collapse: collapse;
    border: 3px solid purple;
    text-align: center;
  }

  th {
    min-width: 100px;
    width: 100px;
  }

  tr {
    border: 1px solid #eee;
    height: 50px;
  }

  :global(td) {
    width: 100px;
  }
</style>

<h1>Module</h1>

<table>
  <thead>
    <tr>
      <th>Module</th>
      <th>Product</th>
      <th>Amount</th>
      <th>Price per 1 product</th>
      <th>Revenue x Ammount</th>
      <th>Flea Fee</th>
      <th>Profit/Loss</th>
      <th>Crafting Needs</th>
      <th>Amount</th>
      <th>Price</th>
      <th>Crafting Needs</th>
      <th>Amount</th>
      <th>Price</th>
      <th>Crafting Needs</th>
      <th>Amount</th>
      <th>Price</th>
      <th>Total Crafting</th>
    </tr>

  </thead>
  <tbody>
    {#each list as module}
      <tr>
        <td>{module.name}</td>
      </tr>

      {#each module.crafts as item}
        <tr>
          <Item crafts={item} />
        </tr>
      {/each}
    {/each}
  </tbody>
</table>
