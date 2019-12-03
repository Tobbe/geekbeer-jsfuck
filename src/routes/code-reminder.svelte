<script>
	import Reminder from '../components/Reminder.svelte';
</script>

<style>
	.inner-container {
		position: absolute;
		top: 50%;
		width: 100%;
		transform: translateY(-50%);
		padding: 1.2rem;
		box-sizing: border-box;
		text-align: left;
	}

	.undefined {
		color: blueviolet;
	}
</style>

<Reminder />

<div class="inner-container">
	<pre>Function(`
    co<span class="undefined">n</span>st <span class="undefined">n</span>am<span class="undefined">e</span> = 'Worl<span class="undefined">d</span>';
    co<span class="undefined">n</span>sol<span class="undefined">e</span>.log('H<span class="undefined">e</span>llo ' + <span class="undefined">n</span>am<span class="undefined">e</span>);
`)()</pre>
</div>