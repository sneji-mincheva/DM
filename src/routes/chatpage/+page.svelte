<script lang="ts">
	import logo from '$lib/assets/logo.svg';
	import newbtn from '$lib/assets/newbtn.svg';
	import search from '$lib/assets/search.svg';
	import learn from '$lib/assets/learn.svg';
	import send from '$lib/assets/send.svg';
	import profile from '$lib/assets/profile.png'
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

<main class="w-[calc(100vw-14rem)] h-screen fixed right-0 flex justify-center">
	<img src="{profile}" alt="profile" class="w-10 fixed right-10 top-12 cursor-pointer">
	<h1 class="text-saira text-3xl fixed text-(--text) mt-10">Welcome</h1>
	<div class="flex h-10">
		<input placeholder="Ask something" type="text" class="w-[40rem] h-10 glassinput chatinput relative bottom-[-89vh] rounded-md active: outline-0 px-4 text-saira">
		<img src="{send}" alt="send" class="w-6 relative bottom-[-89vh] right-10 cursor-pointer">
	</div>
</main>