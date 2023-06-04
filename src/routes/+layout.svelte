<script>
	import './styles.css';
	import NavBar from '../components/NavBar.svelte'
</script>

<main class="app">
	<NavBar />
	<slot />
</main>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100%;
		min-width: 100%;
		align-items: center;
	}
</style>
