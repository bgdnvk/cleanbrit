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

<div class='flex-auto border-2 border-red-500'>
	<h2 class='self-end border-2 border-red-100'>What type of service do you want?</h2>

	<form on:submit|preventDefault={handleSubmit} id='contact' class='flex-auto  '>
		<select class='border-2 border-red-500' bind:value={selected} on:blur="{() => answer = ''}">
			{#each questions as question}
				<option value={question}>
					{question.text}
				</option>
			{/each}
		</select>
	
		
		<label for='name' class='border-2 border-red-500'>Name:</label>
		<input id='name' class='border-2 border-red-500 bg-gray-200 focus:bg-white' type='text' bind:value={answer}>
	
		<label for='phone'>Phone:</label>
		<input id='phone' class='bg-gray-200 focus:bg-white' type='text'>
		<br>
	
	
		<!-- <textarea>Contact us here!</textarea> -->
		<textarea form='contact' class='w-full lg:w-3/4 xl:w-2/4 bg-gray-200 focus:bg-white'></textarea>
		<br>
	
	
		<button disabled={!answer} type=submit>
			Submit
		</button>
	</form>
	
	
	<p>selected service {selected ? selected.id : '[waiting...]'}</p>
</div>

