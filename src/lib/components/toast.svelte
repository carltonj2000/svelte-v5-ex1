<script lang="ts">
	import type { Toast } from '$lib/types';
	import Icon from '@iconify/svelte';
	import { getToastState } from '$lib/components/toast-state.svelte';
	const toastState = getToastState();
	let { toast }: { toast: Toast } = $props();
</script>

<div class="bg-blue-100 m-2 p-3 shadow-xl rounded flex flex-col items-center w-max">
	<div class="w-full flex justify-end mb-2">
		<button onclick={() => toastState.remove(toast.id)}>
			<Icon icon="ic:outline-close" />
		</button>
	</div>
	<h1 class="text-xl font-bold">
		{toast.title}
	</h1>
	<p>
		{toast.message}
	</p>
</div>
