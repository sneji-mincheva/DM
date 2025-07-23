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
        --footer: #474044;
        --footerT: #F1E9DA;
        --login: rgba(41, 49, 50, 0.4);
				--light: #D9D9D9;
    }

    :global(body) {
        margin: 0;
        background: #F1E9DA;
        user-select: none;
    }
</style>

{@render children()}
