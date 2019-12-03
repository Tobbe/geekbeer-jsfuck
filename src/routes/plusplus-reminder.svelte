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
	}

    .result {
        color: #696969;
	}
	
	.zero {
		color: red;
	}
</style>

<Reminder />

<div class="inner-container">
	<div>++[<span class="zero">+[]</span>][<span class="zero">+[]</span>]</div>
	<div class="result">=== 1</div>
</div>
