<script lang="ts">
	let countArr: Array<number> = [];
	let count = 0;

	function increment() {
		count += 1;
		countArr = [...countArr, count]
	}

	$: doubled = count * 2;
</script>

<svelte:head>
	<title>SVELTE</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<button on:click={increment}>
		Count is: {count}
	</button>
	<p>Count doubled is: {doubled}</p>

	<div class='flex-nums'>
		<p>All values</p>
		{#each countArr as num}
			<p>
				{num}
			</p>
		{/each}
	</div>
</section>

<style>
	.flex-nums {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}

	.flex-nums p {
		margin: 0 10px;
	}
</style>
