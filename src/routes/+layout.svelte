<script lang="ts">
	import '../app.css';
    import '../fonts.css'

	let { children } = $props();
</script>

<style>
    :root{
        --bg: #F1E9DA;
        --text: #293132;
        --lighter: #4F5165;
    }

    :global(body) {
        margin: 0;
        background: #F1E9DA;
    }
</style>

{@render children()}
