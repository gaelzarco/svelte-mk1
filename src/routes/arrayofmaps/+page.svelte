<script lang='ts'>
    type User = {
        name: string,
        age: number
    }

    const array: Array<User> = [
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
</script>

<section>
    <h1>Under construction</h1>

    {#each array as user, idx}
        <p>{user.name} is at index {idx}</p>
    {/each}
</section>