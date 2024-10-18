<svelte:head>
	<title>FLEET ASSOCIATES AFRICA</title>
	<meta
		content="Fleet Associates Africa ltd a leading African organization started in the year 2015 in Kenya by a group of experts specializing in fleet management.It is the only organization in the region with the capability of providing fleet services end to end under one roof. It does this through provision of consultancy,training,research and undertaking various fleet practical projects.
		Our main objective is to fill  the management gaps existing in the fleet industry, sectors, and individual organizations with a view to reduce risks related to fleet investments, improving efficiency, safety, productivity and reducing overall transportation and staff costs and thus improving the bottom line."
		name="description" />
</svelte:head>

<script lang="ts">

	interface Clients {
		text: string;
	}

	let clients: Clients[] = [
		{ text: 'Kenya transporters Association' },
		{ text: 'Northern corridor Transit and transport Authority' },
		{ text: 'Cargill Ltd' },
		{ text: 'Transeast ltd' },
		{ text: 'Ufanisi Transporters' },
		{ text: 'Tristar Group' },
		{ text: 'SOS schools' },
		{ text: 'Oshwal Academy Group of Schools' },
		{ text: 'Trakana Ltd' },
		{ text: 'Trade mark east Africa' },
		{ text: 'Dodwell EA Ltd' },
		{ text: 'Great Lakes freight ltd' }
	];
</script>

<section class="container margin-bottom-lg">
	<h1 class="title-intro text-orange font-Square-Grotesk">
		The Fleet Experts
	</h1>
	<div class="intro center-div text-center">
		<p class="font-xs font-medium">Since 2015</p>
		<p class="font-md font-medium large-max-width">
			We are a leading Kenyan organization, that empowers
			businesses across Africa to achieve peak fleet performance. We're the only
			regional provider offering a comprehensive suite of end-to-end fleet
			management solutions under one roof.
		</p>
	</div>
	<div class="fleet1">
		<p></p>
	</div>
	<div class="fleet2 border-top">
		<h2 class="title3 text-orange font-xl font-medium font-Square-Grotesk">
			Our Approach To Fleet Business
		</h2>
		<div class="fleet-img">
			<img
				alt="Fleet Management Approach"
				fetchpriority="high"
				loading="eager"
				src="https://res.cloudinary.com/dy9jpurpz/image/upload/v1717156088/oselzxpuntxwquc21mzj.png"
			/>
		</div>
	</div>
	<h3
		class="font-medium text-orange font-xl font-Square-Grotesk margin-y-lg text-center">
		Our Clients
	</h3>
	<ul class="flex-col">
		{#each clients as client (client)}
			<li class="font-md clients text-center">{client.text}</li>
		{/each}
	</ul>
</section>


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

	.font-Square-Grotesk {
		font-family: 'Square Grotesk', sans-serif;
		}

	.title-intro {
		font-size: 12vw;
		margin-top: var(--lg-px40);
		margin-bottom: var(--sm-px15);
		}

	.text-orange {
		color: var(--red);
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

	.font-medium {
		font-weight: 500;
		}

	.large-max-width {
		max-width: var(--large-max-width);
		}

	.center-div {
		display: flex;
		align-items: center;
		flex-flow: column;
		justify-content: center;
		}

	.flex-col {
		display: flex;
		flex-direction: column;
		}

	.text-center {
		text-align: center;
		}

	.fleet-img {
		padding-top: var(--sm-px15);
		padding-bottom: var(--sm-px15);
		}

	img {
		width: 600px;
		max-width: 100%;
		height: auto;
		border-radius: 5px;
		background-color: white;
		}

	@media (max-width: 719px) {
		.fleet-img {
			max-width: var(--medium-max-width);
			}
		}

	@media (min-width: 720px) {
		.fleet-img {
			max-width: var(--large-max-width);
			}
		}

	.fleet1 {
		margin-top: var(--lg-px40);
		padding-top: var(--xs-px10);
		}

	.fleet2 {
		margin-top: var(--lg-px40);
		padding-top: var(--xs-px10);
		}

	.border-top {
		border-top: solid 1px black;
		}

	.clients {
		font-weight: 500;
		display: flex;
		flex-flow: column;
		margin-bottom: 20px;
		padding-top: var(--xs-px10);
		text-wrap: balance;
		border-top: solid 1px black;
		}

	.margin-y-lg {
		margin-top: var(--lg-px40);
		margin-bottom: var(--md-px20);
		}

	.margin-bottom-lg {
		margin-bottom: var(--lg-px40);
		}
</style>

