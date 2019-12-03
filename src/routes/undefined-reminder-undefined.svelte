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
</style>

<Reminder />

<div class="inner-container">
	<div>[][+[]]</div>
	<div class="result">=== undefined</div>
</div>
