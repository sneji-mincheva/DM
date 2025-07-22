<script lang="ts">
    import logo from '$lib/assets/logo.svg'
    import logow from '$lib/assets/logow.svg'
    import profile from '$lib/assets/profile.png'
    import blob1 from '$lib/assets/blob1.svg'
    import blob2 from '$lib/assets/blob2.svg'
    import blob3 from '$lib/assets/blob3.svg'
    import Button from "$lib/components/Button.svelte";
    import media from '$lib/assets/media.svg'
    import write from '$lib/assets/write.svg'
    import learn from '$lib/assets/learn.svg'
    import {onMount} from "svelte";
    import about from '$lib/assets/about.svg'

    function scrollToTarget(headerOffset: number, element: HTMLElement){
        const elementPosition = element.getBoundingClientRect().top;
        const offsetPosition = elementPosition + window.pageYOffset - headerOffset;

        window.scrollTo({
             top: offsetPosition,
             behavior: "smooth"
        });
}



    onMount(() =>{
        const profile = document.querySelector('#profile') as HTMLElement
        profile.addEventListener('click', () => {window.location.href = '/login'})

        let pos =  $state(window.scrollY)
        $effect(()=>{
            pos = window.scrollY
            if(pos > 50) {
                const navbar: HTMLElement = document.querySelector('nav') as HTMLElement
                const links: HTMLDivElement = document.querySelector("#links") as HTMLDivElement
                links.classList.add("text-(--text)")
                navbar.classList.add("glass")
            }
        })
        const navbar: HTMLElement = document.querySelector('nav') as HTMLElement
        const links: HTMLDivElement = document.querySelector("#links") as HTMLDivElement
        if(window.screenY > 50) {
            links.classList.add("text-(--text)")
            navbar.classList.add("glass")
        }
        window.addEventListener("scroll", () => {
            if(window.scrollY > 50){
                links.classList.add("text-(--text)")
                navbar.classList.add("glass")
            }

            else {
                links.classList.remove("text-(--text)")
                navbar.classList.remove("glass")
            }
        })
        window.addEventListener("scrollend", () => {
            if(window.scrollY < 50) navbar.classList.remove("glass")
        }
        )

        const product = document.querySelector('#product') as HTMLElement
        const productbtn = document.querySelector('#productbtn') as HTMLElement
        const productbtn2 = document.querySelector('#productbtn2') as HTMLElement
        productbtn.addEventListener('click', () => {
           scrollToTarget(250, product)
        })
        productbtn2.addEventListener('click', () => {
           scrollToTarget(250, product)
        })

        const about = document.querySelector('#about') as HTMLElement
        const aboutbtn = document.querySelector('#aboutbtn') as HTMLElement
        const aboutbtn2 = document.querySelector('#aboutbtn2') as HTMLElement
        aboutbtn.addEventListener('click', () => {
           scrollToTarget(100, about)
        })
        aboutbtn2.addEventListener('click', () => {
           scrollToTarget(100, about)
        })
        const help = document.querySelector('#help') as HTMLElement
        const helpbtn = document.querySelector('#helpbtn') as HTMLElement
        const helpbtn2 = document.querySelector('#helpbtn') as HTMLElement
        helpbtn.addEventListener('click', () => {
           scrollToTarget(130, help)
        })
        helpbtn2.addEventListener('click', () => {
           scrollToTarget(130, help)
        })
    })
</script>
<nav class="w-screen h-20 flex items-center fixed z-20">
    <ul class="flex justify-evenly items-center w-screen gap-50">
        <li class="flex mt-1">
            <img src="{logo}" alt="logo" class="w-24 h-12">
        </li>
        <li>
            <div id="links" class="flex gap-20 justify-center mr-10 text-saira text-(--bg) text-2xl z-50 select-none">
                <p class="z-10 cursor-pointer" id="productbtn">Product</p>
                <p class="z-10 cursor-pointer" id="aboutbtn">About</p>
                <p class="z-10 cursor-pointer" id="helpbtn">Help</p>
            </div>
        </li>
        <li>
            <img src="{profile}" alt='profile' class="w-12 h-12" id="profile">
        </li>
    </ul>
</nav>

