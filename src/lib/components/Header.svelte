<script lang="ts">
	import { page } from '$app/stores';
	import { base } from '$app/paths';
	import { Home, Wrench, Building2, Users, Mail } from 'lucide-svelte';

	let y = $state(0);
	const navLinks = [
		{ href: `${base}/`, label: 'Главная', icon: Home },
		{ href: `${base}/services`, label: 'Услуги', icon: Wrench },
		{ href: `${base}/projects`, label: 'Проекты', icon: Building2 },
		{ href: `${base}/about`, label: 'О нас', icon: Users },
		{ href: `${base}/contact`, label: 'Контакты', icon: Mail }
	];
</script>

<svelte:window bind:scrollY={y} />

<header
	class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
	class:bg-white={y > 50}
	class:shadow-md={y > 50}
	class:backdrop-blur-sm={y > 50}
>
	<nav class="container mx-auto flex items-center justify-between p-4">
		<a href="/" class="text-2xl font-bold font-display text-brand-green"> EcoBuild </a>
		<ul class="hidden items-center gap-6 md:flex">
			{#each navLinks as link}
				<li>
					<a
						href={link.href}
						class="text-dark-text/70 transition-colors hover:text-brand-green font-semibold"
						class:text-brand-green={$page.url.pathname === link.href}
					>
						{link.label}
					</a>
				</li>
			{/each}
		</ul>
		<a
			href="{base}/contact"
			class="hidden md:block bg-brand-green text-white px-5 py-2 rounded-full font-semibold transition hover:bg-opacity-90 active:scale-95"
		>
			Связаться
		</a>
	</nav>
</header>