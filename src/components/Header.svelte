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
	class={`relative flex items-center justify-between px-10 py-6 
        ${dark ? 'bg-slate-700' : 'bg-gray-300'} 
        ${dark ? 'text-white' : 'text-gray-900'}
        `}
>
	<div class="h-8 w-8">
		<button class="h-6 w-6" on:click={toggleMenu}>
			{#if open == true}
				<MdClose />
			{:else}
				<IoIosMenu />
			{/if}
		</button>
	</div>
	<h1 class="text-3xl font-bold text-center">Pariah Projects</h1>
	<button class="h-6 w-6" on:click={toggleDark}>
		{#if dark == true}
			<MdWbSunny />
		{:else}
			<IoIosMoon />
		{/if}
	</button>
	{#if open == true}
		<div
			class={`absolute top-20 left-0 w-64 max-h-max z-10 p-10        
		${dark ? 'bg-slate-700' : 'bg-gray-300'} 
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
