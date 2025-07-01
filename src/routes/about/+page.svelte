<script lang="ts">
	import { Award, Target, Users } from 'lucide-svelte';
	import { base } from '$app/paths';

	const team = [
		{
			name: 'Алексей Иванов',
			role: 'Генеральный директор, Основатель',
			imageUrl: `${base}/about/person1.jpg`
		},
		{
			name: 'Елена Петрова',
			role: 'Главный архитектор',
			imageUrl: `${base}/about/person2.jpg`
		},
		{
			name: 'Дмитрий Сидоров',
			role: 'Руководитель строительных проектов',
			imageUrl: `${base}/about/person3.jpg`
		}
	];
</script>

<div class="bg-white">
	<div class="container mx-auto px-4 py-16 sm:py-24">
		<div class="grid grid-cols-1 items-center gap-12 md:grid-cols-2">
			<div>
				<h1 class="text-4xl font-bold font-display text-dark-text">О компании EcoBuild</h1>
				<p class="mt-6 text-lg text-dark-text/80 leading-relaxed">
					Компания <strong>EcoBuild</strong> была основана в 2015 году с одной простой идеей:
					создавать дома, которые находятся в гармонии с природой и их жителями. Мы верим, что
					современный дом должен быть не только красивым и функциональным, но и экологичным,
					энергоэффективным и здоровым.
				</p>
				<p class="mt-4 text-dark-text/80 leading-relaxed">
					За годы работы мы собрали команду лучших специалистов и отточили технологии, чтобы
					предлагать вам надежные и долговечные решения.
				</p>
			</div>
			<div>
				<img
					src="{base}/about/team.jpg"
					alt="Команда EcoBuild за работой"
					class="rounded-xl shadow-lg"
				/>
			</div>
		</div>
	</div>
</div>

<div class="bg-gray-50">
	<div class="container mx-auto px-4 py-16 sm:py-24">
		<div class="grid grid-cols-1 gap-12 md:grid-cols-3">
			<div class="text-center">
				<Award class="mx-auto h-12 w-12 text-brand-green" />
				<h3 class="mt-4 text-2xl font-bold font-display">Качество</h3>
				<p class="mt-2 text-dark-text/70">
					Бескомпромиссное внимание к деталям на каждом этапе строительства.
				</p>
			</div>
			<div class="text-center">
				<Target class="mx-auto h-12 w-12 text-brand-green" />
				<h3 class="mt-4 text-2xl font-bold font-display">Инновации</h3>
				<p class="mt-2 text-dark-text/70">
					Постоянный поиск и внедрение лучших мировых технологий в строительстве.
				</p>
			</div>
			<div class="text-center">
				<Users class="mx-auto h-12 w-12 text-brand-green" />
				<h3 class="mt-4 text-2xl font-bold font-display">Клиентоориентированность</h3>
				<p class="mt-2 text-dark-text/70">
					Мы слышим наших клиентов и строим партнерские отношения, основанные на доверии.
				</p>
			</div>
		</div>
	</div>
</div>

<div class="bg-white">
	<div class="container mx-auto px-4 py-16 sm:py-24">
		<div class="text-center">
			<h2 class="text-3xl md:text-4xl font-bold font-display text-dark-text">Наша команда</h2>
			<p class="mt-4 max-w-2xl mx-auto text-lg text-dark-text/70">
				Профессионалы, которые любят свое дело и вкладывают душу в каждый проект.
			</p>
		</div>
		<div class="mt-16 grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3">
			{#each team as member}
				<div class="text-center">
					<img
						src={member.imageUrl}
						alt="Фото {member.name}"
						class="mx-auto h-40 w-40 rounded-full object-cover shadow-md"
					/>
					<h4 class="mt-6 text-xl font-bold">{member.name}</h4>
					<p class="text-brand-green">{member.role}</p>
				</div>
			{/each}
		</div>
	</div>
</div>