<script lang='ts'>
    type User = {
        name: string,
        age: number
    }

    let userArr: Array<User> = [
        {
            name: 'jeff',
            age: 24
        },
        {
            name: 'jane',
            age: 22
        },
        {
            name: 'john',
            age: 68
        }
    ]

    function pop() {
        userArr = userArr.slice(1)
    }
</script>

<section>
    <h1>Manipulating and iterating over an array of objs</h1>

    {#each userArr as user, idx}
        <p>{user.name} is at index {idx}</p>
    {/each}

    <button on:click={pop}>
       Delete lowest user index
    </button>
</section>