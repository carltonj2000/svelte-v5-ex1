<script lang="ts">
	import { page } from '$app/stores';
	const links = [
		{ href: '/', name: 'Home' },
		{ href: '/posts', name: 'Posts' }
	];
	const cls = (href: string) => {
		console.log(href, $page.url.pathname);
		return 'px-2 py-1 rounded ' + (href === $page.url.pathname ? 'bg-pink-500' : 'bg-pink-300');
	};
</script>

<nav class="flex bg-pink-100 p-4 gap-2">
	{#each links as { href, name }}
		<div class={cls(href)}><a {href}>{name}</a></div>
	{/each}
</nav>
