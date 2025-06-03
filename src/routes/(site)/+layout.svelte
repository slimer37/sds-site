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
		<a href="/"><img src="/dino.svg" alt="Stupid Dino Studios" width=64 height=64></a>
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
	}

	nav {
		border-bottom: 1px solid black;
		
		position: fixed;
		width: 100%;
		top: 0;
		height: var(--nav-height);
		
		transition: 0.2s cubic-bezier(0.075, 0.82, 0.165, 1);
		
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