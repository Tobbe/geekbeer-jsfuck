<style>
	#reminder {
		position: fixed;
		top: 3rem;
		right: 3rem;
		font-size: 1.4rem;
		white-space: pre;
		line-height: 0.8;
		text-align: left;
	}

	.zero {
		color: red;
	}

	.undefined {
		color: blueviolet;
	}
</style>

<div id="reminder">
	<div><span class="zero">+[]</span>     === 0      </div>
	<div><span class="undefined">[][+[]]</span> === undefined</div>
</div>