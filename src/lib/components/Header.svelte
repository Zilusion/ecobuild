<script lang="ts">
	import { page } from '$app/stores';
	import { Home, Wrench, Building2, Users, Mail } from 'lucide-svelte';

	let y = $state(0); // Позиция скролла

	const navLinks = [
		{ href: '/', label: 'Главная', icon: Home },
		{ href: '/services', label: 'Услуги', icon: Wrench },
		{ href: '/projects', label: 'Проекты', icon: Building2 },
		{ href: '/about', label: 'О нас', icon: Users },
		{ href: '/contact', label: 'Контакты', icon: Mail }
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
			href="/contact"
			class="hidden md:block bg-brand-green text-white px-5 py-2 rounded-full font-semibold transition hover:bg-opacity-90 active:scale-95"
		>
			Связаться
		</a>
		<!-- Мобильное меню можно добавить позже, для экзамена достаточно десктопа -->
	</nav>
</header>