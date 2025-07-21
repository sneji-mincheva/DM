<script lang="ts">
    let { children } = $props();
</script>


<input class="bg-(--login) text-(--bg) opacity-0.4 w-120 h-8 rounded-md flex text-xl pb-1.5 items-center justify-center text-center font-bold">
    {@render children?.()}