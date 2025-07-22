<script lang="ts">
    type Props = {
        children: any;
        onclick?: () => void;
        type?: "button" | "submit" | "reset" | undefined;
    }

    let { children, onclick, type }: Props = $props();
</script>


<button onclick="{onclick}" {type} class="bg-(--text) text-(--bg) w-52 h-10 rounded-md flex text-xl pb-1.5 items-center justify-center text-center font-bold cursor-pointer">
    {@render children?.()}
</button>