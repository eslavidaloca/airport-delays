<script>
	let searchInput = '';
</script>

<svelte:head>
	<title>Flights</title>
</svelte:head>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<input class="input" type="search" name="demo" bind:value={searchInput} placeholder="Search..." />
	</div>
</div>