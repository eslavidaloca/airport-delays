<script>
	import { goto } from "$app/navigation";
</script>

<svelte:head>
	<title>Airports</title>
</svelte:head>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Let's fly together today!</h1>
		<p>Start by choosing either option:</p>
		<div class="grid grid-cols-2 gap-2">
			<button on:click={() => goto('/search/flights')} class="btn variant-ghost-tertiary hover:bg-tertiary-700">Search flights</button>
			<button on:click={() => goto('/search/airports')} class="btn variant-ghost-tertiary hover:bg-tertiary-700">Search airports</button>
		</div>
	</div>
</div>