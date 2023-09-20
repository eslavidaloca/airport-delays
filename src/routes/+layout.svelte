<script lang="ts">
	import '../app.postcss';

	// Floating UI for Popups
	// import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	// import { storePopup } from '@skeletonlabs/skeleton';
	// storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
	import {
		AppShell,
		AppBar,
		Avatar,
		LightSwitch,
		AppRail,
		AppRailAnchor,
		AppRailTile,
		// drawerStore,
		initializeStores,
		Toast
	} from '@skeletonlabs/skeleton';
	// import DrawerSkeleton from '../components/DrawerSkeleton.svelte';

	initializeStores();
	let currentTile: number = 0;

	// $: positionClasses = $drawerStore.open ? 'translate-x-[50%]' : '';
</script>

<Toast />

<!-- App Shell -->
<!-- <AppShell class="transition-transform {positionClasses}"> -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar gridcolumns="grid-cols-3" slotdefault="place-self-center" slottrail="place-content-end">
			<svelte:fragment slot="lead">(icon)</svelte:fragment>
			<span class="text-xl">DataPort</span>
			<svelte:fragment slot="trail">
				<LightSwitch bglight="bg-primary-400 dark:bg-secondary-400" />
				<Avatar src="https://i.pravatar.cc/" />
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		<AppRail>
			<div class="tiles">
				<AppRailTile bind:group={currentTile} name="Home" value={0} title="Home">
					<svelte:fragment slot="lead">
						<div class="flex justify-center">
							<i class="fa-solid fa-house" />
						</div>
					</svelte:fragment>
					<span>Home</span>
				</AppRailTile>
			</div>
			<div class="tiles">
				<AppRailTile bind:group={currentTile} name="Airports" value={1} title="Airports">
					<svelte:fragment slot="lead">
						<div class="flex justify-center">
							<i class="fas fa-cart-flatbed-suitcase" />
						</div>
					</svelte:fragment>
					<span>Airports</span>
				</AppRailTile>
			</div>
			<div class="tiles">
				<AppRailTile bind:group={currentTile} name="Flights" value={2} title="Flights">
					<svelte:fragment slot="lead">
						<div class="flex justify-center">
							<i class="fa-solid fa-plane-departure" />
						</div>
					</svelte:fragment>
					<span>Flights</span>
				</AppRailTile>
			</div>
			<!-- --- -->
			<svelte:fragment slot="trail">
				<AppRailAnchor href="/" target="_blank" title="Account">(icon)</AppRailAnchor>
			</svelte:fragment>
		</AppRail>
	</svelte:fragment>
	<!-- (sidebarRight) -->
	<svelte:fragment slot="pageHeader"><slot name="pageHeader" /></svelte:fragment>
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter"><slot name="pageFooter" /></svelte:fragment>
	<!-- (footer) -->
</AppShell>

<!-- App Bar -->
<!-- <AppBar>
	<svelte:fragment slot="lead">
		<strong class="text-xl">DAirTAport</strong>
	</svelte:fragment>
	<svelte:fragment slot="trail">
		<LightSwitch bgLight='bg-primary-400 dark:bg-secondary-400' />
		
	</svelte:fragment>
</AppBar> -->

<style>
	.tiles:hover div {
		animation: bounce 1s infinite; /* Aplicar la animación de brinco */
	}
</style>