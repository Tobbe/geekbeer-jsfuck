<script>
    export let code;

    let result = '';
    let codeLength = code ? code.length : 0;
    
    function formatResult(result) {
        if (result === undefined) {
            return 'undefined';
        } else if (typeof result === 'string') {
            return '"' + result + '"';
        } else if (Array.isArray(result)) {
            return '[' + result.map(r => formatResult(r)) + ']';
        } else if (typeof result === 'function') {
            const fname = result.toString().match(/\w+/g)[1];
            return '<em>f ' + fname + '()</em>';
        }

        return result;
    }

	function keyHandler(event) {
        if (event.key.length === 1 || event.key === 'Backspace' || event.key === 'Delete' || event.key === 'Space') {
            result = '';
        }

		if (event.key === 'Enter' && !event.shiftKey) {
			console.log('code', code);
            result = Function('return ' + code)();
            result = formatResult(result);
            console.log('result', result);
            codeLength = code.length;

			event.preventDefault();
			return false;
		}
	}
</script>

<style>
	.input:focus {
		outline: none;
    }

    .result {
        color: transparent;
    }
    
    .result.hasResult {
        color: #696969;
    }
</style>

<div class="edit-line active">
	<div
		contenteditable
		class="input"
		spellcheck="false"
		on:keydown={keyHandler}
		bind:textContent={code}
	>
	</div>
    <div class="result" class:hasResult={result !== ''}>
        === {@html result}
    </div>
</div>