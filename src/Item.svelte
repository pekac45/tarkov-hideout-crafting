<script>
  import { list } from "./itemList";

  const sumArr = arr => arr.reduce((a, b) => a + b, 0);

  function calculateExpense(arr) {
    let needSum = [];

    arr.forEach(need => {
      needSum.push(need.item[0].price * need.amount);
    });

    return sumArr(needSum);
  }

  export let crafts;

  const craftsName = crafts.creates[0].item[0].name;
  const craftsPrice = crafts.creates[0].item[0].price;
  const craftsAmount = crafts.creates[0].amount;
  const craftRevenue = craftsPrice * craftsAmount;

  const craftNeedsArr = crafts.needs;
  const craftNeedsPriceTotalArr = [];
  const totalNeedsExpenses = calculateExpense(craftNeedsArr);
  const profit = craftRevenue - totalNeedsExpenses;
</script>

<style>
  td {
    min-width: 100px;
    text-align: center;
  }

  /* .data {
    min-width: 100px;
  } */
</style>

<td />
<th class="data">{craftsName}</th>
<td class="data">{craftsAmount}</td>
<td class="data">{craftsPrice}</td>
<td class="data">{craftRevenue}</td>
<td class="data">n/a</td>
<td class="data">{profit > 0 ? 'Profit' : 'Loss'}: {profit}</td>
<td class="data">{craftNeedsArr[0].item[0].name}</td>
<td class="data">{craftNeedsArr[0].amount}</td>
<td class="data">{craftNeedsArr[0].item[0].price}</td>
<td class="data">
  {#if craftNeedsArr[1]}{craftNeedsArr[1].item[0].name}{:else}-{/if}
</td>
<td class="data">
  {#if craftNeedsArr[1]}{craftNeedsArr[1].amount}{:else}-{/if}
</td>
<td class="data">
  {#if craftNeedsArr[1]}{craftNeedsArr[2].item[0].price}{:else}-{/if}
</td>
<td class="data">
  {#if craftNeedsArr[2]}{craftNeedsArr[2].item[0].name}{:else}-{/if}
</td>
<td class="data">
  {#if craftNeedsArr[2]}{craftNeedsArr[1].amount}{:else}-{/if}
</td>
<td class="data">
  {#if craftNeedsArr[2]}{craftNeedsArr[2].item[0].price}{:else}-{/if}
</td>

<td class="data">{totalNeedsExpenses}</td>
<!-- {#each craftNeedsArr as need}
  {need.item[0].name} {need.amount}x RUB {need.item[0].price}, total: {need.amount * need.item[0].price}
  <br />
{/each} -->
