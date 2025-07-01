<script lang="ts">
	export let title: string;
	export let icon;
</script>

<div class="group rounded-lg bg-white p-6 text-center transition hover:shadow-xl hover:-translate-y-2 border">
	<div
		class="mx-auto flex h-16 w-16 items-center justify-center rounded-full bg-brand-green/10 text-brand-green transition group-hover:bg-brand-green group-hover:text-white"
	>
		<svelte:component this={icon} size={32} />
	</div>
	<h3 class="mt-6 text-xl font-bold font-display text-dark-text">{title}</h3>
	<p class="mt-2 text-dark-text/70">
		<slot />
	</p>
</div>