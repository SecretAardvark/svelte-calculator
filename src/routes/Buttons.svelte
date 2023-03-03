<script>
	export let numbers;
	// export let display;
	export let addDigit;
	export let getResult;
</script>

<div class="row justify-content-around">
	{#each numbers as num, i}
		{#if i == 4}
			<div class="col-2">
				<button type="button" class="btn btn-secondary" on:click={(e) => addDigit(e)} value={num}
					>{num}</button
				>
			</div>
		{:else if num === '='}
			<div class="col-1">
				<button
					type="button"
					class="btn btn-secondary"
					on:click={(display) => getResult(display)}
					value={num}>{num}</button
				>
			</div>
		{:else}
			<div class="col-1">
				<button type="button" class="btn btn-secondary" on:click={(e) => addDigit(e)} value={num}
					>{num}</button
				>
			</div>
		{/if}
	{/each}
</div>

<style>
	div.row {
		padding-top: 5px;
	}
</style>
