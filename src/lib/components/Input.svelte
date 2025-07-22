<script lang="ts">
		type Props = {
			type: 'email' | 'text' | 'password',
			label: string,
			name?: string,
			oninput?: () => void
			required?: boolean
		}

    let { type, label, name, oninput, required }: Props = $props();
</script>


<div class="flex flex-col">
	<label for="{label}" class="text-saira font-light">{label}</label>
	<input {name} id="{label}" {required} {type} {oninput} class="bg-(--login) text-(--bg) opacity-0.4 w-120 h-8 rounded-md flex text-xl items-center justify-center text-center font-bold focus:outline-0">
</div>
