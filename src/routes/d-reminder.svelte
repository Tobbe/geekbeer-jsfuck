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

	.undefined {
		color: blueviolet;
	}

	.nwr {
		white-space: nowrap;
	}
</style>

<Reminder />

<div class="inner-container">
	<div>
		[[]+<span class="undefined">[][+[]]</span>][<span class="zero">+[]</span>]<wbr /><span class="nwr"
		>[++[<span class="zero">+[]</span>][<span class="zero">+[]</span>]</span> +
		<span class="nwr">++[<span class="zero">+[]</span>][<span class="zero">+[]</span>]</span>]
	</div>
	<div class="result">=== "d"</div>
</div>