<script lang="ts">
	import Typewriter from 'svelte-typewriter';

	const words = [
		'gutta',
		'gjengen',
		'familien',
		'klassen',
		'kollektivet',
		'teamet',
		'kontoret',
		'fotballaget',
		'korpset',
		'bandet',
		'gruppa',
		'Variant',
		'syklubben',
		'kollokviegruppa',
		'alle',
		'søskenflokken',
		'nabolaget',
		'mc-klubben'
	];

	const date = Intl.DateTimeFormat('nb-NO', {
		weekday: 'long',
		day: 'numeric',
		month: 'long'
	}).format(new Date());
</script>

<main>
	<header class="header">
		<div class="logo">
			<h1 class="synk">Synk.</h1>

			<Typewriter mode="loopRandom" interval={200} unwriteInterval={100} wordInterval={2750}>
				{#each words as word}
					<h1 class="typewriter">{word}</h1>
				{/each}
			</Typewriter>
		</div>

		<h1 class="date">{date}</h1>
	</header>

	<p class="construction">Denne siden er under konstruksjon, vent og hør...</p>
</main>

<style>
	h1 {
		font-family: 'Recoleta', serif;
		font-weight: 500;
	}

	h1:after {
		margin-left: 2px;
	}

	.date {
		font-weight: 300;
	}

	@media screen and (max-width: 640px) {
		.date {
			display: none;
		}
	}

	.header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		padding: 2rem;
	}

	.logo {
		position: relative;
	}

	.typewriter {
		position: absolute;
		/* Shift text to fix alignment with thinner font. */
		top: 0.5px;
		left: 100%;
		display: flex;
		font-weight: 300;
		white-space: nowrap;
	}

	main {
		--cursor-width: 2px;
		--cursor-color: #fff;

		background-color: var(--bg-color);
		width: 100%;
		height: 100%;
		overflow: hidden;
		display: grid;
		grid-auto-flow: row;
		grid-template-rows: max-content;
	}

	.construction {
		text-align: center;
		margin: auto;
		flex-grow: 1;
		display: grid;
		place-content: center;
		padding: 1rem 1rem 8rem;
	}
</style>
