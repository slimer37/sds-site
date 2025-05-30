<script>
	let { children } = $props();
</script>

<nav>
	<img src="/dino.svg" alt="Stupid Dino Studios" width="64" height="64">
	<a href="/">home</a>
	<a href="/about">about</a>
</nav>

{@render children()}

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
	<link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
</svelte:head>

<style>
	nav {
		display: flex;
		align-items: center;
		gap: 1rem;
		border-bottom: 1px solid black;
	}

	:global(body) {
		font-family: "Roboto", sans-serif;
		font-optical-sizing: auto;
		font-style: normal;
		font-variation-settings:
		"wdth" 100;

		margin-top: 0;
	}
</style>