<script lang="ts">
	import Navbar from "./navbar.svelte";
	import Footer from "../footer.svelte";

	let { children } = $props();
</script>

<Navbar />

<div class="max-w-screen max-h-screen p-0 m-0">

	<div class="content-container">
		{@render children()}
	</div>

	<Footer />
	
</div>

<style>
	.content-container {
		margin-top: var(--nav-height);
		padding: 10px;
	}
</style>