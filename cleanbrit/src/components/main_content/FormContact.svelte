<!-- https://svelte.dev/tutorial/select-bindings -->
<script>
	let questions = [
		{ id: 1, text: `Service 1` },
		{ id: 2, text: `Service 2` },
		{ id: 3, text: `Just information` }
	];

	let selected;

	let answer = '';

	function handleSubmit() {
		alert(`answered question ${selected.id} (${selected.text}) with "${answer}"`);
	}
</script>

<style>
	input { display: block; width: 500px; max-width: 100%; }
</style>

<h2>What type of service do you want?</h2>

<form on:submit|preventDefault={handleSubmit}>
	<select bind:value={selected} on:blur="{() => answer = ''}">
		{#each questions as question}
			<option value={question}>
				{question.text}
			</option>
		{/each}
	</select>

	

	<input bind:value={answer}>

	<!-- <textarea>Contact us here!</textarea> -->


	<button disabled={!answer} type=submit>
		Submit
	</button>
</form>


<p>selected service {selected ? selected.id : '[waiting...]'}</p>