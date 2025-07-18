<script lang="ts">
    let { children } = $props();
</script>


<button class="bg-(--text) text-(--bg) w-52 h-10 rounded-md flex text-xl pb-1.5 items-center justify-center text-center font-bold">
    {@render children?.()}
</button>