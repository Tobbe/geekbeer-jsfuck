<script>
	import * as sapper from '@sapper/app';

	export let segment;

	const routes = [
		'/',
		'jsfuck',
		'code',
		'code-wrapped',
		'edit',
		'explain-0',
		'explain-empty',
		'explain-result',
		'a',
		'undefined-reminder',
		'undefined-reminder-zero',
		'undefined-reminder-undefined',
		'plusplus-reminder',
		'two-reminder',
		'undefined-string-reminder',
		'd-reminder',
		'code-reminder',
		'function',
		'function-underline',
		'code-reminder-function',
		'full-reminder',
		'question',
	];

	$: segmentIndex = segment ? routes.indexOf(segment) : 0;

	function keyHandler(event) {
		if (event.target.contentEditable !== 'true') {
			if (event.key === 'ArrowRight') {
				const newIndex = Math.min(segmentIndex + 1, routes.length - 1);
				sapper.goto(routes[newIndex]);
			} else if (event.key === 'ArrowLeft') {
				const newIndex = Math.max(segmentIndex - 1, 0);
				sapper.goto(routes[newIndex]);
			} else if (event.key === '0') {
				sapper.goto(routes[0]);
			}
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
		display: none;
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
		<li><a class:selected="{segment === 'undefined-reminder'}" href="undefined-reminder">undefined (reminder)</a></li>
		<li><a class:selected="{segment === 'undefined-reminder-zero'}" href="undefined-reminder-zero">undefined (reminder 0)</a></li>
		<li><a class:selected="{segment === 'undefined-reminder-undefined'}" href="undefined-reminder-undefined">undefined (reminder undefined)</a></li>
		<li><a class:selected="{segment === 'plusplus-reminder'}" href="plusplus-reminder">plusplus (reminder)</a></li>
		<li><a class:selected="{segment === 'two-reminder'}" href="two-reminder">two (reminder)</a></li>
		<li><a class:selected="{segment === 'undefined-string-reminder'}" href="undefined-string-reminder">undefiend string (reminder)</a></li>
		<li><a class:selected="{segment === 'd-reminder'}" href="d-reminder">d (reminder)</a></li>
		<li><a class:selected="{segment === 'code-reminder'}" href="code-reminder">code (reminder)</a></li>
		<li><a class:selected="{segment === 'function'}" href="function">function</a></li>
		<li><a class:selected="{segment === 'function-underline'}" href="function-underline">function-underline</a></li>
		<li><a class:selected="{segment === 'code-reminder-function'}" href="code-reminder-function">code (reminder, function)</a></li>
		<li><a class:selected="{segment === 'full-reminder'}" href="full-reminder">full-reminder</a></li>
		<li><a class:selected="{segment === 'question'}" href="question">question</a></li>
	</ul>
</nav>
