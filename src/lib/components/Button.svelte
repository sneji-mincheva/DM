<script lang="ts">
    type Props = {
        children: any;
        onclick: () => void;
    }

    let { children, onclick }: Props = $props();
</script>


<button onclick="{onclick}" class="bg-(--text) text-(--bg) w-52 h-10 rounded-md flex text-xl pb-1.5 items-center justify-center text-center font-bold cursor-pointer">
    {@render children?.()}
</button>