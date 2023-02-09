<script lang="ts">
	import Typewriter from 'svelte-typewriter';

	const words = [
		'group',
		'gutta',
		'gjengen',
		'fæmmen',
		'klassen',
		'kollektivet',
		'teamet',
		'kontoret',
		'fotballaget',
		'korpset',
		'bandet',
		'gruppa',
		'Variant'
	];

	const palette = [
		'#837647',
		'#B94338',
		'#863E5F',
		'#BB46A0',
		'#161354',
		'#A26931',
		'#757B2A',
		'#623A32',
		'#0C3283',
		'#9556A3',
		'#2F327B',
		'#602C12',
		'#537AA6',
		'#53606E',
		'#37779C',
		'#AC5525',
		'#3D4F20',
		'#931C33',
		'#956E46',
		'#BD5524',
		'#797575',
		'#6F7692',
		'#3D2930',
		'#43777F',
		'#2059B9',
		'#B82B4A',
		'#394047',
		'#438550',
		'#916D65',
		'#617F4B'
	];

	const bgColor: string = palette[Math.floor(Math.random() * palette.length)];
	const date = Intl.DateTimeFormat('nb-NO', {
		weekday: 'long',
		day: 'numeric',
		month: 'long'
	}).format(new Date());
</script>

<main style="--bg-color: {bgColor}">
	<header class="header">
		<div class="logo">
			<h1 class="synk">Synk.</h1>

			<Typewriter
				mode="loopRandom"
				keepCursorOnFinish
				interval={200}
				unwriteInterval={100}
				wordInterval={2750}
			>
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
		font-weight: 200;
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
		font-weight: 200;
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
