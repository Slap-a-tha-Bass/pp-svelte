<script>
	import MdWbSunny from 'svelte-icons/md/MdWbSunny.svelte';
	import IoIosMoon from 'svelte-icons/io/IoIosMoon.svelte';
	import IoIosMenu from 'svelte-icons/io/IoIosMenu.svelte';
	import MdClose from 'svelte-icons/md/MdClose.svelte';
	import { darkTheme, menuOpen } from '../theme/store';

	const toggleMenu = () => ($menuOpen = !$menuOpen);
	const toggleDark = () => ($darkTheme = !$darkTheme);

	$: dark = $darkTheme;
	$: open = $menuOpen;
</script>

<div
	class={`relative flex items-center justify-between px-4 sm:px-10 py-5 
        ${dark ? 'bg-gray-800' : 'bg-gray-100'} 
        ${dark ? 'text-gray-100' : 'text-indigo-900'}
        `}
>
	<div class="h-8 w-8">
		<button class="h-8 w-8" on:click={toggleMenu}>
			{#if open == true}
				<MdClose />
			{:else}
				<IoIosMenu />
			{/if}
		</button>
	</div>
	<h4 class="text-2xl sm:text-5xl text-center underline">Pariah Projects</h4>
	<button class="h-6 w-6" on:click={toggleDark}>
		{#if dark == true}
			<MdWbSunny />
		{:else}
			<IoIosMoon />
		{/if}
	</button>
	{#if open == true}
		<div
			class={`absolute top-16 sm:top-20 left-4 w-64 max-h-max z-10 p-10 border-double border-8 border-indigo-900 rounded-lg       
		${dark ? 'bg-gray-900' : 'bg-gray-100'} 
        ${dark ? 'text-white' : 'text-gray-900'}`}
		>
			<ul class="text-lg">
				<li on:click={toggleMenu} on:keydown={toggleMenu} class="mt-3"><a href="/">Home</a></li>
				<li on:click={toggleMenu} on:keydown={toggleMenu} class="mt-3">Projects</li>
				<li on:click={toggleMenu} on:keydown={toggleMenu} class="mt-3">Blog</li>
				<li on:click={toggleMenu} on:keydown={toggleMenu} class="mt-3">Contact</li>
			</ul>
		</div>
	{/if}
</div>
