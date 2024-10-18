<script lang="ts">
	import { get, writable } from 'svelte/store';
	import { page } from '$app/stores';
	import TimeDisplay from './TimeDisplay.svelte';

	let activeLink = writable<string>('');

	const links: Array<{ path: string; label: string }> = [
		{ path: '/', label: 'HOME' },
		{ path: '/services', label: 'SERVICES' },
		{ path: '/about', label: 'ABOUT' },
		{ path: '/faq', label: 'FAQ' }
	];

	$: activeLink.set(get(page).url.pathname);

	const handleNavigation = (path: string) => {
		activeLink.set(path);
	};
</script>

<nav>
	<div class="flex-row-between padding-y padding-x center-contents">
		<h1 class="logo text-orange font-Square-Grotesk">FAA</h1>
		<ul class="flex-row-between bg-blur">
			{#each links as { path, label } (path)}
				<li class="{$activeLink === path ? 'active-link' : ''} font-xs">
					<a on:click={() => handleNavigation(path)} href={path}>{label}</a>
				</li>
			{/each}
		</ul>
		<TimeDisplay />
	</div>
</nav>


<style>
	@media (min-width: 720px) {
		nav {
			display: block;
			}
		}

	@media (max-width: 719px) {
		nav {
			display: none;
			}
		}

	nav {
		position: sticky;
		z-index: 999;
		top: 0;
		view-transition-name: nav;
		}

	.center-contents {
		align-content: center;
		}

	.flex-row-between {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		}

	.text-orange {
		color: var(--red);
		}

	.font-Square-Grotesk {
		font-family: 'Square Grotesk', sans-serif;
		}

	ul > li {
		margin-right: var(--sm-px15);
		margin-left: var(--sm-px15);
		list-style: none;
		}

	.padding-y {
		padding-top: var(--xs-px10);
		padding-bottom: var(--xs-px10);
		}

	.padding-x {
		padding-right: var(--xs-px10);
		padding-left: var(--xs-px10);
		}

	.bg-blur {
		padding: var(--xs-px10);
		border-radius: 8px;
		background-color: var(--green);
		box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.1);
		}

	ul > li > a {
		font-weight: 600;
		transition: all 0.3s ease;
		text-decoration: none;
		color: var(--red);
		}

	a:hover {
		padding: 5px;
		transition: all 0.3s ease;
		color: var(--red);
		border-radius: 5px;
		background-color: var(--white);
		}

	.active-link a {
		padding: 5px;
		transition: all 0.3s ease;
		color: var(--red);
		border-radius: 5px;
		background-color: var(--white);
		}

	.font-xs {
		font-size: calc(clamp(0.65rem, 0.6062rem + 0.1798vw, 0.75rem));
		}
</style>
