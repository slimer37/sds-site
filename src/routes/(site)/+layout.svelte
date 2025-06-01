<script>
	let { children } = $props();
</script>

<nav>
	<img src="/dino.svg" alt="Stupid Dino Studios" width="64" height="64">
	<a href="/">home</a>
	<a href="/about">about</a>
</nav>

{@render children()}

<style>
	nav {
		display: flex;
		align-items: center;
		gap: 1rem;
		border-bottom: 1px solid black;

		position: absolute;
		width: 100vw;
		left: 0;
		top: 0;

		height: 64px;
	}

	:global(body) {
		margin-top: 72px;
	}
</style>