<script>
	import '@skeletonlabs/skeleton/themes/theme-modern.css';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../app.postcss';
	import { AppShell, AppBar, AppRail, AppRailTile } from '@skeletonlabs/skeleton'
	import { writable } from 'svelte/store';

	$: storeValue = writable(1);;
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Skeleton</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://discord.gg/EXqV7W8MtY"
					target="_blank"
					rel="noreferrer"
				>
					Discord
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://twitter.com/SkeletonUI"
					target="_blank"
					rel="noreferrer"
				>
					Twitter
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/skeletonlabs/skeleton"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		<AppRail selected={storeValue}>
			<svelte:fragment slot="lead">
				<!-- AppRailTiles -->
				<AppRailTile label="Home" title="Home" value={1} tag="a" href="/home"></AppRailTile>
			</svelte:fragment>
			<!-- AppRailTiles -->
			<svelte:fragment slot="trail">
				<!-- AppRailTiles -->
			</svelte:fragment>
		</AppRail>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
