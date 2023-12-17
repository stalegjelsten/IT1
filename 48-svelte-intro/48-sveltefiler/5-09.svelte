<script>
    let tall1 = (Math.random() * 10).toFixed(0);
    let tall2 = (Math.random() * 10).toFixed(0);
</script>

<table border="1">
    <tr>
        <th>Tall1</th>
        <th>Regneart</th>
        <th>Tall2</th>
        <th>=</th>
        <th>Svar</th>
    </tr>
    <tr>
        <td>{tall1}</td>
        <td>+</td>
        <td>{tall2}</td>
        <td>=</td>
        <td>{tall1 + tall2}</td>
    </tr>
    <tr>
        <td>{tall1}</td>
        <td>-</td>
        <td>{tall2}</td>
        <td>=</td>
        <td>{tall1 - tall2}</td>
    </tr>
    <tr>
        <td>{tall1}</td>
        <td>*</td>
        <td>{tall2}</td>
        <td>=</td>
        <td>{tall1 * tall2}</td>
    </tr>
    <tr>
        <td>{tall1}</td>
        <td>/</td>
        <td>{tall2}</td>
        <td>=</td>
        <td>{tall1 / tall2}</td>
    </tr>
</table>

<style>
    td {
        text-align: center;
    }
</style>
