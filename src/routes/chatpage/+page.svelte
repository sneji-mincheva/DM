<script lang="ts">
	import logo from '$lib/assets/logo.svg';
	import newbtn from '$lib/assets/newbtn.svg';
	import search from '$lib/assets/search.svg';
	import learn from '$lib/assets/learn.svg';
	import send from '$lib/assets/send.svg';
	import profile from '$lib/assets/profile.png'
	import image from '$lib/assets/image.png'
	import { onMount } from 'svelte';

	let visible = $state(false);

	function toggle() {
		visible = !visible;
	}

	let response = $state(	);

	async function send_prompt() {
		const prompt = (document.querySelector('#prompt') as HTMLInputElement).value;
		(document.querySelector("#prompt") as HTMLInputElement).value = '';

		return puter.ai.chat(prompt, { model: "gpt-4o-mini" })
	}

	onMount(() => {
		const profilebtn = document.querySelector('#profile') as HTMLImageElement;
		profilebtn.addEventListener('click', toggle);
	})
</script>


<nav class="flex flex-col items-center w-56 h-screen pt-10 fixed">
	<div class="h-screen w-56 chatbar fixed top-0 left-0"></div>
	<img src="{logo}" alt="logo" class="w-30 opacity-80">
	<ul
		class="mt-16 flex flex-col gap-6">
		<li class="flex justify-start items-center gap-4 w-56 px-4">
			<img src="{newbtn}" alt="newbtn" class="opacity-75 w-9 cursor-pointer">
			<p class="text-(--lighter) text-saira text-lg font-medium">New chat</p>
		</li>
		<li class="flex justify-start items-center gap-4 w-56 px-4">
			<img src="{search}" alt="search" class="opacity-75 w-9 cursor-pointer">
			<p class="text-(--lighter) text-saira text-lg font-medium">Find chat</p>
		</li>
		<li class="flex justify-start items-center gap-4 w-56 px-4 ">
			<img src="{learn}" alt="search" class="opacity-60 w-9 cursor-pointer">
			<p class="text-(--lighter) text-saira text-lg font-medium">Learn</p>
		</li>
		<li>
			<div class="w-56 h-0.5 bg-(--light) opacity-35"></div>
		</li>
	</ul>
</nav>

<section class="absolute w-[calc(100vw-14rem)] mt-30 min-h-screen h-[200vw] overflow-scroll right-0">
	{#if response}
		{#await response}
			<p>Loading...</p>
		{:then res}
				<p>{res.toString()}</p>
		{:catch error}
			<p>{error}</p>
		{/await}
	{/if}
</section>

<main class="w-[calc(100vw-14rem)] h-screen fixed flex justify-center right-0">
	<img src="{profile}" alt="profile" class="w-10 fixed right-10 top-12 cursor-pointer" id="profile">
	{#if visible}
		<form action="?/logout" method="post">
			<button type="submit" class="cursor-pointer w-20 h-8 bg-(--text) text-(--bg) rounded-md fixed right-10 top-24 active: outline-0">Logout</button>
		</form>
	{/if}
	<h1 class="text-saira text-3xl fixed text-(--text) mt-10">Welcome</h1>
	<div class="flex h-10 z-40">
		<input id="prompt" placeholder="Ask something" type="text" class="w-[40rem] h-10 glassinput chatinput relative bottom-[-89vh] rounded-md active: outline-0 px-10 text-saira z-40">
		<button onclick="{() => {}}">
			<img src="{image}" alt="send" class="w-6 relative bottom-[-89vh] right-10 cursor-pointer z-40">
		</button>
		<button onclick="{() => {response = send_prompt()}}">
			<img src="{send}" alt="send" class="w-6 relative bottom-[-89vh] right-10 cursor-pointer z-40 opacity-40">
		</button>
	</div>
</main>

