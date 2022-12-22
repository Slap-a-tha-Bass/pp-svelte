<script>
	import Stylesheet from '../theme/Stylesheet.svelte';
	import { darkTheme } from '../theme/store.js';
	import Header from '../components/Header.svelte';

	$: dark = $darkTheme;
</script>

<Stylesheet />

<div class:dark>
	<div class="min-h-screen transition bg-gray-100 text-gray-800 dark:bg-gray-900 dark:text-white">
		<Header />
	</div>
</div>
