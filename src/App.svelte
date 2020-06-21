<script>
	import Card from './Card.svelte';
	import Array from './Array.svelte';
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	let files;
	let content;
	$: todoList = [];
	const regex = /TODO: \w.*/g;

	function handleFiles() {
		let reader = new FileReader();
		reader.readAsText(files[0])

		reader.onload = function(event) {
			content = event.target.result;
			
			console.log(content);
		}
	}

$: {
	if (content) {
		let listContent = content.match(regex);
		for (let i=0; i<listContent.length; i++) {
			todoList.push({
				todo: listContent[i].replace("TODO: ",""),
				done: false,
			});
		}
	}
}

	let chk = false;

</script>

<main>

<input type="file" bind:files on:change={handleFiles}>
{#if todoList.length > 0}
{#each todoList as item, i}
	<Card cardContent={item.todo} cardNum={i+1} bind:x={item.done}/>
{/each}
{:else}
	<p>Connect a file.</p>
{/if}

</main>

<style>

</style>