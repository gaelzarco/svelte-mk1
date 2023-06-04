<script lang='ts'>
    let user: {loggedIn: boolean} = { loggedIn: false }

    $: userLoginState = user.loggedIn ? 'Logged In' : 'Logged Out'
</script>

<section>
    <div id='btn-container'>
        {#if user.loggedIn}
            <button on:click={() => user.loggedIn = false}>Log Out</button>
        {:else}
            <button on:click={() => user.loggedIn = true}>Log In</button>
        {/if}
    </div>

    <p>{userLoginState}</p>
</section>

<style>
    #btn-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }
</style>