<script>
	export let display;
	export let addDigit;
</script>

<div class="row justify-content-around">
	<div class="col-auto">
		<input class="display" type="text" id="result" value={display} disabled />
	</div>
	<div class="col"><div class="btn btn-secondary" on:click={() => (display = '0')}>C</div></div>
	<div class="col">
		<button class="btn btn-secondary" on:click={(e) => addDigit(e)} value="/">/</button>
	</div>
</div>

<style>
	div.row {
		padding-top: 5px;
	}
</style>
