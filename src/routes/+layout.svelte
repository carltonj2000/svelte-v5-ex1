<script lang="ts">
	import Nav from '$lib/components/nav.svelte';
	import Toaster from '$lib/components/toaster.svelte';
	import { setToastState } from '$lib/components/toast-state.svelte';

	import type { Snippet } from 'svelte';
	import './app.css';

	let { children }: { children: Snippet } = $props();

	setToastState();
</script>

<Toaster />
<Nav />
<main class="p-4 relative">
	{@render children()}
</main>
