<script lang="ts">
		type Props = {
			type: 'email' | 'text' | 'password',
			label: string,
		}

    let { type, label }: Props = $props();
</script>


<div class="flex flex-col">
	<label for="{label}" class="text-saira font-light">{label}</label>
	<input id="{label}" type="{type}" class="bg-(--login) text-(--bg) opacity-0.4 w-120 h-8 rounded-md flex text-xl items-center justify-center text-center font-bold focus:outline-0">
</div>
