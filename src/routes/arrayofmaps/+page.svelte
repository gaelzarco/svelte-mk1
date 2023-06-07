<script lang='ts'>
    type User = {
        name: string,
        age: number
    }
    let jeff: User = {
        name: 'john',
        age: 12
    }
    let jane: User = {
        name: 'jane',
        age: 18
    }
    let god: User = {
        name: 'god',
        age: 40000
    }

    const array: User[] = [jeff, jane, god]
</script>

<section>
    <h1>Under construction</h1>

    {#each array as user, idx}
        <p>{user.name} is at index {idx}</p>
    {/each}
</section>