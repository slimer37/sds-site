<script lang='ts'>
	let { children } = $props();

	let header: Element;

	function shrinkWhenScrolled() {
		const scrollThreshold = 50;
		
		if (document.body.scrollTop > scrollThreshold || document.documentElement.scrollTop > scrollThreshold) {
			header.classList.add("shrunk-header");
		} else {
			header.classList.remove("shrunk-header");
		}
	}
</script>

<svelte:window on:scroll={shrinkWhenScrolled} />

<div class="max-w-screen max-h-screen p-0 m-0">

	<nav class="flex justify-between items-center p-3" bind:this={header}>
		<a href="/" class="logo"><img src="/dino.svg" alt="Stupid Dino Studios" class="w-full h-full"></a>
		<div class='btn-container'>
			<a href="/about">about</a>
		</div>
	</nav>

	<div class="content-container">
		{@render children()}
	</div>
	
</div>

<style>
	:root {
		--nav-height: 80px;
		--shrunk-nav-height: 60px;
		--shrink-transition: 0.2s cubic-bezier(0.3, 0.81, 0.39, 1.39);
	}

	:global(.logo) {
		height: 64px;
		width: 64px;

		transition: var(--shrink-transition);
	}

	:global(.shrunk-header > .logo) {
		height: 54px;
		width: 54px;
	}

	nav {
		border-bottom: 1px solid black;
		
		position: fixed;
		width: 100%;
		top: 0;
		height: var(--nav-height);
		
		transition: var(--shrink-transition);
		
		z-index: 1000;

		background-color: white;

		font-size: 1em;
	}

	:global(.shrunk-header) {
		height: var(--shrunk-nav-height) !important;
		font-size: 0.75em;
	}

	.btn-container {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1rem;

		padding: 5px;

		transition-duration: 1s;
	}

	.content-container {
		margin-top: var(--nav-height);
		padding: 10px;
	}
</style>