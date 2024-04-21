<script>

  let dataSet = [1,6,4,2,5]

const RandomList = () => {
    dataSet = []
    for (let i = 0; i < 5; i++) {
      dataSet.push(Math.floor(Math.random() * 9) + 1)
    }

}
		
const bubbleSort = () => {
	let done = false;
	while (!done) {
		done = true;
		for (let i = 0; i < dataSet.length; i++) {
			if (dataSet[i] && dataSet[i + 1] && dataSet[i] > dataSet[i + 1]) {	
				[dataSet[i], dataSet[i + 1]] = [dataSet[i + 1], dataSet[i]];
				done = false;
			}
		}
	}
}
	
</script>

<div class="text-center mt-12 text-teal-600">
	<div class="text-4xl font-bold">Bubble Sort</div>
	<div class="text-2xl font-semibold">Svelte Example</div>	
</div>

<div class="flex justify-center my-12 font-bold text-3xl">
	<div>
		{#each dataSet as item, index (index)}
			<span class="m-4 p-4 bg-teal-600 text-white rounded-md">{item}</span>
		{/each}
	</div>
</div>

<div class="flex justify-center">
	<button on:click|preventDefault={RandomList} class="my-2 mx-4 py-2 px-4 bg-teal-600 border-2 text-white border-teal-600 rounded-md hover:text-teal-600 hover:bg-white duration-300 hover:scale-105 hover:-translate-y-2">
		Randomize List
	</button>

	<button on:click|preventDefault={bubbleSort} class="my-2 mx-4 py-2 px-4 border-teal-600 border-2 text-teal-600 rounded-md hover:text-white hover:bg-teal-600 duration-300 hover:scale-105 hover:-translate-y-2">
		Sort List
	</button>
</div>


	




