<script>
    /** @type {string[][]} */
    export let item_list;
</script>

<table>
    <thead>
        <tr>
            <th colspan="2">물품 칸</th>
        </tr>
    </thead>
    <tbody>
        {#each item_list as items}
            <tr>
                {#each items as item}
                    <td>
                        <textarea type="text" maxlength="75" bind:value="{item}"></textarea>
                    </td>
                {/each}
            </tr>
        {/each}
    </tbody>
</table>

<style>
    tr {
        border-bottom: 3px solid black;
    }

    th {
        font-weight: 400;
        font-size: 30px;
    }

    th,
    td {
        text-align: center;
    }

    td,
    textarea {
        width: 450px;
        height: 80px;
    }

    td:not(:last-child) {
        border-right: 3px solid black;
    }

    textarea {
        padding: 5px;
        border: none;
        outline: none;
        resize: none;
        overflow: hidden;
        font: inherit;
        font-size: 20px !important;
    }
</style>
