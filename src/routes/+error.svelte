<script lang="ts">
	import logo from '$lib/assets/logo.svg';
	import Button from '$lib/components/Button.svelte';
</script>
<main class="h-screen bg-(--bg) flex flex-col items-center justify-center">
	<img src="{logo}" alt="logo" class="fixed top-10 left-10 w-40">
	<div class="flex flex-col gap-12">
	<div class="flex flex-col place-items-center gap-(-5)">
		<p class="text-saira text-(--text) text-9xl">404</p>
		<p class="text-saira text-(--text) text-3xl">Page not found</p>
	</div>
	<div class="flex flex-col place-items-center gap-5">
		<Button onclick={() => {window.location.href = '/'}}>Home</Button>
	</div>
	</div>
</main>