<script lang='ts'>
    let selectedMap: string = '1'

    type nestedMapType = {
        [key: string]: {
            [key: string]: string
        }
    }

    let nestedMap: nestedMapType = {
        '1': {
            '1': 'this',
            '2': 'is',
            '3': 'map',
            '4': 'one'
        },
        '2': {
            '1': 'nice.',
            '2': 'its',
            '3': 'map',
            '4': 'two'
        },
        '3': {
            '1': 'map',
            '2': 'three',
            '3': 'is',
            '4': 'cool'
        },
        '4': {
            '1': 'nah',
            '2': 'this',
            '3': 'is',
            '4': 'four'
        }
    }

    function updateSelectedMap(e: Event): void {
        selectedMap = (e.currentTarget as HTMLButtonElement).id
    }

</script>

<section>
    <h4>Working with nested Maps</h4>
    <div class='map-selection'>
        {#each Object.keys(nestedMap) as key}
            <button 
                id={key}
                on:click={updateSelectedMap}
                >{key}</button>
        {/each}
    </div>

    {#each Object.keys(nestedMap[selectedMap]) as nestedKey}
        <p>{nestedMap[selectedMap][nestedKey]}</p>
    {/each}
</section>

<style>
    section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .map-selection {
        display: inline-flex;
        align-items: center;
        justify-content: center;
    }

    .map-selection button {
        margin-inline: 10px;
        width: 50px;
    }
</style>