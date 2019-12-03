<script>
	export let segment;

	function keyHandler(event) {
		if (event.target.contentEditable !== 'true') {
			console.log('navigate');
		}
	}
</script>

<style>
	nav {
		position: absolute;
		bottom: 0;
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0 1em;
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	.selected {
		position: relative;
		display: inline-block;
	}

	.selected::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
	}
</style>

<svelte:window on:keydown={keyHandler} />

<nav>
	<ul>
		<li><a class:selected="{segment === undefined}" href=".">index</a></li>
		<li><a class:selected="{segment === 'jsfuck'}" href="jsfuck">jsfuck</a></li>
		<li><a class:selected="{segment === 'code'}" href="code">code</a></li>
		<li><a class:selected="{segment === 'code-wrapped'}" href="code-wrapped">code (wrapped)</a></li>
		<li><a class:selected="{segment === 'edit'}" href="edit">edit</a></li>
		<li><a class:selected="{segment === 'explain-0'}" href="explain-0">explain 0</a></li>
		<li><a class:selected="{segment === 'explain-empty'}" href="explain-empty">explain ''</a></li>
		<li><a class:selected="{segment === 'explain-result'}" href="explain-result">explain (result)</a></li>
		<li><a class:selected="{segment === 'a'}" href="a">a</a></li>
	</ul>
</nav>
