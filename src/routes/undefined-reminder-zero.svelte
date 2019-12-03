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

<div id="reminder">
	<div><span class="zero">+[]</span>     === 0     </div>
	<div>[][<span class="zero">+[]</span>] === undefined</div>
</div>

<div class="inner-container">
	<div>[][+[]]</div>
	<div class="result">=== undefined</div>
</div>
