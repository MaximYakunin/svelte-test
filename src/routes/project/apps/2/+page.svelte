<h1>Учет расходов</h1>
<p>Название расхода:</p>
<div class="input">
    <input type="text" bind:value={newName}>
</div>
<p>Сумма:</p>
<div class="input">
    <input type="text" bind:value={newAmount}>
    <button class="button" on:click={addExpense}>Отправить</button>
</div>
<table>
<thead>
        <tr>
            <th>Названия расходов</th>
            <th>Суммы</th>
            <th>Действие</th>
        </tr>
</thead>
<tbody>
        {#each expenses as expense, i}
    <tr>
        <td><div>{expense.name}</div></td>
        <td><div>{expense.amount}</div></td>
        <td><button on:click={() => deleteExpense(i)}>Удалить</button></td>
    </tr>
        {/each}
</tbody>
</table>
<script>
let expenses = [];
let newName = '';
let newAmount = '';
function addExpense() {
    if (newName !== '' && newAmount !== '') {
        expenses = [
             ...expenses,
            {
                name: newName,
                amount: newAmount,
            },
        ];
        newName = '', newAmount = '';
    }
}
function deleteExpense(index) {
    expenses.splice(index, 1);
    expenses = expenses;
}

</script>
<style>
input[type='text'] {
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-right: 10px;
    width: 200px;
}
table {
    margin-top: 20px;
    border-collapse: collapse;
    width: 100%;
}
th,
td {
    border: 1px solid #ccc;
    padding: 8px;
    text-align: left;
}
th {
background-color: #eee;
}
button {
    padding: 5px 10px;
    background-color: #4caf50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
h1 {
        font-size: 24px;
        margin-bottom: 20px;
}   
</style>
