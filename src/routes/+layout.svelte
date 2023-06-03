<script>
	import './styles.css';
</script>

<main class="app">
	<slot />
</main>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		min-width: 100vw;
		align-items: center;
		justify-content: center;
		justify-items: center;
		text-align: center;
	}
</style>
