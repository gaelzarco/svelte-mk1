<script lang="ts">
	import CounterComponent from "../components/CounterComponent.svelte";
	let countArr: Array<number> = [];
	let count: number = 0;

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
		Increment
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

	<CounterComponent currentVal={count} />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

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
