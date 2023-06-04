<script lang="ts">
    let errMsg: string = ''
    let map: {[key: string]: string} = {
        '1': 'one',
        '2': 'two',
        '3': 'three',
        '4': 'four'
    }
    let newMapEntry: {key: string, value: string} = {
        key: '',
        value: ''
    }

    function updateNewMapKey(): void {
        errMsg = ''

        if (newMapEntry.key === '') {
            errMsg = 'Key cannot be empty'
            return
        } else if (newMapEntry.value === '') {
            errMsg = 'Value cannot be empty'
            return
        }

        map[newMapEntry.key] = newMapEntry.value
    }
</script>

<section>
    <p style="color: red;">{errMsg}</p>
    
    {#each Object.keys(map) as key}
        <p>{key} is {map[key]}</p>
    {/each}

    <form on:submit={updateNewMapKey}>
        <h3>Add a new value to the map</h3>
        <input
            type='text'
            placeholder="New Map Key"
            on:change={e => newMapEntry.key = e.currentTarget.value}
        />

        <input
            type='text'
            placeholder="New Map Value"
            on:change={e => newMapEntry.value = e.currentTarget.value}
        />

        <button type='submit'>Add New Map Entry</button>
    </form>
</section>

<style>
    form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin-top: 10px;
    }

    :is(form input, form button) {
        margin-top: 10px;
    }
</style>