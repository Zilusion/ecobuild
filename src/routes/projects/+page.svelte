<script lang="ts">
	import { base } from '$app/paths';

	const projects = [
		{
			title: 'Дом "Сканди"',
			location: 'Подмосковье, КП "Лесной остров"',
			area: '180 м²',
			imageUrl: `${base}/projects/project1.jpg`
		},
		{
			title: 'Вилла "Панорама"',
			location: 'Сочи, Красная Поляна',
			area: '250 м²',
			imageUrl: `${base}/projects/project2.webp`
		},
		{
			title: 'Коттедж "Лесная симфония"',
			location: 'Ленинградская обл., пос. Репино',
			area: '210 м²',
			imageUrl: `${base}/projects/project3.webp`
		},
		{
			title: 'Дом "Минимал"',
			location: 'Казань, пос. "Зеленый бор"',
			area: '150 м²',
			imageUrl: `${base}/projects/project4.webp`
		},
		{
			title: 'Шале "Горный воздух"',
			location: 'Алтайский кrai',
			area: '190 м²',
			imageUrl: `${base}/projects/project5.webp`
		},
		{
			title: 'Дуплекс "Гармония"',
			location: 'г. Тверь',
			area: '2x120 м²',
			imageUrl: `${base}/projects/project6.jpg`
		}
	];
</script>

<div class="container mx-auto px-4 py-16">
	<div class="text-center">
		<h1 class="font-display text-dark-text text-4xl font-bold">Выполненные проекты</h1>
		<p class="text-dark-text/70 mx-auto mt-4 max-w-2xl text-lg">
			Мы гордимся каждым построенным домом. Посмотрите на некоторые из наших работ.
		</p>
	</div>

	<div class="mt-16 grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3">
		{#each projects as project}
			<div
				class="group overflow-hidden rounded-xl bg-white shadow-md transition-shadow hover:shadow-2xl"
			>
				<div class="overflow-hidden">
					<img
						src={project.imageUrl}
						alt={project.title}
						class="h-64 w-full object-cover transition-transform duration-500 group-hover:scale-110"
					/>
				</div>
				<div class="p-6">
					<h3 class="font-display text-dark-text text-xl font-bold">{project.title}</h3>
					<p class="text-dark-text/60 mt-2">{project.location}</p>
					<div class="mt-4 border-t pt-4">
						<span class="text-brand-green font-semibold">Площадь: {project.area}</span>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>
