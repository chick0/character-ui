<script>
    /** @type {string} */
    export let name;

    /** @type {number} */
    export let exp;

    /** @type {number} */
    export let lv;

    /** @type {string} */
    export let note;

    /** @type {string} */
    export let image_url;
</script>

<table>
    <thead>
        <tr>
            <th class="name">이름</th>
            <th class="exp">경험치</th>
            <th class="lv">레벨</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>{name}</td>
            <td><b>{exp}</b></td>
            <td><b>{lv}</b></td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th>초상화와 참고사항</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>{note}</td>
        </tr>
        {#if image_url.length != 0}
            <tr>
                <td>
                    <img src="{image_url}" alt="캐릭터 초상화" />
                </td>
            </tr>
        {/if}
    </tbody>
</table>

<style>
    table:not(:last-child) {
        border-bottom: 3px solid black;
    }

    th:not(:last-child),
    td:not(:last-child) {
        border-right: 3px solid black;
    }

    th {
        font-weight: 400;
        font-size: 18px;
        text-align: center;
    }

    td {
        text-align: center;
        padding-top: 15px;
        padding-bottom: 15px;
    }

    /*  */

    .name {
        width: 250px;
    }

    .exp {
        width: 120px;
    }

    .lv {
        width: 80px;
    }

    table:last-child {
        width: 450px;
    }

    img {
        max-width: 250px;
    }
</style>
