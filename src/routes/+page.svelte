<script>
	import { goto } from "$app/navigation";

	// import { openDrawer } from "../components/DrawerSkeleton.svelte";
	
</script>

<svelte:head>
	<title>Home</title>
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

<!-- <div class="container mx-auto p-8 space-y-8">
	<h1 class="h1">Hello Skeleton</h1>
	<p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
	<section>
		<a class="btn variant-filled-primary" href="https://kit.svelte.dev/">SvelteKit</a>
		<a class="btn variant-filled-secondary" href="https://tailwindcss.com/">Tailwind</a>
		<a class="btn variant-filled-tertiary" href="https://github.com/">GitHub</a>
	</section>
</div> -->
