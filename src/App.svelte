<script>
    import Stat from "src/lib/stat.svelte";
    import Face from "src/lib/face.svelte";
    import Item from "src/lib/item.svelte";

    let is_loading = true;

    let ability_list = [
        {
            stat: 0,
            name: "근력",
            bonus: 0,
        },
        {
            stat: 0,
            name: "민첩",
            bonus: 0,
        },
        {
            stat: 0,
            name: "건강",
            bonus: 0,
        },
        {
            stat: 0,
            name: "지능",
            bonus: 0,
        },
        {
            stat: 0,
            name: "지혜",
            bonus: 0,
        },
        {
            stat: 0,
            name: "매력",
            bonus: 0,
        },
    ];

    let armor = {
        stat: 0,
        bonus: 0,
    };

    let hp = {
        stat: 0,
        bonus: 0,
    };

    let name = "가나다라마바사아자차카타파하";
    let exp = 0;
    let lv = 0;

    let note = "ㄴㅁㅇ";
    let image_url = "ㅗ";

    let item_list = [
        ["가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가가끝", ""],
        ["", ""],
        ["", ""],
        ["", ""],
        ["", ""],
        ["", ""],
        ["", ""],
        ["", ""],
        ["", ""],
        ["", ""],
    ];

    $: console.log(item_list);

    if (import.meta.env.DEV == true) {
        is_loading = false;
    }
</script>

<div class="container">
    {#if is_loading == true}
        <p>캐릭터 정보를 불러오고 있습니다...</p>
    {:else}
        <div class="character-wrapper">
            <div>
                <Stat bind:ability_list="{ability_list}" bind:armor="{armor}" bind:hp="{hp}" />
            </div>

            <div>
                <Face
                    bind:name="{name}"
                    bind:exp="{exp}"
                    bind:lv="{lv}"
                    bind:note="{note}"
                    bind:image_url="{image_url}" />
            </div>

            <div>
                <Item bind:item_list="{item_list}" />
            </div>
        </div>
    {/if}
</div>

<style>
    .character-wrapper {
        display: flex;
        flex-wrap: nowrap;
    }
</style>
