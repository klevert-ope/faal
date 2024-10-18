<script lang="ts">
	import { get, writable } from 'svelte/store';
	import TimeDisplay from '$lib/TimeDisplay.svelte';
	import { fly } from 'svelte/transition';
	import { page } from '$app/stores';

	const isOpen = writable(false);
	let activeLink = writable<string>('');

	$: activeLink.set(get(page).url.pathname);

	function toggleMenu() {
		isOpen.update(value => !value);
		document.body.style.overflow = get(isOpen) ? 'hidden' : 'auto';
	}

	function handleNavigation(href: string) {
		toggleMenu();
		activeLink.set(href);
		setTimeout(() => {
			history.pushState({}, '', href);
			window.dispatchEvent(new Event('popstate'));
		}, 500);
	}

	const links: { path: string; label: string }[] = [
		{ path: '/', label: 'HOME' },
		{ path: '/services', label: 'SERVICES' },
		{ path: '/about', label: 'ABOUT' },
		{ path: '/faq', label: 'FAQ' }
	];
</script>

<nav class="container">
	<div class="menu-nav">
		<div class="flex-row-between">
			<h1 class="logo text-orange font-Square-Grotesk">FAA</h1>
			<button class="hamburger font-medium font-md text-orange" on:click={toggleMenu}>
				{#if $isOpen}
					CLOSE
				{:else}
					MENU
				{/if}
			</button>
		</div>
		<TimeDisplay />
	</div>
</nav>

{#if $isOpen}
	<div class="menu" transition:fly={{ y: -300, duration: 500 }}>
		<ul>
			{#each links as { path, label }, index}
				<li class="{$activeLink === path ? 'active-link' : ''} slide-up"
						style="opacity: 0; animation-delay: {350 + index * 100}ms">
					<a href={path} on:click={() => handleNavigation(path)}>{label}</a>
				</li>
			{/each}
		</ul>
	</div>
{/if}

<style>
	.container {
		width: 100%;
		margin-right: auto;
		margin-left: auto;
		padding-right: var(--sm-px15);
		padding-left: var(--sm-px15);
		}

	@media (min-width: 540px) {
		.container {
			width: 540px;
			}
		}
	@media (min-width: 720px) {
		.container {
			width: 720px;
			}
		}
	@media (min-width: 960px) {
		.container {
			width: 960px;
			}
		}
	@media (min-width: 1140px) {
		.container {
			width: 1140px;
			}
		}

	@media (min-width: 720px) {
		nav {
			display: none;
			}
		}

	@media (max-width: 719px) {
		nav {
			display: block;
			}
		}

	nav {
		position: sticky;
		z-index: 9999;
		top: 0;
		margin-bottom: var(--sm-px15);
			padding-top: var(--md-px20);
			padding-bottom: var(--md-px20);
		background-color: var(--green);
		box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.1);
	  view-transition-name: nav;
		}

	button {
		color: var(--black);
		all: unset;
		}

	.hamburger {
		cursor: pointer;
		}

	.menu {
		position: fixed;
		top: 0;
		left: 0;
		z-index: 9998;
		width: 100%;
		height: 100vh;
		padding: 20px;
		background-color: var(--green);
		display: flex;
		justify-content: center;
		align-items: center;
		transition: transform 0.5s ease-in-out, background-color 0.5s;
		}

	.menu a {
		font-size: 12vw;
		margin-bottom: 10px;
		text-decoration: none;
		color: var(--red);
		font-weight: 600;
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

	.font-medium {
		font-weight: 500;
		}

	.font-md {
		font-size: calc(clamp(1.1rem, 1.0124rem + 0.3596vw, 1.3rem));
		}

	ul > li {
		margin-bottom: var(--sm-px15);
		list-style: none;
		}

	.menu > ul {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
		margin: 0;
		padding: 0;
		}

	.active-link a {
		padding: 5px;
		transition: all 0.3s ease;
		color: var(--red);
		border-radius: 5px;
		background-color: var(--white);
		}

	.slide-up {
		animation: slideUp 0.5s ease-in-out forwards;
		}

	@keyframes slideUp {
		from {
			transform: translateY(100%);
			opacity: 0;
			}
		to {
			transform: translateY(0);
			opacity: 1;
			}
		}
</style>

