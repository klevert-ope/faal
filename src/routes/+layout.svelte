<svelte:head>
	<link href="https://fonts.cdnfonts.com/css/pp-neue-montreal" rel="stylesheet">
	<link href="https://fonts.cdnfonts.com/css/square-grotesk" rel="stylesheet">
</svelte:head>

<script lang="ts">
	import { onNavigate } from '$app/navigation';
	import Navlg from '$lib/NavLg.svelte';
	import NavSm from '$lib/NavSm.svelte';
	import Footer from '$lib/FooterContact.svelte';


	interface Navigation {
		complete: Promise<void>;
	}

	onNavigate((navigation: Navigation) => {
		if (!('startViewTransition' in document)) return;

		return new Promise<void>((resolve) => {
			(document as Document & {
				startViewTransition: Function
			}).startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});
</script>

<Navlg />
<NavSm />
<slot />
<Footer />

<style global>
	:root {
		font-family: 'PP Neue Montreal', sans-serif;
		color: var(--black);
		background-color: var(--white);
		--white: #f4f0e6;
		--black: #141414;
		--red: #FF692E;
		--green: #2B4212;
		--small-max-width: 200px;
		--medium-max-width: 450px;
		--large-max-width: 600px;
		--xlarge-max-width: 800px;
		--xxlarge-max-width: 1000px;
		--lg-px40: 40px;
		--md-px20: 20px;
		--sm-px15: 15px;
		--xs-px10: 10px;
		}

	:global(body) {
		overflow-x: hidden;
		margin: 0;
		padding: 0;
		}

	:root::view-transition-old(root) {
		animation: 90ms cubic-bezier(0.4, 0, 1, 1) both fade-out, 300ms cubic-bezier(0.4, 0, 0.2, 1) both slide-to-top;
		}

	:root::view-transition-new(root) {
		animation: 210ms cubic-bezier(0, 0, 0.2, 1) 90ms both fade-in, 300ms cubic-bezier(0.4, 0, 0.2, 1) both slide-from-bottom;
		}

	@media (prefers-reduced-motion: no-preference) {
		:root::view-transition-old(root) {
			animation: 90ms cubic-bezier(0.4, 0, 1, 1) both fade-out, 300ms cubic-bezier(0.4, 0, 0.2, 1) both slide-to-top;
			}

		:root::view-transition-new(root) {
			animation: 210ms cubic-bezier(0, 0, 0.2, 1) 90ms both fade-in, 300ms cubic-bezier(
					0.4,
					0,
					0.2,
					1
			) both slide-from-bottom;
			}
		}

	@keyframes fade-in {
		from {
			opacity: 0;
			}
		}

	@keyframes fade-out {
		to {
			opacity: 0;
			}
		}

	@keyframes slide-from-bottom {
		from {
			transform: translateY(100px);
			}
		}

	@keyframes slide-to-top {
		to {
			transform: translateY(-100px);
			}
		}
</style>
