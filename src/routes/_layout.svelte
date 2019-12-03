<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
	main {
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		width: 100%;
		text-align: center;
		font-size: 3rem;
		padding: 1.2rem;
		box-sizing: border-box;
	}
</style>

<main>
	<slot></slot>
</main>
<Nav {segment} />