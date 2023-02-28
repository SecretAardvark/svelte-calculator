<script>
	import { Styles } from 'sveltestrap';
	import { Container, Col, Button, Row } from 'sveltestrap';
	let display = '0';

	const addDigit = () => {
		console.log(this.innerHTML);
	};

	const getResult = () => {
		console.log(display);
		//eval(display)
	};
</script>

<div>
	<div class="bg-dark container" id="container">
		<div class="row justify-content-around">
			<div class="col-auto">
				<input class="display" type="text" id="result" value={display} disabled />
			</div>
			<div class="col"><div class="btn btn-secondary">C</div></div>
			<div class="col"><div class="btn btn-secondary">/</div></div>
		</div>
		<div class="row justify-content-around">
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={() => addDigit()} value="1"
					>1</button
				>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>2</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => console.log(this.innerHTML)}>3</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>4</button>
			</div>
			<div class="col-2">
				<button class="btn btn-secondary" on:click={() => addDigit()}>+</button>
			</div>
		</div>
		<div class="row justify-content-around">
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={() => addDigit()}>5</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>6</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>7</button>
			</div>

			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>8</button>
			</div>
			<div class="col-2">
				<button class="btn btn-secondary" on:click={() => addDigit()}>-</button>
			</div>
		</div>
		<div class="row justify-content-around">
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={() => addDigit()}>9</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>0</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => addDigit()}>.</button>
			</div>
			<div class="col-1">
				<button class="btn btn-secondary" on:click={() => getResult()}>=</button>
			</div>
			<div class="col-2">
				<button class="btn btn-secondary" on:click={() => addDigit()}>*</button>
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
