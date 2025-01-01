<script lang="ts">
	import { page } from '$app/state';

	const ROUTES = [
		{
			name: 'today',
			href: '/'
		},
		{
			name: 'overall',
			href: '/overall'
		}
	];
</script>

<header class="flex h-12 items-center justify-between gap-2 border-b border-neutral-800 px-5">
	<h1 class="text-lg font-bold">Descipline&period;svelte</h1>
	<nav>
		<ul class="flex gap-4">
			{#each ROUTES as route}
				<li>
					<a
						class={`${page.url.pathname !== route.href && 'opacity-50'} hover:underline`}
						href={route.href}>{route.name}</a
					>
				</li>
			{/each}
		</ul>
	</nav>
</header>
