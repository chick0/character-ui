<script>
    /** @type {import("src/stat").Ability[]} */
    export let ability_list;

    /** @type {import("src/stat").Stat} */
    export let armor;

    /** @type {import("src/stat").Stat} */
    export let hp;
</script>

<table>
    <thead>
        <tr>
            <th>방어도</th>
            <th>능력치</th>
            <th>보너스</th>
        </tr>
    </thead>
    <tbody>
        {#each ability_list as ability}
            <tr>
                <td>{ability.stat}</td>
                <td title="{ability.stat} + {ability.bonus} = {ability.stat + ability.bonus}">{ability.name}</td>
                <td>{ability.bonus}</td>
            </tr>
        {/each}
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th>방어도</th>
            <th></th>
            <th>보너스</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>{armor.stat}</td>
            <td>장갑</td>
            <td>{armor.bonus}</td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th>최대치</th>
            <th></th>
            <th>현재</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>{hp.stat}</td>
            <td>HP</td>
            <td>{hp.bonus}</td>
        </tr>
    </tbody>
</table>

<style>
    th,
    td {
        text-align: center;
        width: 100px;
    }

    th {
        font-weight: 400;
        font-size: 18px;
    }

    td {
        padding: 5px;
        padding-top: 15px;
        padding-bottom: 15px;
    }

    tr > td:nth-child(2) {
        font-weight: bold;
        font-size: 25px;
    }

    table {
        border-bottom: 3px solid black;
    }
</style>
