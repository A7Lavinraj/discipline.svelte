<script lang="ts">
	import '../app.css';
	import Header from '$components/header.svelte';
	let { children } = $props();
</script>

<Header />
<main class="mx-5 my-5">
	{@render children()}
</main>
