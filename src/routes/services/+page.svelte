<svelte:head>
	<title>SERVICES</title>
	<meta
		content="Unlock the full potential of your fleet with our comprehensive suite of end-to-end fleet management solutions. As a leading Kenyan organization, we empower businesses across Africa to achieve peak performance, providing the most comprehensive and integrated services in the region. Discover how our solutions can optimize your operations and drive success."
		name="description" />
</svelte:head>


<script lang="ts">
	interface Services {
		text: string;
	}

	let service1s: Services[] = [
		{ text: 'Fleet management training for investors and Directors' },
		{ text: 'Fleet Management training for Managers' },
		{ text: 'Driver &operator defensive and safety training' },
		{ text: 'Advanced driver training' }
	];

	let service2s: Services[] = [
		{ text: 'Fleet Asset management-Specification development, replacement planning and disposal services' },
		{ text: 'Fleet Maintenance-Development/review of fleet maintenance program, tyre management and Spare parts management' },
		{ text: 'Fleet business Management-Development/review of business plans, policies' },
		{ text: 'Fleet Safety-Development/review of fleet risk management systems' },
		{ text: 'Fleet Staffing-Development/review of staffing needs and recruitment and sourcing of fleet staff e.g. Fleet   Managers, drivers Mechanics' }
	];

	let service3s: Services[] = [
		{ text: 'Automotive–Maintenance and repairs and parts supplies' },
		{ text: 'Refrigeration &Air conditioning for commercial and domestic design maintenance, repairs and parts' },
		{ text: 'Auto electrical and electronic systems repairs' },
		{ text: 'Electrical–Installation ,maintenance and repairs' },
		{ text: 'Welding and fabrication' },
		{ text: 'Body repairs and respraying' }
	];
</script>

<section class="container margin-bottom-lg">
	<h1 class="title-intro font-Square-Grotesk text-orange">Services</h1>

	<h3
		class="service1 padding-bottom-xs font-normal text-orange font-xl font-Square-Grotesk">
		Human Resource Empowerment
	</h3>
	<ul>
		{#each service1s as service1 (service1)}
			<li class="font-md">{service1.text}</li>
		{/each}
	</ul>

	<h3
		class="service1 padding-bottom-xs font-normal margin-top-md text-orange font-xl font-Square-Grotesk">
		Fleet Consultancy Projects
	</h3>
	<ul>
		{#each service2s as service2 (service2)}
			<li class="font-md">{service2.text}</li>
		{/each}
	</ul>

	<h3
		class="service1 padding-bottom-xs font-normal margin-top-md text-orange font-xl font-Square-Grotesk">
		Maintenance Projects
	</h3>
	<ul>
		{#each service3s as service3 (service3)}
			<li class="font-md">{service3.text}</li>
		{/each}
	</ul>

	<h4 class="padding-y-sm text-orange font-Square-Grotesk font-normal font-xl">
		Technology & Data Driven Solutions
	</h4>
	<p class="font-medium font-md">
		All our solutions are based on real data and not any other adhoc decisions
	</p>

	<h4 class="padding-y-sm text-orange font-Square-Grotesk font-normal font-xl">
		Technical Support
	</h4>
	<p class="font-medium font-md">
		By well trained, experienced and competent staff
	</p>
</section>

<style>
	.container {
		width: 100%;
		margin-right: auto;
		margin-left: auto;
		padding-right: var(--sm-px15);
		padding-left: var(--sm-px15);

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

	.title-intro {
		font-size: 10vw;
		margin-top: var(--md-px20);
		margin-bottom: var(--md-px20);
		}

	.text-orange {
		color: var(--red);
		}

	.font-Square-Grotesk {
		font-family: 'Square Grotesk', sans-serif;
		}

	.font-xl {
		font-size: calc(clamp(1.7rem, 1.3933rem + 1.2584vw, 2.4rem));
		}

	.font-md {
		font-size: calc(clamp(1.1rem, 1.0124rem + 0.3596vw, 1.3rem));
		}

	.font-normal {
		font-weight: 450;
		}

	.padding-bottom-xs {
		padding-bottom: var(--xs-px10);
		}

	li {
		font-weight: 500;
		display: flex;
		flex-flow: column;
		margin-left: var(--sm-px15);
		padding: var(--xs-px10);
		text-wrap: balance;
		border-top: solid 1px black;
		}

	.margin-top-md {
		margin-top: var(--md-px20);
		}

	.font-medium {
		font-weight: 500;
		}

	.padding-y-sm {
		padding-top: var(--sm-px15);
		padding-bottom: var(--sm-px15);
		}

	.margin-bottom-lg {
		margin-bottom: var(--lg-px40);
		}
</style>
