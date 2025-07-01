<script lang="ts">
	import { Home, ClipboardList, Lightbulb, DraftingCompass } from 'lucide-svelte';
	import { base } from '$app/paths';

	const services = [
		{
			title: 'Индивидуальное проектирование',
			description:
				'Разработаем уникальный проект вашего будущего дома с учетом всех ваших пожеланий, особенностей участка и современных архитектурных тенденций.',
			icon: DraftingCompass,
			imageUrl: '/services/service1.webp'
		},
		{
			title: 'Строительство "под ключ"',
			description:
				'Берем на себя все этапы: от заливки фундамента до финишной отделки. Вы получаете готовый к заселению дом в оговоренные сроки.',
			icon: Home,
			imageUrl: '/services/service2.webp'
		},
		{
			title: 'Внутренняя отделка',
			description:
				'Выполняем отделочные работы с использованием экологически чистых материалов. Создаем интерьеры, в которых комфортно жить и дышать.',
			icon: Lightbulb,
			imageUrl: '/services/service1.webp'
		},
		{
			title: 'Ландшафтный дизайн',
			description:
				'Организуем пространство вокруг вашего дома: от газона и дорожек до систем автополива и зон отдыха, чтобы создать гармонию с природой.',
			icon: ClipboardList,
			imageUrl: '/services/service4.webp'
		}
	];
</script>

<div class="container mx-auto px-4 py-16">
	<div class="text-center">
		<h1 class="font-display text-dark-text text-4xl font-bold">Наши услуги</h1>
		<p class="text-dark-text/70 mx-auto mt-4 max-w-2xl text-lg">
			Мы предлагаем полный комплекс услуг для создания дома вашей мечты — от идеи до воплощения.
		</p>
	</div>

	<div class="mt-16 space-y-16">
		{#each services as service, i}
			<div
				class="flex flex-col items-center gap-8 md:flex-row md:gap-12 {i % 2 !== 0
					? 'md:flex-row-reverse'
					: ''}"
			>
				<div class="w-full md:w-1/2">
					<img
						src={service.imageUrl}
						alt={service.title}
						class="h-80 w-full rounded-xl object-cover shadow-lg"
					/>
				</div>

				<div class="w-full text-center md:w-1/2 md:text-left">
					<div
						class="bg-brand-green/10 text-brand-green inline-flex h-14 w-14 items-center justify-center rounded-full"
					>
						<svelte:component this={service.icon} size={28} />
					</div>
					<h2 class="font-display text-dark-text mt-4 text-3xl font-bold">{service.title}</h2>
					<p class="text-dark-text/80 mt-4 leading-relaxed">
						{service.description}
					</p>
					<a
						href="{base}/contact"
						class="text-brand-green mt-6 inline-block font-semibold hover:underline"
					>
						Узнать больше →
					</a>
				</div>
			</div>
		{/each}
	</div>
</div>
