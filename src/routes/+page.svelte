<script>
	import { Styles } from 'sveltestrap';
	import { evaluate } from 'mathjs';
	//import { Container, Col, Button, Row } from 'sveltestrap';
	let display = '0';

	const addDigit = (event) => {
		if (display === '0') {
			display = '';
		}
		display += event.target.value;
	};

	const getResult = () => {
		let result = evaluate(document.getElementById('result').value);
		display = result;
	};

	//TODO: Refactor. Display compononet + numbers component? Svelte might also be able to generate the buttons
	//		with a loop so it's not so boilerplate-y.
	//TODO: Squeeze in a backspace button somewhere.
</script>

<div>
	<div class="bg-dark container" id="container">
		<div class="row justify-content-around">
			<div class="col-auto">
				<input class="display" type="text" id="result" value={display} disabled />
			</div>
			<div class="col"><div class="btn btn-secondary" on:click={() => (display = '0')}>C</div></div>
			<div class="col">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="/">/</button>
			</div>
		</div>
		<!--display component-->
		<div class="row justify-content-around">
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={(e) => addDigit(e)} value="1"
					>1</button
				>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="2">2</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="3">3</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="4">4 </button>
			</div>
			<div class="col-2">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="+">+</button>
			</div>
		</div>
		<!--NumberRow component-->
		<div class="row justify-content-around">
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={(e) => addDigit(e)} value="5"
					>5</button
				>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="6">6</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="7">7</button>
			</div>

			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="8">8</button>
			</div>
			<div class="col-2">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="-">-</button>
			</div>
		</div>
		<div class="row justify-content-around">
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={(e) => addDigit(e)} value="9"
					>9</button
				>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="0">0</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value=".">.</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => getResult()} value="=">=</button>
			</div>
			<div class="col-2">
				<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="*">*</button>
			</div>
		</div>
	</div>
</div>
<Styles />

<style>
	#container {
		max-width: 350px;
		padding: 10px;
	}
	div.row {
		padding-top: 5px;
	}
</style>
