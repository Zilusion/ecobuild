<script lang="ts">
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import { fade } from 'svelte/transition';

	export const prerender = true;

	export let data: any;
</script>

<div class="flex min-h-screen flex-col bg-gray-50">
	<Header />
	<main class="flex-grow pt-20"> <!-- pt-20 чтобы контент не уезжал под шапку -->
		{#key data.url}
			<div in:fade={{ duration: 300, delay: 300 }} out:fade={{ duration: 300 }}>
				<slot />
			</div>
		{/key}
	</main>
	<Footer />
</div>