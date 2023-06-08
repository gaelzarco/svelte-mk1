<script lang='ts'>
    async function fetchData() {
        const res = await fetch('https://amiiboapi.com/api/amiibo/?name=Toon Zelda - The Wind Waker')
        const data = await res.json()

        if (res.ok) return data.amiibo[0].character
        else throw new Error('Something went wrong...')
    }

    let promise = fetchData()

    function handleClick() {
        promise = fetchData()
    }

</script>

<section>
    <h1>Working with async data fetching in Svelte</h1>

    <button on:click={handleClick}>
       refetch amiibo
    </button>

    {#await promise}
        <p>...waiting</p>
    {:then amiibo}
        <p>The amiibo is {amiibo}</p>
    {:catch error}
        <p style="color: red">{error.message}</p>
    {/await}
</section>

<style>

</style>