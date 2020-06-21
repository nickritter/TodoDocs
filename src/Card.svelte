<script>
export let cardContent;
export let cardNum;
//export let lineNumber = 0;
export let x = false; //bool

</script>

<main>
	<input type="checkbox" name="" id="completeToggle-{cardNum}" class="todoChk" bind:checked={x}>
	<!--p class="lineNumber">{lineNumber}</p-->
	<p class="todoText">{cardContent}</p>
</main>

<style>
	main {
		display:flex;
		align-items: center;
		border: 1px solid grey;
		padding: 0.5em 2em;
		border-radius: 0.5em;
		margin: 0.1em;
	}

	.todoChk {
		margin: 15px;
		color: grey;
		font-size: 0.5em;
	}
</style>