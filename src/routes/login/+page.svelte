 <script lang="ts">
 import Input from "$lib/components/Input.svelte";
 import Button from "$lib/components/Button.svelte";
 import blob1 from '$lib/assets/blob1.svg';
 import blob3 from '$lib/assets/blob3.svg';
 import logo from '$lib/assets/logo.svg';
 import google from '$lib/assets/google.svg';
 import { onMount } from 'svelte';

  onMount(() => {
   document.querySelector('#logo')?.addEventListener('click', () => {window.location.href = '/'})
 })
 </script>

 <nav class="w-screen h-20 flex items-center fixed z-20">
    <ul class="flex justify-start items-center w-screen gap-50 p-10">
        <li class="flex mt-1">
            <img src="{logo}" alt="logo" class="w-24 h-12 cursor-pointer" id="logo">
        </li>
    </ul>
</nav>

 <main class="flex flex-col gap-4 items-center justify-center h-screen z-30 overflow-x-hidden">
   <p class="text-saira text-(--text) text-3xl mb-16">Welcome back</p>
   <Input type="email" label="Email" />
   <Input type="password" label="Password" />
    <div class="flex flex-col justify-center items-center gap-2 mb-10">
      <p class="text-saira font-light text-(--text)">or use</p>
      <img src="{google}" alt="google" class="w-10">
    </div>
   <Button>Log in</Button>

   <img src="{blob1}" alt="decoration" class="w-60 absolute left-[-1rem] bottom-[-.7rem] z-10 blob">
   <img src="{blob3}" alt="decoration" class="w-60 absolute right-0 bottom-[-.7rem] blob z-10">
   <a href="/register" class="absolute bottom-10 right-10 z-20"><p class="text-saira font-light text-(--bg)">No account? <b>Sign up</b></p></a>
 </main>