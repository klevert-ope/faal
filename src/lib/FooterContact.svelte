<script lang="ts">
	import { Icon } from 'svelte-icons-pack';
	import { TrOutlineMailFast } from 'svelte-icons-pack/tr';
	import { BsTelephoneFill } from 'svelte-icons-pack/bs';

	let currentYear: number;
	const date = new Date();
	currentYear = date.getFullYear();
</script>

<section class="bg-green">
	<div class="container h-svh">
		<h5 class="font-xl text-orange font-Square-Grotesk margin-y-md text-white">
			Fleet Associates Africa Ltd
		</h5>
		<div class="font-medium font-md text-white">
			<p>Queens Park Court Off Eastern Bypass, Embakasi</p>
			<p>P.O. Box 772-00521</p>
			<p>Nairobi, Kenya</p>
		</div>
		<div class="flex-center">
			<p
				class="font-xl text-orange font-medium font-Square-Grotesk place-center">
				Talk To Us ...
			</p>
			<div class="contacts">
				<div class="flex-row">
					<Icon color="var(--white)" size="44" src={TrOutlineMailFast} />
					<a class="font-md"
						 href="mailto:info@faaafrica.com">info@faaafrica.com</a>
				</div>
				<div class="flex-row">
					<Icon color="var(--white)" size="24" src={BsTelephoneFill} />
					<a class="font-md"
						 href="tel:+254728764014">+254728764014</a>
				</div>
			</div>
		</div>
		<div class="place-bottom">
			<small class="font-xs font-medium text-white">
				FAA &copy; {currentYear} All rights reserved.
			</small>
		</div>
	</div>
</section>

<style>
	.container {
		position: relative;
		width: 100%;
		height: 100%;
		margin-right: auto;
		margin-left: auto;
		padding: var(--sm-px15);

		@media (min-width: 540px) {
			width: 540px;
			}
		@media (min-width: 720px) {
			width: 720px;
			}
		@media (min-width: 960px) {
			width: 960px;
			}
		@media (min-width: 1140px) {
			width: 1140px;
			}
		}

	.text-white {
		color: var(--white);
		}

	.font-xl {
		font-size: calc(clamp(1.7rem, 1.3933rem + 1.2584vw, 2.4rem));
		}

	.font-md {
		font-size: calc(clamp(1.1rem, 1.0124rem + 0.3596vw, 1.3rem));
		}

	.font-xs {
		font-size: calc(clamp(0.65rem, 0.6062rem + 0.1798vw, 0.75rem));
		}

	.font-Square-Grotesk {
		font-family: 'Square Grotesk', sans-serif;
		}

	.font-medium {
		font-weight: 500;
		}

	.margin-y-md {
		margin-top: var(--md-px20);
		margin-bottom: var(--sm-px15);
		}

	.text-orange {
		color: var(--red);
		}

	.bg-green {
		background-color: var(--green);
		}

	.h-svh {
		min-height: 80svh;
		}

	.flex-center {
		position: absolute;
		top: 50%;
		left: 50%;
		display: flex;
		flex-direction: column;
		transform: translate(-50%, -50%);
		}

	a {
		margin-top: var(--xs-px10);
		margin-bottom: var(--xs-px10);
		margin-left: var(--xs-px10);
		text-decoration: none;
		color: var(--white);
		}

	a:hover {
		color: var(--red);
		}

	.place-bottom {
		position: absolute;
		right: 0;
		bottom: 20px;
		left: 0;
		display: flex;
		align-items: center;
		justify-content: center;
		}

	.contacts {
		display: flex;
		flex-direction: column;
		}

	.flex-row {
		display: flex;
		align-items: center;
		flex-direction: row;
		justify-content: center;
		}
</style>
