<svelte:head>
	<title>FAQ</title>
	<meta
		content="Explore answers to common questions about our fleet management solutions. Our FAQ page provides insights into how we empower businesses across Africa to achieve peak fleet performance. Discover valuable information about our comprehensive suite of services and find solutions to your fleet management queries."
		name="description" />
</svelte:head>

<script lang="ts">
	import { Icon } from 'svelte-icons-pack';
	import {
		BsArrowDownCircleFill,
		BsArrowUpCircleFill
	} from 'svelte-icons-pack/bs';
	import { slide } from 'svelte/transition';
	import { cubicInOut } from 'svelte/easing';

	interface FAQItem {
		question: string;
		answer: string;
	}

	let faqs: FAQItem[] = [
		{
			question: 'What is Fleet Associates Africa?',
			answer: 'Fleet Associates Africa (FAA) is a leading African organization established in Kenya in 2015 by fleet management experts. We are the only company in the region offering comprehensive, end-to-end fleet management solutions under one roof.'
		},
		{
			question: 'What services do you offer?',
			answer: 'FAA provides a wide range of fleet management services, including consultancy, training, research, and undertaking practical fleet projects.'
		},
		{
			question: 'How can your consultancy services benefit my organization?',
			answer: 'Our fleet management consultants have extensive experience and can help you design and implement a customized plan to optimize your fleet operations, saving you time and money.'
		},
		{
			question: 'What kind of training programs do you offer?',
			answer: 'We offer various training programs for fleet managers, drivers, and other personnel involved in fleet operations. These programs cover topics like safe driving practices, fuel efficiency techniques, and preventative maintenance.'
		},
		{
			question: 'Do you conduct research on fleet management?',
			answer: 'Yes, FAA actively researches the latest trends and best practices in fleet management. We use this knowledge to continuously improve our services and provide our clients with the most up-to-date solutions.'
		},
		{
			question: 'Why should I choose Fleet Associates Africa over other fleet management companies?',
			answer: 'FAA is the only company in the region offering comprehensive, end-to-end fleet management solutions under one roof. This allows us to provide a seamless and efficient service that meets all your fleet management needs.'
		},
		{
			question: 'How can I learn more about your services?',
			answer: 'Please visit our website or contact us directly. We would be happy to discuss your specific needs and how we can help you achieve your fleet management goals.'
		}
	];

	let openIndex: number | null = null;

	function toggleAnswer(index: number) {
		openIndex = openIndex === index ? null : index;
	}
</script>

<section class="container margin-bottom-lg">
	<h1 class="title-intro font-Square-Grotesk text-orange">FAQ</h1>
	<ul>
		{#each faqs as { question, answer }, index}
			<li>
				<div class="faq-item">
					<button
						on:click={() => toggleAnswer(index)}
						class="faq-question"
						style="all: unset; cursor: pointer;"
					>
            <span class="font-normal text-orange font-md font-Square-Grotesk">
              {question}
            </span>
					</button>
					<button on:click={() => toggleAnswer(index)} class="icon-pointer"
									style="all: unset; cursor: pointer;">
						{#if openIndex === index}
							<Icon color="var(--red)" size="24" src={BsArrowUpCircleFill} />
						{:else}
							<Icon color="var(--red)" size="24" src={BsArrowDownCircleFill} />
						{/if}
					</button>
				</div>
				{#if openIndex === index}
					<p class="font-medium answer font-md"
						 transition:slide="{{ duration: 800, easing: cubicInOut }}">
						{answer}
					</p>
				{/if}
			</li>
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

	ul {
		padding: 0;
		}

	li {
		margin-bottom: var(--lg-px40);
		list-style: none;
		}

	.faq-item {
		display: grid;
		align-items: center;
		width: 100%;
		grid-template-columns: 1fr auto;
		column-gap: 20px;
		}

	.faq-question {
		height: calc-size(auto);
		cursor: pointer;
		all: unset;
		}

	.icon-pointer {
		cursor: pointer;
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

	.font-md {
		font-size: calc(clamp(1.1rem, 1.0124rem + 0.3596vw, 1.3rem));
		}

	.font-normal {
		font-weight: 450;
		}

	.answer {
		max-width: var(--large-max-width);
		margin-top: var(--lg-px40);
		padding: var(--xs-px10);
		color: white;
		border-radius: 5px;
		background-color: var(--red);
		}

	.margin-bottom-lg {
		margin-bottom: var(--lg-px40);
		}

	p {
		padding: var(--xs-px10);
		}
</style>

