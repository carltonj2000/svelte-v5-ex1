<script lang="ts">
	import { getToastState } from '$lib/components/toast-state.svelte';
	const toastState = getToastState();
	let title = $state('');
	let message = $state('');
	let titleInput = $state<HTMLInputElement>();

	const setToastState = (e: any) => {
		e.preventDefault();
		toastState.add(title, message);
		title = '';
		message = '';
		titleInput?.focus();
	};
</script>

<h1 class="text-xl font-bold mb-4">Home Page</h1>

<form class="flex flex-col items-start gap-2 w-min" onsubmit={setToastState}>
	<label for="name">Title</label>
	<input name="title" class="border rounded-md" bind:value={title} bind:this={titleInput} />
	<label for="message">Message</label>
	<input name="message" class="border rounded-md" bind:value={message} />
	<button class="bg-green-200 px-2 py-1 rounded shadow-md w-full">Add Toast</button>
</form>
