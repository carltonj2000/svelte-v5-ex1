<script lang="ts">
	import { getToastState } from './toast-state.svelte';
	import Toast from './toast.svelte';
	const toastState = getToastState();
</script>

<div class="absolute top-0 right-0 flex flex-col items-center">
	{#each toastState.toasts as toast}
		<Toast {toast} />
	{/each}
</div>
