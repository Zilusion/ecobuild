<script lang="ts">
	import ServiceCard from '$lib/components/ServiceCard.svelte';
	import { Wrench, TreePine, ShieldCheck } from 'lucide-svelte';
    import { base } from '$app/paths'; 
</script>

<section class="relative h-[60vh] min-h-[400px] bg-cover bg-center bg-fixed" style="background-image: url('/eco-house.jpg')">
    <div class="absolute inset-0 bg-black/50"></div>
    <div class="relative z-10 container mx-auto flex flex-col items-center justify-center h-full text-center text-white">
        <h1 class="text-4xl md:text-6xl font-bold font-display leading-tight">
            Дома, в которых дышится легко
        </h1>
        <p class="mt-4 max-w-2xl text-lg md:text-xl text-white/80">
            Строим энергоэффективные дома из экологически чистых материалов по современным технологиям.
        </p>
        <a href="{base}/projects" class="mt-8 bg-brand-green text-white px-8 py-3 rounded-full font-semibold text-lg transition hover:bg-opacity-90 active:scale-95">
            Наши проекты
        </a>
    </div>
</section>

<section class="py-16 sm:py-24 bg-white">
    <div class="container mx-auto px-4">
        <div class="text-center">
            <h2 class="text-3xl md:text-4xl font-bold font-display text-dark-text">Почему выбирают EcoBuild</h2>
            <p class="mt-4 max-w-2xl mx-auto text-dark-text/70">
                Мы объединяем любовь к природе и страсть к инновациям для создания вашего идеального дома.
            </p>
        </div>
        <div class="mt-12 grid grid-cols-1 gap-8 md:grid-cols-3">
            <ServiceCard title="Современные технологии" icon={Wrench}>
                Используем передовые каркасные и модульные технологии для скорости и качества.
            </ServiceCard>
            <ServiceCard title="Экологичные материалы" icon={TreePine}>
                Только сертифицированная древесина и безопасные для здоровья утеплители.
            </ServiceCard>
            <ServiceCard title="Гарантия качества" icon={ShieldCheck}>
                Строгий контроль на всех этапах строительства и гарантия на все работы до 10 лет.
            </ServiceCard>
        </div>
    </div>
</section>

<section class="bg-gray-100">
    <div class="container mx-auto px-4 py-16 text-center">
        <h2 class="text-3xl font-bold font-display text-dark-text">Готовы построить дом мечты?</h2>
        <p class="mt-2 text-lg text-dark-text/70">Свяжитесь с нами для бесплатной консультации и расчета стоимости.</p>
        <a href="{base}/contact" class="mt-6 inline-block bg-brand-green text-white px-8 py-3 rounded-full font-semibold text-lg transition hover:bg-opacity-90 active:scale-95">
            Обсудить проект
        </a>
    </div>
</section>