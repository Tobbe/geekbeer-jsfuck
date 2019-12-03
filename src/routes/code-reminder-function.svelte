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

	.new {
		color: green;
	}
</style>

<Reminder />

<div class="inner-container">
	<pre>Function(`
    <span class="new">co</span><span class="undefined">n</span>s<span class="new">t</span> <span class="undefined">n</span><span class="new">a</span>m<span class="undefined">e</span> = 'W<span class="new">o</span>rl<span class="undefined">d</span>';
    <span class="new">co</span><span class="undefined">n</span>s<span class="new">o</span>l<span class="undefined">e</span>.l<span class="new">o</span>g<span class="new">(</span>'H<span class="undefined">e</span>ll<span class="new">o</span> ' + <span class="undefined">n</span><span class="new">a</span>m<span class="undefined">e</span><span class="new">)</span>);
`)()</pre>
</div>