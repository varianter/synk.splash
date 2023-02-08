<script>
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
		'venninnegjengen',
		'Variant'
	];
</script>

<main>
	<div class="wrapper">
		<h1 class="synk">Synk.</h1>

		<Typewriter
			mode="loopOnce"
			keepCursorOnFinish
			interval="200"
			unwriteInterval="100"
			wordInterval="2750"
		>
			{#each words as word}
				<h1 class="typewriter">{word}</h1>
			{/each}
		</Typewriter>
	</div>

	<footer>Denne siden er under konstruksjon, følg med 😉🥁</footer>
</main>

<style>
	h1 {
		font-size: 3rem;
		font-weight: 500;
	}
	.wrapper {
		position: relative;
		display: flex;
		transform: translateX(-50%);
	}
	.typewriter {
		position: absolute;
		left: 100%;
		display: flex;
		margin-left: 2px;
		font-weight: 300;
		white-space: nowrap;
	}
	main {
		--cursor-width: 2px;

		background-color: #f1eddf;
		width: 100%;
		height: 100%;
		display: grid;
		place-content: center;
	}

	h1:after {
		margin-left: 2px;
	}

	footer {
		position: absolute;
		bottom: 5%;
		left: 50%;
		transform: translateX(-50%);
	}
</style>
