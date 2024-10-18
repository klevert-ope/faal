<svelte:head>
	<title>ABOUT</title>
	<meta
		content="Since 2015, our journey has been dedicated to empowering businesses across Africa to achieve peak fleet performance. Learn more about our story, mission, and commitment to providing comprehensive end-to-end fleet management solutions under one roof. Discover how we've evolved over the years to become a leading Kenyan organization in the fleet management industry."
		name="description" />
</svelte:head>

<script lang="ts">
	interface Lists {
		text: string;
	}

	let missions: Lists[] = [
		{ text: 'Partnership with clients' },
		{ text: 'To improve the quality of services and goods used in the industry' },
		{ text: 'To use technology to create visibility and ensure efficiency and effectiveness' },
		{ text: 'To empower staffs involved in fleet operations' }
	];

	let values: Lists[] = [
		{ text: 'Focus on our vision' },
		{ text: 'Professionalism – know our business well' },
		{ text: 'Honesty and integrity – to our business, customers and personal relations' },
		{ text: 'Quality, safety and environment – maximum compliance with best practices' }
	];

</script>

<section class="container margin-bottom-lg">
	<h1 class="title-intro font-Square-Grotesk text-orange">About</h1>
	<p class="font-md font-medium">
		Fleet Associates Africa ltd a leading African organization started in the
		year 2015 in Kenya by a group of experts specializing in fleet management.It
		is the only organization in the region with the capability of providing
		fleet services end to end under one roof. It does this through provision of
		consultancy,training,research and undertaking various fleet practical
		projects. Our main objective is to fill the management gaps existing in the
		fleet industry, sectors, and individual organizations with a view to reduce
		risks related to fleet investments, improving efficiency, safety,
		productivity and reducing overall transportation and staff costs and thus
		improving the bottom line.
	</p>

	<h4 class="padding-y-sm text-orange font-Square-Grotesk font-xl">Vision</h4>
	<p class="font-md font-medium">
		To be recognized as industrial leader in providing an efficient, safe and
		cost effective fleet management systems with a view to attaining fleet
		management excellence
	</p>

	<h4 class="padding-y-sm text-orange font-Square-Grotesk font-xl">Mission</h4>
	<ul>
		{#each missions as mission (mission)}
			<li class="font-md">{mission.text}</li>
		{/each}
	</ul>

	<h4 class="padding-y-sm text-orange font-Square-Grotesk font-xl">Value</h4>
	<ul>
		{#each values as value (value)}
			<li class="font-md">{value.text}</li>
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

	.text-orange {
		color: var(--red);
		}

	.font-Square-Grotesk {
		font-family: 'Square Grotesk', sans-serif;
		}

	.title-intro {
		font-size: 10vw;
		margin-top: var(--md-px20);
		margin-bottom: var(--md-px20);
		}

	.font-xl {
		font-size: calc(clamp(1.7rem, 1.3933rem + 1.2584vw, 2.4rem));
		}

	.font-md {
		font-size: calc(clamp(1.1rem, 1.0124rem + 0.3596vw, 1.3rem));
		}

	.font-medium {
		font-weight: 500;
		}

	.padding-y-sm {
		padding-top: var(--sm-px15);
		padding-bottom: var(--sm-px15);
		}

	li {
		font-weight: 500;
		margin-left: var(--sm-px15);
		padding: var(--xs-px10);
		list-style: disc;
		text-wrap: balance;
		}

	.margin-bottom-lg {
		margin-bottom: var(--lg-px40);
		}
</style>
