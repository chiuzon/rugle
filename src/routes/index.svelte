<script lang="ts">
	import { slide, fly } from 'svelte/transition';

	let answers = [];

	let answerInput = '';

	$: console.log(answers);
</script>

<div class="flex justify-center py-2 ">
	<div class="w-full lg:w-1/2 flex flex-col gap-2">
		<p class="bg-black text-white px-5 flex items-center">Value: 1000$ - 1000$</p>
		<p class="bg-black text-white px-5 flex items-center">Date: 05/26/2021 - 05/26/2021</p>
		<p class="bg-black text-white px-5 flex items-center">Audited: Yes</p>
	</div>
</div>
<hr />
<div class="flex justify-center py-2">
	<div class="w-full lg:w-1/2 flex flex-col gap-2">
		{#each Array(6) as answerId, index}
			{#if !answers[index]}
				<p transition:slide class=" bg-black p-4 inline-block" />
			{:else}
				<div transition:fly class="bg-black text-xl p-2 flex justify-center items-center gap-10">
					<span>🟩</span>
					<span>🟩</span>
					<span>🟩</span>
					<span>🟩</span>
					<span>🟩</span>
				</div>
			{/if}
		{/each}
	</div>
</div>
<hr />
<div class="flex justify-center py-2">
	<div class="w-full lg:w-1/2 flex flex-col gap-2">
		<input
			type="text"
			list="browsers"
			class="border-2 border-black w-full p-1"
			placeholder="Pick an exploited defi protocol"
			bind:value={answerInput}
			on:keypress={(e) => {
				if (e.charCode === 13 && answers.length < 6) answers = [...answers, answerInput];
			}}
		/>

		<datalist id="browsers">
			<option value="Ronin Network" />
			<option value="Poly Network" />
			<option value="Wormhole" />
			<option value="BitMart" />
			<option value="Compound" />
			<option value="Indexed Finance" />
		</datalist>
	</div>
</div>

<!-- #Tradle #33 1/6
🟩🟩🟩🟩🟩
https://oec.world/en/tradle -->

<!-- #Tradle #33 X/6
🟩🟩🟨⬜⬜
🟩🟨⬜⬜⬜
🟩🟩🟩🟩⬜
🟩⬜⬜⬜⬜
🟩🟩🟩🟩⬜
🟩🟩🟩🟩⬜
https://oec.world/en/tradle -->
