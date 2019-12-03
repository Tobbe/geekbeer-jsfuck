<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
	main {
		text-align: center;
		font-size: 3rem;
		box-sizing: border-box;
	}

	main.center {
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		width: 100%;
		padding: 1.2rem;
	}
</style>

{#if segment.indexOf('reminder') >= 0}
	<main>
		<slot></slot>
	</main>
{:else}
	<main class="center">
		<slot></slot>
	</main>
{/if}
<Nav {segment} />