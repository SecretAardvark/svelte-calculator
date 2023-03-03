<script>
	import { Styles } from 'sveltestrap';
	import { evaluate } from 'mathjs';
	import Display from './display.svelte';
	import Buttons from './Buttons.svelte';
	let display = '0';

	const addDigit = (event) => {
		if (display === '0') {
			display = '';
		}
		display += event.target.value;
		console.log(display);
	};

	const getResult = () => {
		let result = evaluate(document.getElementById('result').value);
		display = result;
	};
	//TODO: Squeeze in a backspace button somewhere.
</script>

<div>
	<div class="bg-dark container" id="container">
		<Display bind:display {addDigit} />
		<!--display component-->
		<Buttons numbers={['1', '2', '3', '4', '+']} {addDigit} {getResult} />
		<Buttons numbers={['5', '6', '7', '8', '-']} {addDigit} {getResult} />
		<Buttons numbers={['9', '0', '.', '=', '*']} {addDigit} {getResult} />
	</div>
</div>
<Styles />

<style>
	#container {
		max-width: 350px;
		padding: 10px;
		margin-top: 50px;
	}
</style>
