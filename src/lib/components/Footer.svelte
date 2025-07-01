<script lang="ts">
	import { base } from '$app/paths';
</script>

<footer class="bg-dark-text text-white">
	<div
		class="container mx-auto grid grid-cols-1 gap-8 px-4 py-12 md:grid-cols-3 md:text-left text-center"
	>
		<div>
			<h3 class="text-xl font-bold font-display">EcoBuild</h3>
			<p class="mt-2 text-white/70">Строим будущее, заботясь о планете.</p>
		</div>
		<div>
			<h4 class="font-bold tracking-wider">НАВИГАЦИЯ</h4>
			<ul class="mt-4 space-y-2">
				<li><a href="{base}/services" class="text-white/70 hover:text-white">Услуги</a></li>
				<li><a href="{base}/projects" class="text-white/70 hover:text-white">Проекты</a></li>
				<li><a href="{base}/about" class="text-white/70 hover:text-white">О нас</a></li>
			</ul>
		</div>
		<div>
			<h4 class="font-bold tracking-wider">КОНТАКТЫ</h4>
			<ul class="mt-4 space-y-2 text-white/70">
				<li>г. Москва, ул. Зеленая, д. 1</li>
				<li>+7 (495) 123-45-67</li>
				<li>hello@ecobuild.dev</li>
			</ul>
		</div>
	</div>
	<div class="bg-black/20 py-4 text-center text-sm text-white/50">
		© {new Date().getFullYear()} EcoBuild. Все права защищены.
	</div>
</footer>