<main class="flex flex-col gap-5 items-center justify-center h-screen z-30 overflow-x-hidden">
    <h1 class="text-saira font-bold text-(--text) text-[2.5rem] text-center">All-in-One Support for<br>the Modern Designer</h1>
    <p class="text-saira text-(--text) text-center mb-16">DesignMate AI supercharges your creative process with smart tools for visuals, copy, and<br> design learning — all in one place. Create faster, design smarter.</p>
    <Button onclick={() => {window.location.href = '/chatpage'}}>Start your journey</Button>
    <img src="{blob1}" alt="decoration" class="w-60 absolute left-[-1rem] bottom-[-.7rem] z-10 blob">
    <img src="{blob2}" alt="decoration" class="w-[30rem] absolute left-[calc(50%-15rem)] top-[-1rem] blob z-10">
    <img src="{blob3}" alt="decoration" class="w-60 absolute right-0 bottom-[-.7rem] blob z-10">
</main>

<section class="gap-7 flex flex-col h-screen z-50 text-center justify-center items-center">
    <div class="w-[50rem] bg-cyan-50 h-90">

    </div>
    <p class="text-md font-medium text-saira text-(--text)" >DesignMate AI supercharges your creative process with smart tools for visuals, copy, and <br> design learning — all in one place. Create faster, design smarter.</p>
</section>
<section class="h-[49vh] flex justify-baseline items-center flex-col gap-16" id="product">
    <p class="text-saira font-light text-center text-2xl">Product</p>
    <div class="flex gap-32">
        <div class="flex flex-col gap-2">
            <img src="{media}" alt="decoration" class="h-15" >
            <p class="text-saira font-normal text-center text-xl">Generates media</p>
        </div>
        <div class="h-25 w-[.3rem] rounded-2xl bg-gradient-to-b from-(--text) to-(--lighter)"></div>
        <div class="flex flex-col gap-2">
            <img src="{write}" alt="decoration" class="h-15" >
            <p class="text-saira font-normal text-center text-xl">Copywrites</p>
        </div>
        <div class="h-25 w-[.3rem] rounded-2xl bg-gradient-to-b from-(--text) to-(--lighter)"></div>
        <div class="flex flex-col gap-2">
            <img src="{learn}" alt="decoration" class="h-15">
            <p class="text-saira font-normal text-center text-xl">Helps you learn</p>
        </div>
    </div>
</section>
<section class="h-50 flex items-center justify-baseline flex-col gap-20" id="about">
    <p class="text-saira font-light text-center text-2xl gap-2">About</p>
    <div class="flex items-center gap-20">
        <p class="text-saira font-normal text-xl text-(--text) leading-6 text-center">An AI-powered platform for generating<br> images, videos, and copywriting. Learn<br> design theory and grow your skills. Made<br> to help designers create more effectively.</p>
        <img src="{about}" class="w-[30rem] h-64" alt="about">
    </div>
</section>
<section class="h-[45vw] flex flex-col justify-center items-center gap-10 mt-10" id="help">
    <p class="text-saira font-light text-center text-2xl gap-5">Help</p>
    <p class="text-saira font-medium text-2xl text-(--text) text-center mb-6">Text us at our official<br> social media pages.</p>
    <img src ="{blob1}" class="h-80 absolute left-[-1rem] bottom-[-266vh] blob" alt="blob">
    <img src ="{blob3}" class="h-60 absolute right-0 bottom-[-266vh] blob" alt="blob">
</section>
<footer class="flex items-center justify-center w-full h-80 bg-(--footer) flex-col">
    <div class="flex justify-between w-[99vw] px-5">
        <p class="text-(--footerT) text-saira text-2xl font-bold">Contact us</p>
        <p class="text-(--footerT) text-saira text-2xl font-bold">Navigation</p>
    </div>
    <div class="flex justify-between w-[99vw] px-5">
        <div class="flex flex-col gap-2 mt-16">
            <a class="text-(--footerT) text-saira font-medium text-2xl text-left">Facebook</a>
            <a class="text-(--footerT) text-saira font-medium text-2xl text-left">Instagram</a>
            <a class="text-(--footerT) text-saira font-medium text-2xl text-left">Email</a>
        </div>
        <img src="{logow}" class="w-40 h-40 justify-center" alt="logo-white">
        <div class="flex flex-col gap-2 mt-16">
            <p class="text-(--footerT) text-saira font-medium text-2xl text-right cursor-pointer" id="productbtn2">Product</p>
            <p class="text-(--footerT) text-saira font-medium text-2xl text-right cursor-pointer" id="aboutbtn2">About</p>
            <p class="text-(--footerT) text-saira font-medium text-2xl text-right cursor-pointer" id="helpbtn2">Help</p>
        </div>
    </div>
    <p class="text-(--footerT) text-saira text-xl font-light relative bottom-[-2rem]">Privacy Policy | Terms of Use</p>
</footer>