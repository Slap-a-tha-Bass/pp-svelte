<script>
	import MdWbSunny from 'svelte-icons/md/MdWbSunny.svelte';
	import IoIosMoon from 'svelte-icons/io/IoIosMoon.svelte';
	import IoIosMenu from 'svelte-icons/io/IoIosMenu.svelte';
	import { darkTheme } from '../theme/store';

	const toggleDark = () => ($darkTheme = !$darkTheme);
	$: dark = $darkTheme;
</script>

<div
	class={`relative flex items-center justify-between px-10 py-5 
        ${dark ? 'bg-slate-700' : 'bg-gray-300'} 
        ${dark ? 'text-white' : 'text-gray-900'}
        `}
>
	<div class="h-6 w-6">
		<IoIosMenu />
	</div>
	<h1 class="text-3xl font-bold text-center">Pariah Projects</h1>
	<button class="h-6 w-6" on:click={toggleDark}>
		{#if dark == true}
			<MdWbSunny />
		{:else}
			<IoIosMoon />
		{/if}
	</button>
</div>
