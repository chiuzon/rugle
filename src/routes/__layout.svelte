<script lang="ts">
	import '$lib/style.css';
</script>

<div class="flex justify-center">
	<div class="w-full lg:w-1/2 flex justify-between items-center p-2">
		<h1 class="text-3xl font-bold">Rugle</h1>

		<div class="flex gap-5">
			<a href="">Play</a>
			<a href="">How to Play</a>
		</div>
	</div>
</div>
<div class="flex justify-center">
	<div class="w-full lg:w-1/2 p-2">
		<slot />
	</div>
</div>
