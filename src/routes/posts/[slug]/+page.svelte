<script lang="ts">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
	import { getToastState } from '$lib/components/toast-state.svelte';
	const toastState = getToastState();
	const msg = 'Post ' + $page.params?.['slug'];
	onMount(() => toastState.add('Post Message', msg, 10000));
</script>

<h1 class="text-lg font-semibold">{msg}</h1>
