<script lang="ts">
	import { handleAnchorClick } from '$lib/utils';
	import { page } from '$app/stores';
	import { navigation } from '$lib/utils';

	export let en = false;
	$: navigationLang = en ? navigation.en : navigation.it;
</script>

<footer class="border-t border-white border-opacity-5 px-4 sm:px-8 lg:px-14">
	<nav class="flex items-start py-8 sm:py-12 justify-between text-xl sm:text-2xl font-light">
		<a href="#top" class="text-5xl sign opacity-90" on:click={handleAnchorClick}> SS </a>

		<div class="flex flex-col sm:flex-row gap-x-7 opacity-80">
			{#each navigationLang as item (item.name)}
				<a href={item.href} on:click={handleAnchorClick}>{item.name}</a>
			{/each}
		</div>
	</nav>
	<div
		class="flex items-center justify-between text-md sm:text-lg font-light pt-2 sm:pt-0 pb-6 opacity-70"
	>
		Copyright © 2023 - Simone Salerno
	</div>
</footer>
