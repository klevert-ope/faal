<script lang="ts">
	import { onMount } from 'svelte';
	import { writable } from 'svelte/store';

	type IntervalID = number;

	export const location = writable<string>('Africa/Nairobi');

	const currentTime = writable(new Date().toLocaleTimeString(undefined, {
		timeZone: $location,
		hour: '2-digit',
		minute: '2-digit'
	}));

	let interval: IntervalID;

	const updateTime = () => {
		currentTime.set(new Date().toLocaleTimeString(undefined, {
			timeZone: $location,
			hour: '2-digit',
			minute: '2-digit'
		}));
	};

	onMount(() => {
		const locationSubscription = location.subscribe(value => {
			currentTime.set(new Date().toLocaleTimeString(undefined, {
				timeZone: value,
				hour: '2-digit',
				minute: '2-digit'
			}));
			updateTime();
		});

		interval = setInterval(updateTime, 1000);

		return () => {
			locationSubscription();
			clearInterval(interval);
		};
	});
</script>

<div class="flex-row">
	<p class="font-xs font-medium">{$currentTime}</p>
	<p class="padding-left font-xs font-medium">
		{$location}
	</p>
</div>

<style>
	.flex-row {
		display: flex;
		align-items: center;
		flex-direction: row;
		}

	.padding-left {
		padding-left: var(--xs-px10);
		}

	.font-xs {
		font-size: calc(clamp(0.65rem, 0.6062rem + 0.1798vw, 0.75rem));
		color: var(--red);
		}

	.font-medium {
		font-weight: 600;
		}
</style>
